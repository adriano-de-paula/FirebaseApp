# FirebaseApp – Semana 10

Atividade referente à **Semana 10** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi realizada a implementação de **datas e horários nas anotações**, além da integração com o recurso de mapa já desenvolvido anteriormente.

---

## 🎯 Objetivo da Semana

- Trabalhar com seleção de datas e horários no Flutter
- Integrar DatePicker e TimePicker
- Armazenar informações temporais no Firestore
- Melhorar a estrutura das anotações
- Integrar funcionalidades de mapa às notas

---

## 📅 Datas e Horários no Flutter

Foram utilizados os componentes:

- `showDatePicker` → seleção de data  
- `showTimePicker` → seleção de horário  

Esses componentes permitem:

- Interface visual amigável  
- Retorno assíncrono dos valores selecionados  
- Integração com o estado da aplicação  

---

## ⚙️ Alterações no Banco de Dados

Os documentos de notas passaram a ter novos campos:

```json
{
  "description": "Texto da nota",
  "createdAt": "timestamp",
  "updatedAt": "timestamp",
  "date": "timestamp",
  "timeMinutes": "int"
}
````

* `date` → armazena a data selecionada
* `timeMinutes` → armazena o horário em minutos

---

## 📱 Funcionalidades Implementadas

### 🔹 Seleção de Data

* Abertura de calendário com `DatePicker`
* Escolha de dia, mês e ano
* Armazenamento no Firestore

```dart
showDatePicker(...)
```

---

### 🔹 Seleção de Horário

* Seleção de hora e minuto com `TimePicker`
* Conversão para minutos totais
* Armazenamento no banco

```dart
showTimePicker(...)
```

---

### 🔹 Formatação de Dados

Foram criadas funções para exibir os dados:

* Data → formato `MM/AAAA`
* Hora → formato `HH:mm`

---

### 🔹 Integração com Mapa

Cada nota agora pode:

* Abrir o mapa
* Exibir localização associada
* Editar posição diretamente

```dart
_openMapViewer(...)
```

---

### 🔹 Interface Melhorada

Foram adicionados ícones nas notas:

* 📍 Mapa
* 📅 Data
* ⏰ Horário
* 🗑 Remover

Cada item possui ação específica diretamente na lista.

---

## 🔄 Atualizações em Tempo Real

A listagem continua utilizando:

* `StreamBuilder`

Garantindo:

* Atualização automática dos dados
* Sincronização com o Firestore

---

## 📚 Tecnologias Utilizadas

* Flutter
* Firebase Firestore
* DatePicker
* TimePicker
* Integração com mapas

---

## 🧠 Conceitos Aplicados

* Manipulação de datas e horários
* Interfaces interativas
* Persistência de dados temporais
* Integração entre funcionalidades
* Programação assíncrona

---

## 📌 Considerações

Nesta semana as anotações evoluíram para um nível mais completo, permitindo registrar não apenas texto, mas também **informações de tempo e localização**.

Isso aproxima o aplicativo de soluções reais como:

* Agendas
* Lembretes
* Aplicativos de tarefas

---

## 🌿 Controle de Versão

```bash
git branch semana10
git checkout semana10
git add .
git commit -m "Semana 10"
git push origin semana10
```


