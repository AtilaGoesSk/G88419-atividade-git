# **Hospedando um Repositório no GitHub**
## **Criar um Repositório no GitHub**

1. Acesse [GitHub](https://github.com/) e faça login.
2. No canto superior direito, clique no ícone `+` e selecione **"New repository"**.
3. Escolha um nome para o repositório.
4. Defina a visibilidade do repositório (**público** ou **privado**).
5. Clique em **"Create repository"**.

## **Conectar um Repositório Local ao GitHub**

### **Inicializar o Git no Projeto**
```sh
cd /caminho/do/projeto
git init
```

### **Adicionar Arquivos ao Git**
```sh
git add .
git commit -m "Primeiro commit"
```

### **Conectar ao Repositório Remoto**
```sh
git remote add origin <URL_DO_REPOSITORIO>
git remote -v
```

### **Enviar o Código para o GitHub**
```sh
git branch -M main
git push -u origin main
```

## **Clonar um Repositório do GitHub**
```sh
git clone <URL_DO_REPOSITORIO>
```

## **Atualizar o Código no GitHub**
```sh
git add .
git commit -m "Descrição das mudanças"
git push origin main
```

## **Sincronizar o Código com o GitHub**
```sh
git pull origin main
```

E por fim, o nosso codigo está hospedado em GIT.
