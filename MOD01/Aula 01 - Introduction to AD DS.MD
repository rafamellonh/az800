## ADDS

* É um service de diretorio utilisado para centralizar todas identidades dentro da infraestrutura de rede (user, passwords, pcs e etcs)

## Logical components

* Partitions
* Schema
* Domains
    * É uma unidade administrativa fundamental que organiza os recursos de uma rede, como users, computers, grupos e dispositivos de maneira logica e gerenciavel. 

* Domains trees
    * É uma estrutura hierarquica que consiste em um ou mais dominios que compartilham um namespace continuio.
    * example.com, rs.example.com e sp.example.com

* Forests
    * É a estrutura de mais alto nivel em uma implantacao do ADDS, é um agrupamento de uma ou mais arvores de dominios que compartilham um esquema comum

* Sites
    * Representa uma ou mais sub-redees fisicas, sao usados principalmente para gerenciar a replicacao de dados entre controladores de dominio e para otimizar
      a autenticacao e o trafego de rede em uma infra.
* OUs
* Containers

## Physical components

* Domain controllers
* Data stores
* Global catalog servers
* RODCs