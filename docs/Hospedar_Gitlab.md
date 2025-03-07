# Como Funciona o Processo de Hospedagem de Código no GitLab

O GitLab é uma plataforma de DevOps que permite hospedar, gerenciar e versionar seu código. Além disso, oferece diversas funcionalidades para facilitar o gerenciamento de projetos, integração contínua (CI), entrega contínua (CD), e muito mais. Neste guia, vamos explicar como hospedar seu código no GitLab, desde a criação de um repositório até a integração com o GitLab CI/CD.

## Passo 1: Criando uma Conta no GitLab

Antes de tudo, você precisa ter uma conta no GitLab. Siga os passos abaixo para criar sua conta:

1. Acesse o site oficial do GitLab: [https://gitlab.com](https://gitlab.com).
2. Clique em **Sign Up** (Cadastrar-se) no canto superior direito.
3. Preencha o formulário com seu e-mail, nome de usuário e senha, ou faça login usando uma conta do Google ou GitHub.
4. Após criar sua conta, você será redirecionado para o painel principal do GitLab.

## Passo 2: Criando um Novo Repositório (Projeto) no GitLab

Para hospedar seu código, você precisa criar um novo repositório (também chamado de "Projeto" no GitLab). Siga os passos abaixo:

1. No painel principal, clique em **New Project** (Novo Projeto).
2. Escolha entre:
   - **Create Blank Project**: Crie um projeto vazio.
   - **Import Project**: Importe um repositório existente de outra plataforma (como GitHub, Bitbucket).
   - **Create from Template**: Crie um projeto a partir de um template.
3. Preencha as informações do projeto, como:
   - **Project Name** (Nome do Projeto).
   - **Visibility Level** (Nível de Visibilidade): Escolha se o projeto será público ou privado.
   - **Description** (Descrição): Adicione uma breve descrição do seu projeto (opcional).
4. Após preencher as informações, clique em **Create project** (Criar projeto).

Agora você tem um repositório no GitLab para hospedar seu código.

## Passo 3: Clonando o Repositório para o Seu Computador

Para começar a trabalhar com o código localmente, você precisa clonar o repositório criado para o seu computador. Para fazer isso:

1. No repositório do GitLab, clique no botão **Clone**.
2. Você verá duas opções para clonar:
   - **Clone with HTTPS**: Use o comando `git clone` com o URL HTTPS.
   - **Clone with SSH**: Use o comando `git clone` com o URL SSH (requer configuração de chave SSH).
   
   Se você ainda não configurou sua chave SSH, é recomendado usar o método **HTTPS**.
   
   Exemplo de comando para clonar com HTTPS:
   ```bash
   git clone https://gitlab.com/seunome/seuprojeto.git

   ## Passo 4: Adicionando e Commitando Arquivos no Repositório

Após clonar o repositório, você pode começar a trabalhar no código e adicionar arquivos. Para enviar essas alterações para o repositório GitLab, siga os passos abaixo:

1. **Adicionar arquivos**: Crie ou edite arquivos no seu diretório local.

2. **Adicionar os arquivos ao Git**:
   Use o comando `git add` para adicionar os arquivos que foram modificados ao índice para o commit.
   ```bash
   git add .

