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


## Passo 5: Configurando CI/CD no GitLab (Opcional)

O GitLab oferece integração contínua (CI) e entrega contínua (CD) para automatizar a construção, os testes e a implantação do seu projeto. Para configurar o CI/CD, siga os passos abaixo:

1. **Criar o arquivo `.gitlab-ci.yml`**

   No seu repositório no GitLab, crie um arquivo chamado `.gitlab-ci.yml` na raiz do seu projeto. Esse arquivo vai definir o pipeline de CI/CD. O GitLab vai automaticamente procurar por esse arquivo e executar as etapas definidas nele.

2. **Configurar o conteúdo do `.gitlab-ci.yml`**

   O conteúdo do arquivo `.gitlab-ci.yml` pode ser algo simples como o exemplo abaixo:

   ```yaml
   stages:
     - build
     - test
     - deploy

   build:
     script:
       - echo "Construindo o projeto..."

   test:
     script:
       - echo "Executando testes..."

   deploy:
     script:
       - echo "Implantando o projeto..."


## Passo 6: Monitorando o Status do Projeto

Após enviar suas alterações e configurar a integração contínua, você pode monitorar o status do seu projeto diretamente no GitLab. Aqui estão algumas funcionalidades que você pode usar para monitorar o progresso e a saúde do seu repositório:

1. **Pipelines**

   O GitLab oferece uma interface visual para acompanhar o status dos pipelines, que são responsáveis por automatizar as etapas de construção, teste e deploy do seu projeto. Para verificar o status de execução do pipeline, siga os passos abaixo:
   
   - No seu repositório, clique em **CI/CD** no menu lateral.
   - Em seguida, clique em **Pipelines**.
   - Lá você verá uma lista de todos os pipelines executados, com seu status atual (passando, falhando ou aguardando).

   Você pode visualizar detalhes sobre cada pipeline, incluindo quais estágios foram concluídos com sucesso ou falharam. Se algum estágio falhar, o GitLab fornecerá logs detalhados para ajudar na depuração do problema.

2. **Issues**

   O GitLab permite o gerenciamento de tarefas, bugs e funcionalidades a serem implementadas através de **Issues**. Para acompanhar os problemas e progresso do seu projeto, você pode usar a seção de issues para criar novas tarefas e acompanhar as existentes.

   - Para visualizar ou criar novas issues, vá até a seção **Issues** no seu repositório.
   - Você pode criar uma nova issue clicando em **New Issue** e fornecendo detalhes sobre o que precisa ser resolvido ou implementado.
   - É possível atribuir as issues a diferentes membros da equipe e adicionar etiquetas para facilitar o gerenciamento.

   As issues são úteis para organizar o trabalho e garantir que todas as tarefas sejam realizadas de forma eficiente.

3. **Merge Requests**

   Quando você estiver pronto para integrar suas mudanças em uma branch principal (geralmente chamada de `master` ou `main`), o GitLab permite que você crie um **Merge Request**. Isso ajuda a revisar o código antes de mesclá-lo, promovendo a colaboração e garantindo que o código esteja em conformidade com os padrões da equipe.

   - Para criar um novo merge request, vá até a seção **Merge Requests** no seu repositório.
   - Clique em **New Merge Request** e selecione a branch que deseja mesclar com a branch principal.
   - O GitLab irá gerar um formulário de merge request onde você pode adicionar uma descrição e atribuir revisores para revisar as alterações.

   Durante o processo de merge request, o GitLab executa automaticamente os pipelines definidos no arquivo `.gitlab-ci.yml`, garantindo que o código passe por todas as etapas de construção, testes e deploy antes de ser integrado à branch principal.

4. **Monitoramento de Deploys**

   Se você configurou etapas de deploy no seu pipeline de CI/CD, o GitLab também permite monitorar o status de deploys. Para isso, você pode configurar integrações com diferentes plataformas de deploy (como Kubernetes, AWS, Google Cloud, etc.) para garantir que a aplicação seja implantada corretamente.

   - Dentro do painel de CI/CD, você pode visualizar o status dos deploys em tempo real.
   - Além disso, se algum deploy falhar, o GitLab vai gerar logs que podem ser usados para diagnosticar o problema.

5. **Notificações**

   O GitLab oferece a opção de configurar notificações para que você seja alertado sobre alterações no status do projeto, como falhas de pipeline, novos merge requests ou atualizações de issues. Você pode personalizar as notificações para receber apenas as informações relevantes para você.

   Para configurar as notificações, vá até **Configurações** no GitLab, depois **Notificações** e escolha a frequência e os tipos de eventos que você quer ser notificado.

Com essas ferramentas, você pode monitorar de forma eficaz o status do seu projeto e tomar ações rápidas caso algum problema seja identificado.


## Passo 7: Trabalhando com Branches

O GitLab, assim como o Git, permite o uso de **branches** para gerenciar diferentes versões do seu código. Isso é útil quando você quer adicionar novas funcionalidades, corrigir bugs ou testar algo sem afetar a branch principal do projeto (geralmente chamada de `master` ou `main`). Aqui está como você pode trabalhar com branches no GitLab:

1. **Criar uma nova branch**

   Para começar a trabalhar em uma nova funcionalidade ou correção de bug, você precisa criar uma nova branch. Isso pode ser feito diretamente no terminal ou através da interface do GitLab.

   - Para criar uma nova branch localmente, abra seu terminal e execute o seguinte comando:
     ```bash
     git checkout -b nome-da-sua-branch
     ```
     Isso cria uma nova branch chamada `nome-da-sua-branch` e automaticamente troca para ela.

   - Se você estiver usando o GitLab diretamente na interface web, pode navegar até o seu repositório e clicar na opção para **Criar Nova Branch**.

2. **Fazer alterações e commit na nova branch**

   Após criar a branch, faça as alterações necessárias no código. Isso pode incluir adicionar novos arquivos, corrigir bugs ou implementar novas funcionalidades.

   - Adicione as mudanças ao Git:
     ```bash
     git add .
     ```

   - Em seguida, faça o commit das suas alterações:
     ```bash
     git commit -m "Descrição das alterações feitas na branch"
     ```
     A descrição do commit deve ser clara e descritiva sobre o que foi feito.

3. **Enviar a branch para o repositório remoto**

   Depois de realizar o commit, você precisa enviar sua branch para o repositório remoto no GitLab. Para isso, use o comando:
   ```bash
   git push origin nome-da-sua-branch



