# Aula 01 - Banco de dados / Ana Claudia

Email: acbloureiro@ufg.br

# **Introdução à Teoria de Banco de Dados**
## O que é? 
É uma coleção organizada de dados que tem uma relação

### **Dados**
Qualquer símbolo que não necessariamente tem algum significado

Ex.: Números: 09, 11, 17, 21

### **Informação**
Dados que tem alguma semântica ou uma estruturação

Ex.: Dias do mês de maio que choveu na cidade do Rio de Janeiro"

### **Conhecimento**
A informação é processada e transformada, em experiẽncia pelo indivíduo, isso é conhecimento

Ex.: Conectando os dados de vários anos podemos ter a frequência das chuvas no mês de maio no Rio de Janeiro.

# Hierarquia dos sistemas de informação dentro de uma organização
![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/j6Zbzr5cGiuZdjAM57Jb5.png?ixlib=js-3.7.0 "image.png")



# **Tipos de Armazenamento/Persistência de Dados**
## **-> Arquivos**
Desvantagens:

- Redundância
- Inconsistência
- Dificuldade de Acesso
- Falta de Segurança
## **-> Bancos de Dados**
Estruturado com uma coleção de arquivos relacionados entre si

São a solução para as desvantagens do armazenamento com arquivos

# **Modelos de Dados em Bancos de Dados**
## Conceito:
Um Banco de Dados é representado por um **Modelo de Dados**, que é um conjunto de conceitos para descrever sua estrutura (nomes, tipos, relacionamentos, restrições).

**obs.:**

- Representa aspectos do mundo real (mini mundo ou universo de discurso) 
- É uma coleção de dados logicamente coerentes com algum significado inerente
- É projetado, construído e instanciado (“povoado”) para uma aplicação específica.
Está intrinsecamente aos **REQUISITOS **onde se faz necessário levantar os requisitos de dados ao iniciar o desenvolvimento de software.

## **Principais Modelos de Banco de Dados:**
### -> **Banco de Dados Hierárquico:**
- Organiza dados em uma **estrutura do tipo árvore**, com cada registro tendo um único "pai
### -> **Banco de Dados de Rede:**
- Baseia-se no modelo hierárquico, mas permite **relações muitos para muitos** (vários pais para um filho)
### -> **Banco de Dados Orientado a Objetos:**
- As informações são armazenadas de maneira semelhante a um **objeto**, com recursos e métodos associados
### -> **Banco de Dados Relacional:**
- Utiliza um conjunto de **Tabelas** que representam os dados e seus relacionamentos
- Ex.: PostgreSQL
### -> **Banco de Dados Não Relacional ou NoSQL:**
- Utilizam uma variedade de formatos como **documentos, grafos, colunas largas, chave-valor**
- Ex.: MongoDB
## **Modelo X Implementação:**
**-> Modelo**: ** **Abstrato

**-> Implementação: ** Representação física na máquina

## **Outros Conceitos:**
**-> Esquema: **Representação do modelo

**->Instância: **Estado do BD (O banco populado)

# **Sistema Gerenciador de Banco de Dados (SGBD)**
## Conceito
Um SGBD é um **conjunto de programas** que permite aos usuários criar e manter um banco de dados

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/eSjH_Htsb3YxpHuAGCq1v.png?ixlib=js-3.7.0 "image.png")

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/WKfowwl6V-THjuux2-VZ3.png?ixlib=js-3.7.0 "image.png")



## Exemplos:
MySQL, PostgreSQL, Oracle, MongoDB, SQL Server, SQLite

## **Principais Funções de um SGBD:**
### **1. Definição de Dados:**
-> Deve possuir um processor e compilador **DDL**

-> Criar tabela, coluna...

`﻿``CREATE TABLE PESSOA (CPF int 11 NOT NULL, Nome VARCHAR(100));` 

### **2. Manipulação de Dados:**
->  Possui um processador e compilador **DML**

`﻿``SELECT * FROM FUNCIONARIO WHERE SALARIO >= 1000;` 

### **3. Controle de Dados:**
-> Possui um processador e compilador **DCL**

`﻿``GRANT SELECT ON FUNCIONARIO TO JOSE;` 

### **4. Otimização e Execução de Consultas:**
-> Um componente **OTIMIZADOR** processa requisições DML para determinar um modo eficiente de execução

### **5. Garantia de Segurança e Integridade dos Dados:**
-> Monitora requisições, rejeita tentativas de violar restrições e controla acessos

### **6. Recuperação de Dados e Concorrência**
-> Gerencia **Backup e Restauração**, e controla o acesso **concorrente** de múltiplos usuários (gerenciador de transações)

### **7. Dicionário de Dados:**
-> Contém **metadados** (dados sobre os dados), como definições de objetos, restrições de segurança e integridade. É um banco de dados de sistema.

### **8. Desempenho:**
-> Garante que as funções sejam realizadas da forma mais **eficiente** possível



------------------------------ Próxima Aula ---------------------------------



 



 




