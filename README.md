
## 🚀 Como executar o projeto

### 1. Suba o ambiente com Docker

```bash
docker compose up -d
```

### 2. Acesse o container do PHP

```bash
docker exec -it php bash
```

### 3. Instale as dependências

```bash
composer install
```

### 4. Copie o arquivo `.env.example` para `.env`:

```bash
cp .env.example .env
```

> Altere as variáveis do `.env` de acordo com o seu ambiente, principalmente as variáveis de banco de dados.

### 5. Gere a APP_SECRET (caso necessário)

```bash
php -r "echo bin2hex(random_bytes(16));"
```

E adicione a chave gerada na variável `APP_SECRET` do seu arquivo `.env`.

### 6. Execute as migrations

```bash
php bin/console doctrine:migrations:migrate
```

Confirme com `yes` para aplicar as mudanças no banco de dados.

---

## 🔐 Permissões

Para garantir que os diretórios tenham as permissões corretas:

```bash
docker exec -it php bash
chmod -R 777 var
chmod -R 777 public
```

> Substitua os diretórios conforme necessário.

---

## 📄 Documentação

- CRUD de Empresas
- CRUD de Sócios, com relação `ManyToOne` com Empresas

---

## 🌐 Acesso

A aplicação estará disponível em:

```
http://localhost:9001/
```

---

