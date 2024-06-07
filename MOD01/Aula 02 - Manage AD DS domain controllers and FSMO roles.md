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
