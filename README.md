# Camille-Andrade-TCC
# 📡 SENSEWAY:SISTEMA DE ORIENTAÇÃO INDOOR COM LUVA RFID E APLICAÇÃO WEB PARA PESSOAS COM DEFICIÊNCIA VISUAL  
### 👩‍🎓 Autora: Camille Andrade  

Repositório principal que organiza **todo o projeto do TCC**, incluindo firmware (ESP32), backend (API),e frontend.  
Este repositório centraliza todos os artefatos para facilitar a avaliação, manutenção e reprodução da solução.

---

# 🔗 Repositórios do Projeto

## 🖥️ **Frontend – Aplicação Web SenseWay**
Interface web para visualização da localização em tempo real e gerenciamento da solução.  
🔗 Repositório: **https://github.com/camilleandrade125/SenseWay**

---

## ⚙️ **Backend – REST API (NodeJS)**
Responsável por receber dados do ESP32, processar, armazenar e disponibilizar para a aplicação web.  
🔗 Repositório: **https://github.com/camilleandrade125/senseway-api-v2**

---

## 🔌 **Firmware – ESP32**
Responsável pela leitura RFID, envio do UID, processamento e execução das ações (áudio, publicação para API).  
📂 Disponível na pasta: **https://drive.google.com/drive/folders/1OcJHe5dglzYFQ0PqoEl3-mH_J6V_DFSE?usp=sharing**

---

# 🧭 Arquitetura Geral da Solução

### 📍 **1. Módulo RFID – RC522**
- Lê o UID das etiquetas RFID instaladas nos cômodos.  
- Envia o código da tag via **SPI** para o ESP32.

### ⚙️ **2. ESP32 – Unidade Principal**
- Processa o UID recebido.  
- Identifica o cômodo correspondente.  
- Envia comando **PLAY** via **UART (TX – 9600 bps)** ao DF Player Mini.  
- Envia dados em **JSON via Wi-Fi** para a API:  
  `UID, cômodo, timestamp, status`

### 🔊 **3. DF Player Mini**
- Recebe comandos via **UART (RX – 9600 bps)**.  
- Reproduz o áudio do cômodo correspondente.  
- Saída conectada ao speaker da luva.

### 🌐 **4. REST API (NodeJS)**
- Recebe dados do ESP32.  
- Armazena no banco **MongoDB Atlas**.  
- Disponibiliza endpoints para consulta em tempo real.

### 🖥️ **5. Aplicação Web - SenseWay**
- Exibe o cômodo detectado no último registro.  
- Interface simples para acompanhamento do responsável.  
- Comunicação via HTTPS/JSON.

---

# 🛠️ Tecnologias

## 🔹 **Hardware**
- 📡 RC522 e Tags — Leitor RFID  
- 🔌 ESP32 — Microcontrolador Wi-Fi  
- 🎵 DF Player Mini  
- 🔊 Speaker  
- 🔋 Fonte 5V + Step-Down

## 🔹 **Backend**
- NodeJS  
- Express  
- MongoDB Atlas 
- Mongoose  

## 🔹 **Frontend**
- HTML, CSS, ReactJS










