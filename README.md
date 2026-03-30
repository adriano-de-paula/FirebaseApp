# FirebaseApp – Semana 5

Atividade referente à **Semana 5** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi implementado um sistema de **anotações em tempo real**, utilizando o Cloud Firestore com controle de acesso por usuário autenticado.

---

## 🎯 Objetivo da Semana

- Implementar operações de CRUD (Create, Read, Update, Delete)
- Trabalhar com dados em tempo real no Firestore
- Garantir segurança dos dados por usuário autenticado
- Integrar interface Flutter com banco de dados dinâmico

---

## 🗄 Estrutura do Banco de Dados

Foi utilizada a seguinte estrutura no Firestore:

users/{userId}/notes/{noteId}

Cada usuário possui sua própria coleção de anotações.

Exemplo de documento:

```json
{
  "description": "Minha primeira anotação",
  "createdAt": "timestamp",
  "updatedAt": "timestamp"
}
```

---

## 🔐 Regras de Segurança

As regras do Firestore foram alteradas para garantir que:

- Cada usuário acesse apenas seus próprios dados
- Apenas usuários autenticados possam ler e escrever
```javascript
match /users/{userId}/{document=**} {
  allow read, write: if request.auth != null && request.auth.uid == userId;
}
```

---

## 📱 Funcionalidades Implementadas

### 🔹 Criar anotação (Create)
- Campo de texto para descrição
- Validação de campo vazio
- Inserção no Firestore com timestamp

### 🔹 Listar anotações (Read)
- Uso de `StreamBuilder`
- Atualização automática em tempo real
- Ordenação por data de criação

### 🔹 Editar anotação (Update)
- Edição inline (direto na lista)
- Atualização do campo `description`
- Registro de `updatedAt`


### 🔹 Remover anotação (Delete)
- Confirmação antes da exclusão
- Remoção direta do Firestore

---

## ⚙️ Implementação no Flutter

📄 **Arquivo criado**
- `notes.dart`

Responsável por:

- Gerenciar CRUD das anotações
- Conectar com Firestore
- Controlar estado da interface

---

## 🔄 Uso de StreamBuilder

A listagem das notas utiliza:

```dart
StreamBuilder<QuerySnapshot>(
  stream: _col.orderBy('createdAt', descending: true).snapshots(),
)
```

Isso permite que:

- Alterações no banco sejam refletidas automaticamente na tela
- A aplicação funcione em tempo real

---

## 🧭 Navegação

Foi adicionada uma nova opção no menu lateral (Drawer):

```dart
ListTile(
  title: Text('Anotações'),
)
```

Direcionando para a tela `NotesPage`.

---

## 🧠 Conceitos Aplicados

- CRUD com Firestore
- Aplicações em tempo real
- StreamBuilder
- Controle de acesso com Firebase Auth
- Estrutura de dados por usuário
- Sincronização automática com banco

---

## 📌 Considerações

Nesta semana foi implementado um sistema completo de gerenciamento de dados em tempo real, onde cada usuário possui suas próprias informações armazenadas de forma segura.

O uso do Firestore combinado com StreamBuilder permitiu criar uma aplicação dinâmica, sem necessidade de recarregamento manual dos dados.
