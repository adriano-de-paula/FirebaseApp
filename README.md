# FirebaseApp – Semana 8

Atividade referente à **Semana 8** da disciplina **Desenvolvimento de Aplicativos 2**.

Nesta etapa foram estudados conceitos de **mapas e geração de rotas**, integrando serviços externos para cálculo de trajetos entre dois pontos.

---

## 🎯 Objetivo da Semana

- Trabalhar com mapas no Flutter
- Gerar rotas entre origem e destino
- Consumir serviços externos de direções
- Exibir trajetos no mapa
- Estruturar dados de rotas para armazenamento

---

## 🗺️ Conceito de Rotas

Em aplicações móveis, gerar rotas consiste em:

1. Definir um ponto de origem e um destino  
2. Consultar um serviço de direções  
3. Receber dados como:
   - Distância
   - Duração
   - Caminho (polyline)  
4. Exibir o trajeto no mapa  

---

## ⚙️ Funcionamento Geral

O fluxo da aplicação segue os passos:

1. Usuário seleciona pontos no mapa  
2. Aplicação envia requisição para um serviço de rotas  
3. O serviço retorna:
   - Geometria da rota  
   - Distância  
   - Tempo estimado  
4. A rota é desenhada no mapa utilizando uma **polyline**  
5. Os dados podem ser armazenados no Firestore  

---

## 🌐 Serviço de Rotas

Foi utilizado um serviço externo (exemplo: OSRM) para:

- Calcular o trajeto entre dois pontos
- Retornar os dados necessários para exibição

---

## 🧭 Exibição no Mapa

Para visualização:

- Mapa interativo no Flutter
- Desenho da rota com **polyline**
- Atualização dinâmica da interface

---

## 🗄️ Estrutura de Dados (Firestore)

Os dados de rota podem ser armazenados com:

- Origem (GeoPoint)
- Destino (GeoPoint)
- Distância (metros)
- Duração (segundos)
- Polyline (trajeto)
- Endereço (geocodificação reversa)

---

## 📚 Tecnologias Envolvidas

- Flutter
- Mapas (ex: flutter_map)
- Serviços de rotas (ex: OSRM)
- Firebase Firestore

---

## 🧠 Conceitos Aplicados

- Geolocalização
- Consumo de API externa
- Manipulação de coordenadas geográficas
- Renderização de mapas
- Persistência de dados geoespaciais

---

## 📌 Considerações

Nesta semana foi introduzido o conceito de **aplicações baseadas em localização**, permitindo que o aplicativo calcule e exiba rotas em tempo real.

Esse tipo de funcionalidade é amplamente utilizado em aplicativos como transporte, entrega e navegação.

---

## 🌿 Controle de Versão

```bash id="1j5b2o"
git branch semana8
git checkout semana8
git add .
git commit -m "Semana 8"
git push origin semana8
