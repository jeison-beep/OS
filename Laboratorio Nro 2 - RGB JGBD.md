//Jeison Gabriel Botina Diaz 
//Ing en sistemas 7mo - Semestre
#define semaforo1_verde  10
#define semaforo1_rojo  11
#define semaforo2_verde  9
#define semaforo2_rojo  13
#define semaforo3_verde  8
#define semaforo3_rojo  12
#define interruptor  2

void setup() {
  int semaforos[] = {semaforo1_verde, semaforo1_rojo, semaforo2_verde, semaforo2_rojo, semaforo3_verde, semaforo3_rojo};
  for (int i = 0; i < 6; i++) {
    pinMode(semaforos[i], OUTPUT);
  }
  pinMode(interruptor, INPUT);
  Serial.begin(9600);
}

void setSemaforo(int verde, int rojo, bool estadoVerde, bool estadoRojo) {
  digitalWrite(verde, estadoVerde ? HIGH : LOW);
  digitalWrite(rojo, estadoRojo ? HIGH : LOW);
}

void loop() {
  bool inter = digitalRead(interruptor);
  if (inter == LOW) {
    setSemaforo(semaforo1_verde, semaforo1_rojo, true, true);
    Serial.println("SEMAFORO 1 EN AMARILLO ");
    setSemaforo(semaforo2_verde, semaforo2_rojo, true, true);
    Serial.println("SEMAFORO 2 EN AMARILLO ");
    setSemaforo(semaforo3_verde, semaforo3_rojo, true, true);
    Serial.println("SEMAFORO 3 EN AMARILLO ");
  } else {
    for (int i = 0; i < 3; i++) {
      setSemaforo(semaforo1_verde, semaforo1_rojo, i == 0, i != 0);
      setSemaforo(semaforo2_verde, semaforo2_rojo, i == 1, i != 1);
      setSemaforo(semaforo3_verde, semaforo3_rojo, i == 2, i != 2);
      delay(1000);
    }
  }
}

