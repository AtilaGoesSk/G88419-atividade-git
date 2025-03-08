# Git Handbook

## Introdução ao Git
Git é um sistema de controle de versão distribuído que permite o rastreamento de alterações no código-fonte durante o desenvolvimento de software.

## Instalação
Para instalar o Git, siga as instruções conforme o seu sistema operacional:

**Windows**: Baixe e instale o [Git para Windows](https://git-scm.com/downloads)

**Linux** (Debian/Ubuntu):
 ```sh
 sudo apt update && sudo apt install git
  ```
**macOS**:
  ```sh
  brew install git
  ```
## Configuração Inicial
Após a instalação, configure seu nome e e-mail:
```sh
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```

## Comandos Básicos

### Inicializar um repositório
```sh
git init
```

### Clonar um repositório
```sh
git clone <url-do-repositorio>
```

### Verificar status do repositório
```sh
git status
```

### Adicionar arquivos para commit
```sh
git add <arquivo>
```

### Criar um commit
```sh
git commit -m "Mensagem do commit"
```

### Enviar alterações para o repositório remoto
```sh
git push origin <branch>
```

### Atualizar o repositório local com mudanças remotas
```sh
git pull origin <branch>
```

## Branches
### Criar uma nova branch
```sh
git branch <nome-da-branch>
```

### Trocar para outra branch
```sh
git checkout <nome-da-branch>
```

### Criar e trocar para uma nova branch
```sh
git checkout -b <nome-da-branch>
```

### Mesclar uma branch na branch atual
```sh
git merge <nome-da-branch>
```

## Trabalhando com Repositórios Remotos
### Adicionar um repositório remoto
```sh
git remote add origin <url-do-repositorio>
```

### Verificar os repositórios remotos configurados
```sh
git remote -v
```

### Buscar mudanças remotas sem mesclar
```sh
git fetch origin
```

## Resolvendo Conflitos
Quando ocorre um conflito ao tentar mesclar branches, o Git irá solicitar que você resolva o problema manualmente. Após resolver o conflito nos arquivos:

```sh
git add <arquivo-resolvido>
git commit -m "Resolvendo conflito"
```

## Boas Práticas
- Sempre escreva mensagens de commit descritivas.
- Utilize branches para funcionalidades específicas.
- Atualize seu repositório local regularmente com `git pull`.
- Faça revisões de código antes de mesclar mudanças.
