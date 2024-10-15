# High-Level Design (HLD) - FitFlow

## 1. Introdução

O documento descreve o design de alto nível do sistema FitFlow, uma aplicação para gerenciamento de treinos, que permite a interação entre Personal Trainers, Alunos e Auto Treinadores.

## 2. Arquitetura do Sistema

### Diagrama de Arquitetura
*(Incluir o diagrama que representa a arquitetura geral do sistema)*

### Componentes Principais
- **Front-End**: Interface do usuário desenvolvida em Angular.
- **Back-End**: API RESTful desenvolvida em Spring Boot.
- **Banco de Dados**: PostgreSQL executado em um container Docker para armazenamento de dados.
- **Autenticação**: JWT (JSON Web Tokens) para gerenciamento de autenticação e autorização de usuários.

## 3. Funcionalidades Principais

- **Cadastro de Usuário**: Permite que novos usuários se registrem no sistema.
- **Login de Usuário**: Autenticação de usuários registrados através de tokens JWT.
- **Gerenciamento de Treinos**: Funcionalidade para Personal Trainers criarem e gerenciarem fichas de treino para seus alunos.
- **Visualização de Treinos**: Alunos podem visualizar e preencher dados de suas fichas de treino.

## 4. Fluxos de Trabalho

### Fluxo de Cadastro
1. Usuário seleciona o tipo (Personal Trainer, Aluno, Auto Treinador).
2. Usuário preenche o formulário de cadastro.
3. Sistema registra o usuário e cria a conta.

### Fluxo de Login
1. Usuário fornece credenciais.
2. Sistema verifica as credenciais e autentica o usuário gerando um token JWT.
3. Redireciona para a página principal.


## 5. Tecnologias e Ferramentas

- **Back-End**: Spring Boot, Java
- **Front-End**: Angular, TypeScript
- **Banco de Dados**: PostgreSQL em Docker
- **Autenticação**: JWT (JSON Web Tokens)
- **Ferramentas**: Docker para containerização, Git para versionamento de código.

## 6. Considerações Finais

Este documento apresenta uma visão geral do design do sistema FitFlow.
