# 📒 GoContacts API

Uma API REST simples de gerenciamento de contatos, construída em Go **puro** — sem frameworks, sem bibliotecas externas. Apenas a stdlib.

Este projeto foi desenvolvido como primeiro CRUD em Go, explorando os pacotes nativos `net/http` e `encoding/json` para construir uma API funcional do zero.

---

## 🚀 Funcionalidades

- ✅ Criar contato
- ✅ Listar todos os contatos
- ✅ Buscar contato por ID
- ✅ Atualizar contato
- ✅ Deletar contato

---

## 🛠️ Tecnologias

- [Go](https://golang.org/) — sem dependências externas
- `net/http` — servidor HTTP e roteamento
- `encoding/json` — serialização e desserialização JSON

---

## 📦 Como rodar

**Pré-requisito:** ter o [Go instalado](https://go.dev/dl/) (versão 1.18+)

```bash
# Clone o repositório
git clone https://github.com/rafaelAmora/gocontacts-api.git
cd gocontacts-api

# Rode o servidor
go run main.go
```

O servidor vai iniciar em `http://localhost:8080`.

> ⚠️ Os dados são armazenados **em memória** — ao reiniciar o servidor, os contatos são perdidos.

---

## 📡 Endpoints

Todos os endpoints estão em `/contacts`.

### Criar contato
```
POST /contacts
```
**Body (JSON):**
```json
{
  "name": "João Silva",
  "email": "joao@email.com",
  "phone": "11999999999"
}
```
**Resposta:** `200 OK` com o contato criado (incluindo o `id` gerado).

---

### Listar todos os contatos
```
GET /contacts
```
**Resposta:** `200 OK` com array de contatos.

---

### Buscar contato por ID
```
GET /contacts?id=1
```
**Resposta:** `200 OK` com o contato encontrado, ou `404` se não existir.

---

### Atualizar contato
```
PUT /contacts?id=1
```
**Body (JSON):**
```json
{
  "name": "João Atualizado",
  "email": "novo@email.com",
  "phone": "11888888888"
}
```
**Resposta:** `200 OK` em caso de sucesso, ou `404` se não existir.

---

### Deletar contato
```
DELETE /contacts?id=1
```
**Resposta:** `200 OK` em caso de sucesso, ou `404` se não existir.

---

## 🗂️ Estrutura do projeto

```
gocontacts-api/
└── main.go   # Toda a aplicação em um único arquivo
```

---

## 🧠 O que foi aprendido

- Criação de um servidor HTTP com `http.NewServeMux()`
- Roteamento manual por método HTTP (`GET`, `POST`, `PUT`, `DELETE`)
- Leitura e escrita de JSON com `encoding/json`
- Armazenamento em memória com `map`
- Passagem de parâmetros via query string (`?id=1`)
