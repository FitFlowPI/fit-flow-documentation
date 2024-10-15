# User Stories BDD - FitFlow

# Features

1. [Cadastro de Usuário](#cadastro-de-usuário)
   - [Cadastro bem-sucedido de um Personal Trainer](#cenário-cadastro-bem-sucedido-de-um-personal-trainer)
   - [Cadastro com um email já existente](#cenário-cadastro-com-um-email-já-existente)
   - [Cadastro de Auto Treinador com dados inválidos](#cenário-cadastro-de-auto-treinador-com-dados-inválidos)
2. [Login de Usuário](#login-de-usuário)
   - [Login bem-sucedido](#cenário-login-bem-sucedido)
   - [Falha de login por senha incorreta](#cenário-falha-de-login-por-senha-incorreta)
   - [Falha de login por conta inexistente](#cenário-falha-de-login-por-conta-inexistente)

---

## Cadastro de Usuário

### Feature: Cadastro de Usuário

Para acessar o sistema e usufruir dos serviços, um novo usuário deve ser capaz de se cadastrar com sucesso.

#### Cenário: Cadastro bem-sucedido de um Personal Trainer

- **Dado** que estou na página de cadastro  
- **E** escolho "Personal Trainer" como o tipo de usuário  
- **E** preencho os campos de nome, email, senha e outros dados obrigatórios  
- **Quando** envio o formulário de cadastro  
- **Então** uma nova conta deve ser criada no banco de dados na tabela `users`  
- **E** o campo `user_type` deve ser registrado como 'personal_trainer'  
- **E** o campo `active_plan` deve ser "false"  
- **E** devo receber uma confirmação do cadastro bem-sucedido.

#### Cenário: Cadastro com um email já existente

- **Dado** que estou na página de cadastro  
- **E** uso um email que já está registrado no sistema  
- **Quando** tento enviar o formulário de cadastro  
- **Então** devo ver uma mensagem de erro dizendo que o email já está em uso  
- **E** o sistema deve evitar a criação de uma nova conta.

#### Cenário: Cadastro com dados inválidos

- **Dado** que estou na página de cadastro  
- **E** escolho o tipo de usuário  
- **E** deixo de preencher campos obrigatórios como o email ou a senha  
- **Quando** tento enviar o formulário de cadastro  
- **Então** devo receber uma mensagem de erro indicando que os campos obrigatórios estão faltando  
- **E** o cadastro não deve ser processado até que todos os dados obrigatórios sejam preenchidos corretamente.

---

## Login de Usuário

### Feature: Login de Usuário

Usuários registrados devem ser capazes de fazer login no sistema para acessar suas informações.

#### Cenário: Login bem-sucedido

- **Dado** que sou um usuário registrado no sistema  
- **E** preencho meu email e senha corretamente  
- **Quando** envio o formulário de login  
- **Então** devo ser autenticado com sucesso  
- **E** o sistema deve me redirecionar para a página principal do meu perfil.

#### Cenário: Falha de login por senha incorreta

- **Dado** que sou um usuário registrado  
- **E** preencho meu email corretamente  
- **E** preencho uma senha incorreta  
- **Quando** tento fazer login  
- **Então** o sistema deve me mostrar uma mensagem de erro dizendo que email e/ou senha estão incorretos
- **E** o acesso ao sistema deve ser negado.

#### Cenário: Falha de login por conta inexistente

- **Dado** que estou tentando fazer login no sistema  
- **E** uso um email que não está registrado no banco de dados  
- **Quando** tento fazer login  
- **Então** o sistema deve me mostrar uma mensagem de erro dizendo que email e/ou senha estão incorretos  
- **E** o login não deve ser autorizado.