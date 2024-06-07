* Sysvol
  * Diretorio existente em cada controlador de dominio
  * Contem alguns itens de politicas de groupos, alguns scripts
  * É replicado entre os controladores de dominio com o DFS
  * Tambem armazenda o KDC
 
* KDC
  * Kerberos distribution center
  * Kerberos é um tipo de padrao de autenticacao utilisado pelo active directory
    * Kerberos que cuida de toda autenticacao do ADDS, users, computers SSO  

* Upgrade
  * Perform in-place upgrade
  * ADD new server and promote to domain controller

## Deploy AD DS domain controllers in Azure Virtual Machine

* Network topology
  * É preciso estar com uma topologia extendidade, uma rede hybrida
 
* Site topology
  * Criar um site para o Azure, para assim quem esta no Azure autentique nos controladores de dominio do Azure

* IP addressing:
  * Recomendado que o controlador de dominio tenha um IP estatico
 
* DNS
  * Usar o DNS do windows server e configurar na rede vnet do Azure o DNS
 
* Disks
  * Cuidar para nao colocar discos com cache nas configuracoes da VM que sera instalado o ADDS, pois ele perde tempo.
 
## Backup

* Habilitar lixeira do ADDS
* Nao usar snapshot
* Ter um backup full (system state)
* Ter backup do Sysvol
* Restore Autoritativo e nao autoritativo
   * Autoritativo, quando executado, ele sera quem tera a copia valida, todos os outros iram buscar as infos a partir dele
   * Nao autoritativo, quando um dos controladores de dominio nao esta sincronizando, voce volta o system state como nao autoritativo, assim ele vai buscar a replicacao de outro servidor
 
## Manage the ADDS global catalog role


* Global catalog
  * Tudo que existe dentro do ADDS vai estar dentro do catalago, com seus parametros, objetos e configuracoes
  * O primeiro controlador de dominio obrigatoriamento ele sera o catalago global
  * Voce pode selecionar quem sera o servidor com o catalago global

## FSMO

* É recomendado fazer a divisao das FSMO no servidores, deixar as de Florest em um e as de dominio em outro
* As funcoes de dominio podem ter mais de uma dentro do dominio, as de florestas sao unicas

* Forest oprations masters:
  * Domain naming master
    * Responsavel por gerenciar toda a parte de maming da floresta
    * Responsavel por gerenciar as alteracoes no namespace do dominio dentro de uma floresta
  * Schema master
    * Controla todas as atualizacoes e modificacoes no esquema do Active Directory
 
* Domain oprations masters:
  * RID master
    * Relative identifier, ele desempenha um papel essencial na alocacao de identificadores relativos (RIDs) que sao usados para criar identificadores unicos de seguranca (SIDs) para objetos no dominio.
    * Ele que libera o RID para cada objeto (tipo dar um CPF para cada pessoa)
  * Infrasctrucure master
     * É reponsavel por cuidar da parte da replicacao e validacao de objetos
     * Quando nao tem todos os servidores como catalago global, ele ira ficar cuidando e validando quando um atributo é alterado
     * Se voce alterar alguma informacao no seu usuario, ele vai atualizar se para todos os servidores
  * PDC emulator master
     * Toda criacao tinha que ser feito no pdc que o mesmo replicava para os outros servidores, hoje nao se usa mais isso
     * Ele que controla o servidor de TIME do dominio
 








