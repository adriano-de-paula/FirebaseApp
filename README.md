# FirebaseApp – Semana 3

Atividade referente à **Semana 3** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi criado um banco de dados no Firebase Firestore e realizada a leitura de dados diretamente no aplicativo Flutter.

---

## 🎯 Objetivo da Semana

- Criar um banco de dados no Cloud Firestore
- Inserir dados no banco
- Conectar o aplicativo Flutter ao banco
- Exibir dados do Firestore na interface do aplicativo

---

## 🗄 Banco de Dados Firestore

Foi criado um banco de dados no **Cloud Firestore**.

Configuração realizada:

- Edição: Standard
- Localização: São Paulo
- Modo: Produção

Estrutura criada no banco:

- Coleção: config
- Documento: welcome
- Conteúdo do documento:

```json
{
  "text": "Bem-vindo ao aplicativo Firebase!"
}
```

---
## ⚙️ Alterações no Projeto Flutter

Inicialização do Firebase

O arquivo `main.dart` foi alterado para inicializar o Firebase antes da execução do aplicativo.

```dart
await Firebase.initializeApp(
  options: DefaultFirebaseOptions.currentPlatform,
);
```

### Criação do componente ``welcome.dart``

Foi criado o arquivo ``welcome.dart``, responsável por:

- Acessar o banco Firestore

- Buscar o documento ``welcome``

- Exibir a mensagem no aplicativo

A leitura do banco é feita utilizando **StreamBuilder**, permitindo que a interface seja atualizada automaticamente quando os dados forem modificados no Firestore.

---


## 🔐 Regras do Firestore

Foram definidas regras de leitura para permitir que o aplicativo consulte os dados da coleção ``config``.

```dart
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /config/{doc} {
      allow read: if true;
      allow write: if false;
    }
  }
}
```
---

## 🌿 Controle de Versão

Branch criada para esta etapa:

```markdown
git branch semana3
git checkout semana3
git add .
git commit -m "Semana 3"
git push origin semana3
```
---

## 🧠 Considerações

Nesta semana foi realizada a primeira integração prática entre o aplicativo Flutter e um banco de dados na nuvem utilizando **Cloud Firestore**.

O aplicativo passou a consumir dados externos e exibi-los na interface, introduzindo o conceito de aplicações que utilizam **APIs e serviços de backend**.

