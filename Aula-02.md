# Aula 02 - Banco de Dados / Ana Claudia



# **Como projetar um banco de dados?**


## **Arquitetura de Três Esquemas ou ANSI SPARC**
Modelo que podemos descrever um banco entre 3 níveis de abstração.

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/YY6ZY6YyTlHZg45-F2f7V.png?ixlib=js-3.7.0 "image.png")



Esses três níveis são:

### Nível Externo (nível de visão ): 
-> Descrevem visões, ou views (como os usuários vêem os dados) – parte dos dados de interesse do usuário

Exemplo:

-> Visão externa para um usuário incluir nome, matricula, endereço, curso.

### Nível Conceitual (nível lógico): 
-> Descrevem a estrutura lógica dos dados – descrição das entidades, tipos de dados, conexões, operações e restrições.

Exemplo:

-> Representação conceitual das entidades do banco. Como por exemplo a entidade `Aluno` (com atributos como Matricula: integer, Nome_Aluno: string, Endereço: string), `Curso` (com Sigla_Curso: string, Nome_Curso: string) e `Matriculado` (com Matricula: string, Sigla_Curso: string, Data: date), mostrando seus relacionamentos.

### Nível Interno (nível físico) 
-> Descreve detalhes do armazenamento físico do banco de dados

Exemplo:

-> No nível interno, isso se traduz em comandos como `﻿CREATE TABLE` para definir as tabelas e seus campos, e `CREATE INDEX` para otimização de busca, como `CREATE TABLE Aluno (Matricula: integer, Nome_Aluno: string, Endereço: string); CREATE INDEX Idx_Matricula ON Aluno(Matricula);` 

### Mapamento:
São definidos entre esses esquemas para garantir a correspondência entre os diferentes níveis:

- O **mapeamento Externo → Conceitual** define a correspondência entre uma visão externa específica e a visão conceitual
- O **mapeamento Conceitual → Interno** define como a visão conceitual se corresponde com o banco de dados armazenado fisicamente e especifica como os registros e campos conceituais são representados no nível interno.
## **Independência de Dados**
A arquitetura de três esquemas proporciona a chamada **Independência de Dados**, que é a capacidade de alterar o esquema em um nível sem afetar os esquemas dos níveis superiores:

• **Independência de Dados Lógica**: Mudanças no esquema conceitual não afetam a visão do usuário (esquema externo).

• **Independência de Dados Física**: Mudanças no esquema interno não implicam em mudanças nos esquemas conceitual e externo.



# **Projeto de Banco de Dados**
![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/xlHrtoz2zlV1qY9h87_pJ.png?ixlib=js-3.7.0 "image.png")



## **-> Minimundo: **
 Domínio do problema que precisa ser modelado no banco de dados

## **-> Levantamento e Análise de Requisitos:**
Identificar os requisitos de dados (quais informações precisam ser armazenadas) e os requisitos funcionais (como essas informações serão utilizadas).

## **-> Projeto Conceitual:**
Geralmente feito com Modelo Entidade-Relacionamento (MER) ou UML.

## **-> Análise Funcional:**
Define especificações de transações de alto nível (como as operações de cadastro, consulta, atualização, etc.).

## **-> Projeto Lógico:**
Transformar um modelo Entidade-Relacionamento em tabelas relacionais no caso de bancos SQL.

## **-> Projeto Físico:**
Ajuste do modelo lógico para o ambiente físico do banco (otimizações de performance, tipos de dados específicos, índices, particionamento, etc.).

## **-> Projeto do Programa de Aplicação:**
Desenvolvimento dos programas de aplicação que interagem com o banco.

Inclui formulários, relatórios e lógica de negócio que utilizam as transações.

## **-> Implementação da Transação:**
Criação e execução das transações (operações no banco).

## **Usuário Finais**
-> Interagem com o BD sem necessariamente programar ou escrever programas de consultas.

## **Programadores de Aplicações**:
-> São os responsáveis pela modelagem do banco atuando nos níveis conceituais e lógico. 

## **Administradores de Bancos de Dados (DBA)**:
-> Geralmente são analista de dados

-> Numa hierarquia, o mais experiente

-> Responsável pelo projeto do banco de dados



# **Arquiteturas para SGBDs**
## **Arquitetura Centralizada**
-> Processamento feito numa máquina central

## **Arquitetura Cliente / Servidor**
-> Arquitetura mais usada

-> Dividida em duas partes:** Backend (Server Side) **e **Frontend ( Client Side)**

## **Banco de Dados Distribuídos (BD Distribuído**
-> Nesta arquitetura, máquinas diferentes podem estar conectadas entre si em uma rede de comunicações

-> Uma única tarefa de processamento pode se estender a várias máquinas na rede



# -------------------SLIDE 02 ------------------------


# **Fundamentos de Banco de Dados**


## **Processo de Projeto de Banco de Dados**
O projeto de banco de dados envolve a estruturação das informações de forma organizada. Duas aplicações de exemplo são apresentadas para ilustrar esse processo: uma **Empresa** e uma **Universidade**

## Modelo Entidade-Relacionamento (MER)
O MER é um **modelo popular de alto nível** utilizado na **fase conceitual do projeto de banco de dados**. Ele não possui relação direta com um Sistema Gerenciador de Banco de Dados (SGBD) específico e descreve os dados usando três conceitos principais: **Entidades, Relacionamentos e Atributos**. Sua representação visual é feita através do **Diagrama de Entidade-Relacionamento (DER)**.



![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/A-6HUdutpXr39puYC_Wpv.png?ixlib=js-3.7.0 "image.png")



## **Entidades**
### **-> Definição: **
Uma entidade é uma representação abstrata de um objeto do mundo real que é de interesse para a aplicação

### **-> Exemplos:**
Uma empresa, um empregado, um professor, um aluno

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/8nhbrMpP5Rzi8iFTsSJ_I.png?ixlib=js-3.7.0 "image.png")



### **-> Instâncias:**
Conjunto de entidades

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/NLy8_MSNfJo8FMEhkvO6Z.png?ixlib=js-3.7.0 "image.png")



## **Atributos**
### **-> Definição:**
Atributos são as propriedades específicas que caracterizam uma entidade

### **-> Exemplos:**
Nome, salário, CPF são atributos de um empregado

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/ALM8bm0vrDyI0DYJY80x2.png?ixlib=js-3.7.0 "image.png")

### -> **Tipos de Atributos**:
- **Simples ou Compostos**: Atributos simples são atômicos (Ex: `nome` ), enquanto compostos podem ser divididos em sub-atributos (Ex: `endereço`  pode ter `logradouro` , `número` , `cidade` , `estado` )
- **Monovalorados ou Multivalorados**: Monovalorados têm um único valor (Ex: `sexo` ), enquanto multivalorados podem ter vários valores (Ex: `e-mail` )
- **Armazenados ou Derivados**: Atributos armazenados são diretamente guardados (Ex: `data de nascimento` ), enquanto derivados podem ser calculados a partir de outros atributos (Ex: `idade`  derivada da `data de nascimento` )
- **Valores Null**: Representam valores que não se aplicam ou são desconhecidos (Ex: número de apartamento para quem mora em casa, telefone residencial desconhecido)
### -> **Atributo Chave**: 
Um atributo (ou conjunto de atributos) com um **valor único para cada instância** do conjunto de entidades, permitindo a identificação exclusiva

Ex.: `número de matrícula` (aluno), `cpf` (imposto de renda). Uma chave pode ser **composta** por vários atributos

### ->  **Domínio de um Atributo**:
 Conjunto de **valores permitidos** que podem ser atribuídos a um atributo

Ex.: `idade` de um professor (entre 18 e 70 anos), `nome` (string), `estado civil` (casado, solteiro, divorciado)



![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/GRpP0_dYGTIBWrVfMZ-dK.png?ixlib=js-3.7.0 "image.png")



## **Relacionamentos**
### **-> Definição:**
Relacionamentos são associações entre duas ou mais entidades distintas (instâncias) que possuem um significado

### **-> Exemplos:**
 EMPREGADO trabalha para DEPARTAMENTO, EMPREGADO supervisiona outro EMPREGADO

![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/YcrA1v9o8DvmHKKlGU3UT.png?ixlib=js-3.7.0 "image.png")



## **Restrições sobre Relacionamentos**
### **-> Definição:**
Limitam as combinações possíveis de entidades que podem participar em um conjunto de relacionamentos

### **-> Cardinalidade:**
**Definição**: Representa o **número de instâncias** de um tipo de relacionamento em que uma entidade pode participar

**1:1 (Um para Um)**: Um empregado gerencia um departamento, e um departamento é gerenciado por apenas um empregado.

**N:1 (Muitos para Um)**: Vários empregados trabalham para um departamento, mas um empregado trabalha em apenas um departamento.

**M:N (Muitos para Muitos)**: Vários empregados trabalham em vários projetos, e um projeto tem vários empregados trabalhando.

### **-> Participação:**
**Definição**: Indica se uma entidade **obrigatoriamente participa** ou não de um tipo de relacionamento

- Tipos:
    - **Total**: A entidade deve participar do relacionamento (Ex: Todo departamento tem um gerente)
    - **Parcial**: A entidade pode ou não participar do relacionamento (Ex: Nem todo empregado é gerente)
- Notação:
    - **(0,1) ou 1**: Cardinalidade mínima 0 e máxima 1, participação parcial
    - **(1,1)**: Cardinalidade mínima 1 e máxima 1, participação total
    - **(0,N) ou N**: Cardinalidade mínima 0 e máxima N, participação parcial
    - **(1,N)**: Cardinalidade mínima 1 e máxima N, participação total
## **Conceitos Avançados de Relacionamento**
### **-> Grau do Relacionamento**:
O número de tipos de entidades que participam de um relacionamento.

- **Binário (Grau 2)**: Relacionamentos entre duas entidades (Ex: TRABALHA PARA)
- **Ternário (Grau 3)**: Relacionamentos entre três entidades (Ex: FORNECE)
### **-> Atributos do Relacionamento**:
Atributos que não pertencem a nenhuma das entidades individualmente, mas sim à relação entre elas.

Ex.: A quantidade de horas que um empregado trabalha em um projeto (`número de horas por semana que o empregado trabalha em cada projeto`).

### **-> Papéis do Relacionamento**:
Entidades atuam com um determinado papel em um relacionamento. O nome do papel é atribuído a cada tipo de entidade e é necessário quando o mesmo tipo de entidade participa mais de uma vez em um relacionamento, especialmente em relacionamentos recursivos

### **-> Relacionamentos Recursivos (Auto-Relacionamento)**:
Ocorre quando o **mesmo tipo de entidade participa mais de uma vez** em um tipo de relacionamento, mas com **funções diferentes**.

 **Exemplo**: Disciplinas podem possuir pré-requisitos, que também são disciplinas (Ex: LÓGICA é pré-requisito de BD). É crucial usar papéis para clarear o significado

## **Entidade Fraca**
### **-> Definição:**
Uma **Entidade Fraca** é um tipo de entidade que **não possui identidade própria** (não contém um atributo chave).

### **-> Identificação:**
Suas instâncias são identificadas através de um relacionamento com uma entidade de outro tipo, chamada de **dono ou identificador**, juntamente com os valores de alguns de seus atributos (chamados de **chave parcial**)

### **-> Exemplos:**
- **Avaliação de Professor (Universidade)**: Não possui chave própria; é identificada pela associação com o Professor e sua chave parcial `datahora` .
- **Dependente de Empregado (Empresa)**: Não possui chave própria; depende do empregado para ser identificado.
## **Diagrama de Entidade Relacionamento (DER)**
### **-> Definição:**
O DER é a **notação visual** utilizada para representar o Modelo Entidade-Relacionamento, incluindo entidades, atributos e relacionamentos com suas restrições. Exemplos são fornecidos para os cenários de EMPRESA e UNIVERSIDADE.

### **-> Exemplos:**
![image.png](https://eraser.imgix.net/workspaces/oYE5I7cfPO1g7Q3cLDme/ym79cQbRhygAJD0aQqMZ5cPNemE2/4iUOwzQh1r_SDYalo1rfd.png?ixlib=js-3.7.0 "image.png")





# **Exercício 01:**
## Entidades:
1. Médicos
2. Pacientes
3. Consultas
## Atributos:
### Médicos:
- crm
- nome
- especialidades
### Pacientes:
- cpf
- nome
- idade
- sexo
- endereço
- telefone
### Consultas:
- data_realização
- valor
## Identificadores:
### Médicos:
- crm
### Pacientes:
- cpf
### Consultas:
- data_realização
## Relacionamentos:
### Relacionamento Médico -> Consulta:
- O médico realiza várias consultas
- Uma consulta é realizada por um único paciente.
- Cardinalidade: **Médico (0,N)** -> **Consulta (1,1)**
    - 0 porque um médico pode não ter consultas.
    - N porque pode ter várias consultas.
### Relacionamento Paciente-> Consulta:
- Um Paciente realiza várias consultas.
- Uma Consulta é realizada por um único paciente.
Cardinalidade: **Paciente (1,N)** → **Consulta (1,1)**

- 1 porque para existir um paciente ele já deve ter feito pelo menos uma consulta.
- N porque pode ter várias consultas.
## Participações:
- Paciente participa obrigatoriamente de pelo menos uma consulta (participação total).
- Médico pode existir sem consulta (participação parcial).
- Consulta depende de Paciente e Médico (participação total de Consulta).
## Diagrama de Entidade-Relacionamento(DER):






