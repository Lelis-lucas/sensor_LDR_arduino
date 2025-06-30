# sensor_LDR_arduino
Circuito sensor LDR simples integrado ao arduino nano 

* UM CIRCUITO ONDE O LED ACENDO NO ESCURO E APAGA NA LUZ*
* materiais: 
- Arduino nano
- LDR
- Resistor 10k 
- LED
- Resistor para LED 220
- Protoboard, jumpers

* Funcionamento do LDR: 
 - Mais luz --> Menor resistência
 - Menos luz --> Maior resistência (até 1MOhm)
 
 código: 
 int ldr = A0;     // Entrada do ldr
int led = 3;      // Saida do led

void setup() {
  pinMode(led, OUTPUT);
  Serial.begin(9600);  // Para ver os valores no monitor serial !!!!! 
}

void loop() {
  int valorLuz = analogRead(ldr); // Lê de 0 (escuro) até 1023 (muita luz)
  Serial.println(valorLuz);       // Mostra no monitor serial

  if (valorLuz < 500) {           // Menor valor = mais escuro
    digitalWrite(led, HIGH);      // Liga o LED no escuro
  } else {
    digitalWrite(led, LOW);       // Desliga o LED na claridade
  }

  delay(200); // Leitura a cada 200ms
}

