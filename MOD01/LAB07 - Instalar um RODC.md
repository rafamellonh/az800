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