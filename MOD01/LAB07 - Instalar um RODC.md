## Criar a midia IFM

* Abra o cmd e digite :
    * ``` ntdsutil ```
    * ``` ifm ```
    * ``` activate instance ntds ```
    * ``` ifm ```
    * ``` create sysvol rodc c:\rodc ```

* Exporte o conteudo para o servidor que sera o RODC
* Faca o mesmo processo de adicionar um novo servidor DC, so altere as opcoes de Read-only domain controller na segunta tela de conf
* Selecione a opcao install from midia e seleciona os dados que importou do outro servidor AD

* Grupos que serao importantes para o RODC (usados somente para especificar quem podera ter os dados em cache)
* Deve ser definido os usarios e os computadores
    * Allowed RODC Password Replication Group
    * Denied RODC Password Replication Group

* Pode ser necessario dar privilegios de delegacao para um usuario para controlar o servidor
    * Clique com botao direito sob o icone do servidor na OU domain controllers dentro de usuarios e computadores
    * Selecione propriedades e depois selecione managed by e defina o usuario
    * O usario deve estar sincronizado no grupo : Allowed RODC Password Replication Group 