# FirebaseApp – Semana 9

Atividade referente à **Semana 9** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foi implementado o uso do **sensor de GPS**, permitindo obter a localização do usuário em tempo real dentro do aplicativo.

---

## 🎯 Objetivo da Semana

- Trabalhar com geolocalização no Flutter
- Obter a posição atual do usuário
- Configurar permissões de localização
- Utilizar atualização contínua de localização (stream)

---

## 📍 Conceito de GPS

O GPS (Global Positioning System) permite determinar a posição do dispositivo por meio de coordenadas geográficas:

- Latitude
- Longitude

Esse recurso é essencial para aplicações como:

- Mapas
- Entregas
- Transporte
- Rastreamento

---

## ⚙️ Implementação no Flutter

Para acessar o GPS foi utilizado um plugin de geolocalização (ex: `geolocator`).

Fluxo de funcionamento:

1. Verificar se o serviço de localização está ativo  
2. Solicitar permissões ao usuário  
3. Obter a posição atual  
4. (Opcional) Escutar mudanças de localização em tempo real  

---

## 🔐 Permissões

O aplicativo solicita permissão de acesso à localização do usuário.

Esse passo é essencial para garantir:

- Privacidade
- Segurança
- Funcionamento correto do GPS  

---

## 🔄 Atualização em Tempo Real

Para acompanhar mudanças de localização, pode-se utilizar um **Stream**, permitindo:

- Atualização contínua da posição
- Uso em aplicações de rastreamento
- Maior interatividade

---

## ⚡ Precisão da Localização

Foi abordado o uso de diferentes níveis de precisão:

- Alta precisão → maior consumo de bateria  
- Baixa precisão → menor consumo  

A escolha depende do tipo de aplicação.

---

## 📚 Tecnologias Utilizadas

- Flutter
- Plugin de geolocalização (ex: Geolocator)

---

## 🧠 Conceitos Aplicados

- Geolocalização
- Sensores de dispositivo
- Permissões de sistema
- Streams (dados em tempo real)
- Consumo de recursos (bateria vs precisão)

---

## 📌 Considerações

Nesta semana foi introduzido o uso do **sensor de GPS**, permitindo que o aplicativo interaja com a localização do usuário.

Esse recurso amplia significativamente as possibilidades do aplicativo, podendo ser integrado com mapas, rotas e serviços baseados em localização nas próximas etapas.

---

## 🌿 Controle de Versão

```bash id="kzzp7p"
git branch semana9
git checkout semana9
git add .
git commit -m "Semana 9"
git push origin semana9
