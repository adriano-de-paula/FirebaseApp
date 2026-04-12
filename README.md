# FirebaseApp – Semana 6

Atividade referente à **Semana 6** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi implementado um sistema de **notificações locais**, integrando o aplicativo com eventos internos para exibição de alertas ao usuário.

---

## 🎯 Objetivo da Semana

- Implementar notificações no aplicativo
- Configurar permissões no Android
- Criar canal de notificações
- Integrar notificações com ações do usuário (criação de notas)

---

## 🔔 Conceito Aplicado

Foi utilizado o conceito de **notificações locais**, onde o próprio aplicativo dispara notificações no dispositivo, sem necessidade de um servidor externo.

Esse comportamento é comum em aplicações que precisam notificar eventos como:

- Criação de dados
- Lembretes
- Atualizações internas

---

## ⚙️ Configurações Realizadas

### 📱 Permissão no Android

No arquivo `AndroidManifest.xml` foi adicionada a permissão:

```xml id="1t4j6k"
<uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
```

---

## ⚙️ Configuração do build.gradle

Foi habilitado suporte necessário para notificações:

```dart
isCoreLibraryDesugaringEnabled = true
```
E adicionada dependência:

```dart
coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.1.4")
```

---

## 📄 Arquivo criado

`notifications.dart`

Responsável por:

- Inicializar o sistema de notificações
- Criar canal de notificações
- Exibir notificações no dispositivo

---

## 🔔 Canal de Notificação

Foi criado um canal:

- Nome: **Notificações Importantes**
- Importância: alta

Isso garante que as notificações apareçam com destaque no dispositivo.

---

## 🔄 Integração com o App

A notificação foi integrada ao fluxo de criação de notas (notes.dart):

```dart
Notifications.show(
  id: note.id.hashCode,
  title: 'Nota criada',
  body: text,
);
```

Com isso, sempre que uma nova nota é criada:

- O dado é salvo no Firestore
- Uma notificação é exibida ao usuário

---
  
## 🚀 Inicialização no main.dart

O sistema de notificações foi inicializado no início da aplicação:

```dart
await Notifications.init();
await Permission.notification.request();
```

---

## 📚 Tecnologias Utilizadas

- Flutter Local Notifications
- Firebase (integração com dados)
- Permission Handler

---

## 🧠 Conceitos Aplicados

- Notificações locais
- Permissões de sistema
- Integração entre eventos e interface
- Experiência do usuário (UX)

---

## 📌 Considerações

Nesta semana foi implementado um recurso importante para melhorar a experiência do usuário: notificações em tempo real dentro do próprio aplicativo.

A aplicação passou a reagir a eventos internos, tornando-se mais interativa e próxima de aplicações utilizadas no mercado.
