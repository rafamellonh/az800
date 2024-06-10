## ADDS

* É um service de diretorio utilisado para centralizar todas identidades dentro da infraestrutura de rede (user, passwords, pcs e etcs)

## Logical components

* Partitions
    * É basicamente uma parte do banco de dados do ADDS, banco esse que é um arquivo NTDS.dit(quase que um banco de dados) onde tem varias particoes, aqui algumas : 
    * particao de dominio : contem usuarios, grupos, computadores e outros objetos do dominio
    * particao de configuracao : contem os objetos de configuracao da floresta
    * particao de esquema : contém uma copia do schema

    * Como criar uma AD DS partition?
        * NtdsUtil.exe


* Schema
    * É um conjunto de definicoes que determinam a estrutura dos dados que podem ser armazenados no diretorio. Ele determina classes de objetos e os atributos que esses
      objetos podem ter.

* Domains
    * É uma unidade administrativa fundamental que organiza os recursos de uma rede, como users, computers, grupos e dispositivos de maneira logica e gerenciavel. 
    * Voce pode organizar o dominio com relacoes de pai-filho

* Domains trees
    * É uma estrutura hierarquica que consiste em um ou mais dominios que compartilham um namespace continuio.
    * example.com, rs.example.com e sp.example.com

* Forests
    * É a estrutura de mais alto nivel em uma implantacao do ADDS, é um agrupamento de uma ou mais arvores de dominios que compartilham um esquema comum

* Sites
    * Representa uma ou mais sub-redees fisicas, sao usados principalmente para gerenciar a replicacao de dados entre controladores de dominio e para otimizar
      a autenticacao e o trafego de rede em uma infra.
* OUs
     * É um objeto de container para usarios, computadores, grupos e objetos usado para delegar permissoes, aplicar GPOs e tambem para organizacao

* Containers
     * É um objeto que fornece uma estrutura organizacional para o uso do ADDS, nao pode ser aplicadas GPOs.

## Physical components

* Domain controllers
    * É cada servidor que tem a role do active directore instalada e configurada
    * Armazena a base de dados do ADDS

* Data stores
    * Refere-se ao repositorio onde os dados do Active directory sao armazenados. Este repositorio é essencial para a operacao do ADDS.

* Global catalog servers
    * Ele que armazena todas as informacoes de tudo que existe de objetos dentro do AD

* RODCs
    * É um controlador de dominio somente leitura
