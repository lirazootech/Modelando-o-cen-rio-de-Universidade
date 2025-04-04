# Modelando o Cenário de Universidade

## 📋 **Descrição do Projeto**

Este projeto tem como objetivo modelar e implementar um sistema para gerenciar informações acadêmicas e administrativas em um cenário de universidade. A ideia é criar um banco de dados estruturado que organize alunos, cursos, disciplinas, professores, coordenações, provas e pré-requisitos, com relacionamentos claros entre essas entidades.

## 📐 **Estrutura Conceitual**

A modelagem segue os seguintes conceitos principais:

- **Aluno**: Representa os estudantes matriculados na universidade. Cada aluno pode estar matriculado em diversos cursos e participar de disciplinas.  
- **Curso**: Representa os cursos de graduação ou cursos extras disponíveis. Relaciona-se às disciplinas e é gerido por uma coordenação.  
- **Disciplina**: Representa as disciplinas oferecidas nos cursos. Pode ter pré-requisitos, ser compartilhada por diferentes cursos e é sempre ministrada por um único professor.  
- **Professor**: Representa os docentes da universidade que lecionam disciplinas. Está vinculado a uma coordenação específica.  
- **Coordenação**: Representa o núcleo acadêmico responsável por organizar cursos. Está associada a múltiplos cursos e professores.  
- **Prova**: Representa as avaliações realizadas pelos alunos em cada disciplina. Inclui dois tipos: prova e trabalho.  
- **Pré-requisitos**: Representa a relação de dependência entre disciplinas, indicando que uma disciplina precisa ser concluída antes de outra.  

## 🛠️ **Entidades e Relacionamentos**

**Entidades**

- **Aluno**: Contém informações como nome, matrícula, data de nascimento e cursos vinculados.  
- **Curso**: Inclui nome, código, carga horária e relação com coordenação, disciplinas e alunos.  
- **Disciplina**: Registra dados como nome, código, carga horária e relação com curso e professor.  
- **Professor**: Armazena informações como nome, área de atuação e disciplinas ministradas.  
- **Coordenação**: Registra dados sobre o núcleo responsável pela gestão de cursos e docentes.  
- **Prova**: Contém informações sobre tipo, nota, data e a disciplina relacionada.  
- **Pré-requisitos**: Relaciona disciplinas de forma que uma só possa ser cursada após a conclusão de outra.  

## **Relacionamentos**

- **Curso** está vinculado a múltiplas **Disciplinas** (1:N).  
- **Aluno** pode estar matriculado em vários **Cursos** (N:M).  
- **Disciplina** pode ter vários **Pré-requisitos** (1:N).  
- **Pré-requisitos** associam duas **Disciplinas**: uma como pré-requisito e outra como disciplina principal (N:1).  
- **Disciplina** é ministrada por um único **Professor** (N:1).  
- **Professor** está vinculado a uma única **Coordenação** (N:1).  
- **Coordenação** organiza vários **Cursos** (1:N).  
- **Aluno** realiza várias **Provas** em cada **Disciplina** (N:M).  

## 📄 **Comandos Importantes**

Exemplo de comandos SQL que definem esse relacionamento:  

```sql
CREATE TABLE PreRequisito (
    ID_pre_requisito INT NOT NULL AUTO_INCREMENT,
    ID_disciplina_principal INT NOT NULL,
    ID_disciplina_pre_requisito INT NOT NULL,
    PRIMARY KEY (ID_pre_requisito),
    FOREIGN KEY (ID_disciplina_principal) REFERENCES Disciplina(ID_disciplina),
    FOREIGN KEY (ID_disciplina_pre_requisito) REFERENCES Disciplina(ID_disciplina)
);
```
## 📦 **Tecnologias Utilizadas**

- **MySQL**: Banco de dados relacional para criação e gerenciamento das tabelas.  
- **Workbench**: Ferramenta para modelagem e execução de comandos SQL.  

## 💡 **Arquitetura do Banco de Dados**

As tabelas apresentam características como:  
- Chaves primárias auto incrementadas.  
- Chaves estrangeiras para assegurar integridade referencial.  
- Dados otimizados com tipos adequados (VARCHAR, INT, DATE, etc.).  
- Estrutura flexível para expansões futuras.  

## 🌟 **Contribuições**

Sugestões são bem-vindas! Ficaremos felizes em incorporar melhorias ao projeto.

  
  
  <p align="center">
  Copyright © 2024. Desenvolvido com 🧡 por <a  href="https://lirazootech.vercel.app/">Thays Lira</a>.
  </p>
