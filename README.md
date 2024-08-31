// C++ code
// Codigo Jeison Gabriel Botina Diaz
//*#define int led 11,12,12
const int ledGreen = 11;
const int ledRed = 12;
const int ledYellow = 13;
//*configuraciones*/

void setup()
{
  pinMode(ledGreen, OUTPUT);
  pinMode(ledRed, OUTPUT);
  pinMode(ledYellow, OUTPUT);
  Serial.begin(2000);
  Serial.println("Ingrese un número del 1 al 9 para controlar las luces:");
}

/*procesos de bucle */ 

void loop() {
  if (Serial.available() > 0) {
    int command = Serial.parseInt();
    switch (command) {
      case 1:
        digitalWrite(ledGreen, HIGH);
        Serial.println("Luz verde encendida");
        break;
      case 2:
        digitalWrite(ledGreen, LOW);
        Serial.println("Luz verde apagada");
        break;
      case 3:
        digitalWrite(ledRed, HIGH);
        Serial.println("Luz roja encendida");
        break;
      case 4:
        digitalWrite(ledRed, LOW);
        Serial.println("Luz roja apagada");
        break;
      case 5:
        digitalWrite(ledYellow, HIGH);
        Serial.println("Luz amarilla encendida");
        break;
      case 6:
        digitalWrite(ledYellow, LOW);
        Serial.println("Luz amarilla apagada");
        break;
      case 7:
        digitalWrite(ledGreen, HIGH);
        digitalWrite(ledRed, HIGH);
        digitalWrite(ledYellow, HIGH);
        Serial.println("Todas las luces encendidas");
        break;
      case 8:
        digitalWrite(ledGreen, LOW);
        digitalWrite(ledRed, LOW);
        digitalWrite(ledYellow, LOW);
        Serial.println("Todas las luces apagadas");
        break;
      case 9:
        blinkAllLights();
        break;
      default:
        Serial.println("Comando no válido. Ingrese un número del 1 al 9.");
        break;
    }
  }
}
void blinkAllLights() {
  for (int i = 0; i < 10; i++) {
    digitalWrite(ledGreen, HIGH);
    digitalWrite(ledRed, HIGH);
    digitalWrite(ledYellow, HIGH);
    delay(900);
    digitalWrite(ledGreen, LOW);
    digitalWrite(ledRed, LOW);
    digitalWrite(ledYellow, LOW);
    delay(500);
  }
  Serial.println("Modo intermitente completado");
}
