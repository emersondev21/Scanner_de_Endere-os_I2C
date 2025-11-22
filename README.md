# Scanner_de_Endere-os_I2C
Localizar endereço de dispositivo I2C utilizando a plataforma Arduino Uno

### 🔍 Scanner de Endereços I2C – Arduino

Este projeto realiza a varredura completa do barramento I2C e identifica todos os dispositivos conectados, exibindo seus endereços no monitor serial.
É uma ferramenta essencial para quem utiliza displays, sensores ou qualquer periférico I2C e precisa confirmar o endereço correto para comunicação.

### 📌 Requisitos

Arduino Uno, Mega, Nano ou compatível

Biblioteca Wire.h (já incluída na IDE Arduino)

Pelo menos um dispositivo I2C conectado ao barramento

Monitor Serial configurado a 9600 baud

### 📜 Funcionamento do Código

O código varre todos os endereços possíveis do barramento I2C (de 1 a 126).
Para cada endereço:

O Arduino tenta iniciar uma transmissão I2C usando Wire.beginTransmission(address).

Se Wire.endTransmission() retornar 0, significa que há um dispositivo respondendo naquele endereço.

O endereço é impresso no monitor serial em formato hexadecimal.

Esse processo se repete a cada 2 segundos.

### 🖥️ Como Usar

Conecte seu dispositivo I2C ao Arduino (pinos A4 → SDA e A5 → SCL no Arduino Uno).

Carregue o código na placa.

Abra o Monitor Serial a 9600 baud.

Observe os endereços encontrados, por exemplo:

``` cpp
Dispositivo I2C encontrado no endereco 0x27
```

### 🛠️ Aplicações Comuns

* Identificação do endereço de displays LCD I2C (0x27, 0x3F, etc.)

* Confirmação de sensores como MPU6050, BMP280, DS3231

* Diagnóstico de falhas no barramento I2C

* Testes de conexão e soldagem
