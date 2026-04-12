# FirebaseApp – Semana 7

Atividade referente à **Semana 7** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi implementado o recurso de **upload e exibição de imagem de perfil**, utilizando o Firebase Storage integrado ao Firebase Authentication.

---

## 🎯 Objetivo da Semana

- Trabalhar com upload de arquivos no Firebase
- Utilizar o Firebase Storage
- Permitir seleção de imagem pelo usuário
- Atualizar a foto de perfil do usuário autenticado

---

## ☁️ Firebase Storage

Foi utilizado o serviço **Firebase Storage** para armazenar imagens dos usuários.

Configurações realizadas:

- Bucket configurado no Firebase
- Regras de acesso ajustadas para permitir upload por usuários autenticados

---

## 🔐 Regras de Segurança

Foram definidas regras para permitir que apenas usuários autenticados realizem upload de arquivos:

```javascript id="8mhm8r"
rules_version = '2';

service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

---

## 📱 Funcionalidades Implementadas

### 🔹 Seleção de Imagem
Utilização do pacote **`image_picker`**, permitindo ao usuário:
* Escolher uma imagem da galeria.
* Capturar uma imagem em tempo real com a câmera.

### 🔹 Upload de Imagem
A imagem selecionada é enviada para o **Firebase Storage**:
* **Caminho:** Baseado no ID único do usuário (`UID`).
* **Processamento:** Upload realizado de forma assíncrona para garantir a fluidez da UI.

### 🔹 Atualização do Perfil
Fluxo lógico após o upload bem-sucedido:
1. A URL pública da imagem é obtida do Storage.
2. O perfil do usuário no Firebase Auth é atualizado via `photoURL`.
   ```dart
   await user.updatePhotoURL(url);
   ```

### 🔹 Exibição da Imagem
A interface utiliza o widget **`CircleAvatar`** para renderizar a foto:
```dart
backgroundImage: NetworkImage(user.photoURL!)
```

---

## 📄 Arquivos Criados / Modificados

### `profile.dart`
Responsável pela lógica central de:
* Interface de seleção.
* Comunicação com Firebase Storage.
* Persistência da URL no perfil do usuário.
* Renderização dinâmica da foto.

---

## ⚙️ Integração com o App
A tela de perfil foi integrada ao **Menu Lateral (Drawer)**, facilitando o acesso direto do usuário para visualizar e atualizar suas informações a qualquer momento.

---

## 📚 Tecnologias Utilizadas
* **Flutter** (Framework)
* **Firebase Storage** (Armazenamento de arquivos)
* **Firebase Authentication** (Gestão de usuários)
* **Image Picker** (Acesso ao hardware de imagem)

---

## 🧠 Conceitos Aplicados
* Upload de arquivos em nuvem.
* Manipulação de imagens em dispositivos móveis.
* Integração entre diferentes serviços do ecossistema Firebase.
* Programação assíncrona (`Future/await`).

---

## 📌 Considerações
Nesta etapa, focamos no gerenciamento de imagens de perfil, adicionando uma camada essencial de personalização. A integração entre o **Auth** e o **Storage** demonstra como associar dados binários a usuários autenticados, uma prática fundamental em aplicações reais de mercado.

---

## 🌿 Controle de Versão (Git)

```bash
git branch semana7
git checkout semana7
git add .
git commit -m "Semana 7: Implementação de upload de perfil e integração Firebase"
git push origin semana7
```
