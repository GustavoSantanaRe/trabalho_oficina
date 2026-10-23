# 🔧 Oficina Mecânica — SAEP/SENAI

Sistema web para gerenciamento de uma oficina mecânica, desenvolvido como projeto educacional para o SAEP/SENAI. A aplicação permite organizar clientes, veículos e agendamentos de serviços, utilizando Python, Flask e MySQL.

## 📌 Sobre o Projeto

O **Oficina Mecânica** tem como objetivo facilitar a administração das atividades de uma oficina, centralizando informações de clientes, seus veículos e os serviços agendados em uma única plataforma.

O sistema possui autenticação de usuários, operações de cadastro, consulta, edição e exclusão de registros, além de recursos de segurança para proteger o acesso à aplicação.

## 🚀 Funcionalidades

- 🔐 **Autenticação de usuários:** login com validação de credenciais e encerramento de sessão.
- 👥 **Gerenciamento de clientes:** cadastro, pesquisa, edição e exclusão de clientes.
- 🚗 **Gerenciamento de veículos:** cadastro e edição de veículos vinculados obrigatoriamente a clientes.
- 📅 **Agendamento de serviços:** criação, consulta, alteração de data e exclusão de agendamentos.
- 📊 **Dashboard:** visualização do total de clientes, veículos e agendamentos, além dos próximos serviços.
- 🔒 **Segurança:** utilização de hashes Bcrypt para senhas e implementação de mecanismos de proteção de dados.
- ⏱️ **Controle de sessão:** configuração de expiração de sessão após 15 minutos.
- 🔎 **Pesquisa de clientes:** busca por nome, CPF, e-mail ou telefone.

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem principal do sistema |
| Flask | Desenvolvimento da aplicação web e gerenciamento de rotas |
| MySQL | Armazenamento e gerenciamento dos dados |
| Bcrypt | Geração e verificação de hashes |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização das interfaces |
| JavaScript | Interações e controle de modais |
| Werkzeug | Utilitários utilizados pelo Flask |

## 📂 Estrutura do Projeto

```text
oficina_mecanica/
│
├── saep_db.sql
│
└── sistema/
    ├── app.py
    ├── banco.py
    ├── autenticacao.py
    ├── clientes.py
    ├── veiculos.py
    ├── agendamento.py
    ├── rotas.py
    ├── requirements.txt
    │
    ├── templates/
    │   ├── base.html
    │   ├── login.html
    │   ├── dashboard.html
    │   ├── clientes.html
    │   ├── veiculos.html
    │   └── agendamentos.html
    │
    └── static/
        ├── css/
        │   └── style.css
        │
        └── js/
            └── main.js
```

## ⚙️ Como Executar o Projeto

### 1. Pré-requisitos

Antes de começar, instale:

- Python 3.
- MySQL Server.
- MySQL Workbench ou outro cliente MySQL.
- Git, caso queira clonar o repositório.

### 2. Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
cd oficina_mecanica
```

Substitua `URL_DO_REPOSITORIO` pelo endereço real do seu repositório no GitHub.

### 3. Criar o ambiente virtual

Na pasta raiz do projeto, execute:

```bash
python -m venv venv
```

Ative o ambiente virtual no Windows:

```bash
venv\Scripts\activate
```

No Linux ou macOS:

```bash
source venv/bin/activate
```

### 4. Instalar as dependências

Execute:

```bash
pip install -r sistema/requirements.txt
```

### 5. Configurar o banco de dados

Certifique-se de que o servidor MySQL esteja em execução.

Na pasta raiz do projeto, execute:

```bash
mysql -u root -p < saep_db.sql
```

Digite a senha do MySQL quando solicitado.

Esse script cria o banco de dados `saep_db`, as tabelas necessárias e registros de exemplo.

**Importante:** o script SQL contém comandos `DROP TABLE IF EXISTS`, que excluem as tabelas existentes antes de recriá-las. Faça backup dos dados antes de executá-lo novamente.

### 6. Configurar a conexão com o MySQL

O arquivo `sistema/banco.py` utiliza variáveis de ambiente para configurar a conexão.

As variáveis disponíveis são:

```text
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=saep_db
DB_PORT=3306
```

Configure-as de acordo com seu ambiente. Se utilizar variáveis de ambiente, defina-as no terminal antes de iniciar a aplicação.

### 7. Testar a conexão com o banco

Execute:

```bash
python sistema/banco.py
```

Se a conexão estiver configurada corretamente, o terminal deverá informar que a conexão foi estabelecida e mostrar as tabelas encontradas.

### 8. Iniciar a aplicação

Execute:

```bash
python sistema/app.py
```

Em seguida, abra o navegador no endereço:

http://127.0.0.1:5000

## 🔑 Acesso ao Sistema

O projeto contém usuários de teste cadastrados no banco de dados.

| Usuário | Senha |
|---|---|
| `admin` | `admin123` |
| `mecanico` | `senha123` |
| `recepcao` | `rec123` |

Essas credenciais são destinadas exclusivamente ao ambiente de demonstração. Altere-as antes de qualquer utilização em produção.

## 🗄️ Banco de Dados

O banco `saep_db` utiliza MySQL e contém quatro tabelas principais:

- **usuarios:** armazena os dados dos funcionários e suas credenciais.
- **clientes:** registra informações de contato e cadastro dos clientes.
- **veiculos:** armazena os dados dos veículos e seus respectivos proprietários.
- **agendamentos:** registra datas, serviços, valores estimados, observações e status dos atendimentos.

As relações entre as tabelas permitem associar veículos aos clientes e agendamentos aos clientes e veículos correspondentes.

## 🧪 Testes e Validação

Para validar o funcionamento do sistema, recomenda-se testar:

- [ ] Login com credenciais válidas.
- [ ] Bloqueio de acesso com senha incorreta.
- [ ] Exibição dos dados do usuário autenticado.
- [ ] Cadastro e pesquisa de clientes.
- [ ] Validação do CPF com exatamente 11 dígitos.
- [ ] Edição e exclusão de clientes.
- [ ] Cadastro de veículos vinculados a clientes existentes.
- [ ] Edição e exclusão de veículos.
- [ ] Cadastro e consulta de agendamentos.
- [ ] Ordenação dos serviços por data.
- [ ] Atualização da data e horário de um agendamento.
- [ ] Encerramento da sessão pelo botão de saída.

## 🎯 Objetivo Educacional

Este projeto tem como finalidade aplicar conhecimentos de desenvolvimento web, programação em Python, integração com banco de dados relacionais, autenticação de usuários e organização de código em módulos.

O desenvolvimento também permite praticar operações CRUD (Create, Read, Update e Delete), relacionamentos entre tabelas e validação de regras de negócio.

## 👨‍💻 Desenvolvido no SENAI

Projeto educacional desenvolvido no contexto do SAEP/SENAI, com foco na criação de uma solução para gerenciamento de oficinas mecânicas.

---

**Tecnologias:** Python • Flask • MySQL • Bcrypt • HTML5 • CSS3 • JavaScript

**Projeto:** Sistema de Gerenciamento de Oficina Mecânica
