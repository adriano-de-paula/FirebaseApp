# FirebaseApp – Semana 2

Atividade referente à **Semana 2** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi realizada a criação do projeto no Firebase e a configuração inicial de integração com o projeto Flutter.

---

## 🎯 Objetivo da Semana

- Criar um projeto na plataforma Firebase
- Conectar o projeto Flutter ao Firebase
- Configurar ferramentas necessárias para integração
- Ajustar o arquivo `.gitignore` para evitar envio de arquivos sensíveis ao repositório

---

## 🔥 Criação do Projeto Firebase

Foi criado um projeto na plataforma **Google Firebase**, que será utilizado como base para os serviços de back-end da aplicação.

Durante a criação:

- Foi definido o nome do projeto
- A opção **Google Analytics** foi desmarcada
- O projeto foi configurado no console do Firebase

---

## ⚙️ Integração com o Projeto Flutter

Para realizar a integração entre Flutter e Firebase foram executados os seguintes comandos no terminal:

```bash
firebase login
dart pub global activate flutterfire_cli
flutterfire configure --project=id_do_projeto
```

---

## 📂 Alteração no .gitignore

Foi realizada uma modificação no arquivo .gitignore para evitar que arquivos de configuração sensíveis do Firebase sejam enviados ao repositório.

Itens adicionados:

```bash
# Firebase
firebase.json
.firebase
lib/firebase_options.dart
android/app/google-services.json
```

---

## 🌿 Controle de Versão

Foi criada a branch específica para esta etapa do projeto:

```bash
git branch semana2
git checkout semana2
git add .
git commit -m "Semana 2"
git push origin semana2
```
---

## 🧠 Considerações

A Semana 2 teve como foco a **configuração do ambiente de integração entre Flutter e Firebase**, estabelecendo a base necessária para utilização de serviços como banco de dados, autenticação e armazenamento em nuvem nas próximas etapas do projeto.

---

- **Curso:** Tecnologia em Sistemas para Internet
- **Disciplina:** Desenvolvimento de Aplicativos 2
- **Aluno:** Adriano de Paula  
