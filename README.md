# 🐾 VetPatas - Sistema de Gerenciamento de Clínica Veterinária

Este repositório contém o **Projeto Completo de Banco de Dados** desenvolvido para a disciplina de Modelagem de Banco de Dados. O projeto simula um sistema real para a clínica veterinária fictícia **VetPatas**, abrangendo desde a concepção do cenário até a implementação física e relatórios estratégicos.

---

## 1. 🏢 Cenário

A **VetPatas** é uma clínica veterinária em expansão que necessita informatizar seus processos de atendimento. Atualmente, o controle é feito manualmente, o que gera erros e lentidão.

**Objetivo do Sistema:**
Gerenciar o cadastro de clientes e seus animais, manter um histórico médico único (prontuário) para cada animal, registrar agendamentos de consultas e controlar os medicamentos prescritos.

**Regras de Negócio Identificadas:**
* **Cliente:** Pode possuir vários animais, endereços e telefones.
* **Animal:** Pertence a um único dono e possui um único prontuário médico exclusivo.
* **Consulta:** Um animal pode passar por várias consultas ao longo da vida.
* **Medicamento:** Uma consulta pode resultar na prescrição de vários medicamentos.

---

## 2. 📐 Modelagem Conceitual (DER)

O Diagrama Entidade-Relacionamento (DER) foi criado para representar graficamente as entidades e seus relacionamentos, seguindo o modelo de Peter Chen.

**Entidades Principais:**
* `CLIENTE`
* `ANIMAL`
* `PRONTUÁRIO`
* `CONSULTA`
* `MEDICAMENTO`

![Diagrama Conceitual](DER.drawio.png)

---

## 3. 🧮 Modelagem Lógica

Nesta etapa, o modelo conceitual foi traduzido para o modelo relacional (tabelas), com a definição de chaves primárias (PK) e estrangeiras (FK) e a normalização dos dados.

**Principais Decisões de Projeto:**
* O atributo multivalorado **Telefone** foi transformado na tabela `TELEFONES`.
* O atributo composto **Endereço** foi normalizado na tabela `ENDERECO`.
* A relação N:N entre Consulta e Medicamento foi implementada, neste escopo, associando o medicamento à consulta realizada.

![Modelo Lógico](modelo_logico_relacional.drawio.png)

---

## 4. 🧱 Modelagem Física (SQL)

O banco de dados foi implementado utilizando a linguagem **SQL** no SGBD **MySQL**.

* **Script de Criação Completo:** [script_completo_clinica.sql](script_completo_clinica.sql)

**Estrutura das Tabelas:**
```sql
CREATE TABLE CLIENTE (...);
CREATE TABLE ENDERECO (...);
CREATE TABLE TELEFONES (...);
CREATE TABLE ANIMAL (...);
CREATE TABLE PRONTUARIO (...);
CREATE TABLE CONSULTA (...);
CREATE TABLE MEDICAMENTO (...);
