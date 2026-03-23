# FirebaseApp – Semana 4

Atividade referente à **Semana 4** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi implementado o sistema de **autenticação de usuários** utilizando o Firebase Authentication, permitindo cadastro, login e recuperação de senha.

---

## 🎯 Objetivo da Semana

- Configurar autenticação no Firebase
- Implementar cadastro de usuários
- Implementar login
- Implementar recuperação de senha
- Controlar acesso às telas do aplicativo com base no usuário autenticado

---

## 🔐 Configuração no Firebase

Foi habilitado o método de autenticação:

- **E-mail e senha**

Também foi configurado:

- Domínio autorizado:
`studio.firebase.google.com`

---

## 📱 Funcionalidades Implementadas

### 🔹 Cadastro de usuário
Arquivo: `sign.dart`

- Criação de conta com e-mail e senha
- Validação de campos:
- E-mail válido
- Senha mínima de 6 caracteres
- Confirmação de senha
- Envio de verificação por e-mail
- Tratamento de erros (ex: e-mail já em uso)

---

### 🔹 Login
Arquivo: `login.dart`

- Autenticação com e-mail e senha
- Tratamento de erros:
- Usuário não encontrado
- Senha incorreta
- Muitas tentativas

---

### 🔹 Recuperação de senha
Arquivo: `forgot.dart`

- Envio de e-mail para redefinição de senha
- Feedback ao usuário sobre sucesso ou erro

---

### 🔹 Controle de autenticação (AuthGate)

O `main.dart` foi alterado para controlar o acesso ao app:

```dart
StreamBuilder<User?>(
stream: FirebaseAuth.instance.authStateChanges(),
)
```
Comportamento:

- Usuário não autenticado → vai para tela de login
- Usuário autenticado → acessa a tela principal

---

### 🔹 Logout

Foi implementada a opção de sair do sistema:

```dart
await FirebaseAuth.instance.signOut();
```

Disponível no menu lateral (Drawer).

---

## ⚙️ Integração com o App

O aplicativo agora possui fluxo completo:

1. Usuário cria conta
2. Realiza login
3. Acessa o app
4. Visualiza dados do Firestore (Semana 3)
5. Pode sair da conta

---

## 🌿 Controle de Versão

Branch criada:

```bash
git branch semana4
git checkout semana4
git add .
git commit -m "Semana 4"
git push origin semana4
```
---

## 🧠 Considerações

Nesta semana foi implementado um dos pilares fundamentais de aplicações modernas: **a autenticação de usuários**.

O uso do Firebase Authentication permitiu adicionar um sistema seguro de login sem necessidade de implementar manualmente toda a infraestrutura de autenticação.

Além disso, foi introduzido o conceito de **controle de acesso baseado no estado do usuário**, tornando o aplicativo mais completo e próximo de um sistema real.

