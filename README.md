Kawan Oliveira amorim RM 562197
Alana Vieira Batista RM 563796
https://wokwi.com/projects/432795335404972033
https://youtu.be/ItRtJiLGayU
🚨 Sistema de Alerta com Arduino (LED + Buzzer + Potenciômetro)
📝 Descrição do Problema

Em muitos projetos de automação, é necessário monitorar variáveis como nível de água, luz ou temperatura. Quando esse valor ultrapassa um limite seguro, um **alerta visual ou sonoro** deve ser acionado. Este projeto simula essa lógica usando um potenciômetro como sensor de entrada.



 💡 Visão Geral da Solução

Este sistema utiliza um **Arduino Uno**, um **potenciômetro**, um LED e um buzzer para emitir um alerta caso o valor lido ultrapasse 700.

 📌 Componentes utilizados:

- 1x Arduino Uno  
- 1x Potenciômetro  
- 1x LED vermelho  
- 1x Resistor (220Ω para o LED)  
- 1x Buzzer  
- Jumpers



 ⚙️ Funcionamento

1. O potenciômetro envia um valor analógico (0 a 1023) para o pino **A0** do Arduino.
2. O Arduino lê esse valor a cada segundo (delay 1000).
3. Se o valor for maior que 700, o LED acende e o buzzer é ativado.
4. Caso contrário, ambos permanecem desligados.
5. O valor lido é exibido no Monitor Serial.



📁 Código Arduino

const int sensorPin = A0;
const int ledPin = 9;
const int buzzerPin = 8;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);-
}

void loop() {
  int valor = analogRead(sensorPin);
  Serial.print("Nível simulado: ");
  Serial.println(valor);

  if (valor > 700) {
    digitalWrite(ledPin, HIGH);
    digitalWrite(buzzerPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
    digitalWrite(buzzerPin, LOW);
  }

  delay(1000);;
}
