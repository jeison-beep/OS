void setup(){
  for(int i=2;i<14;i=i+1){
  	pinMode(i,OUTPUT);
  }
}
void loop(){
/*
2 verde2
3 amarillo2
4 rojo2

5 verde1
6 amarillo1
7 rojo1

8 rojo3
9 amarillo3
10 verde3

11 verde4
12 amarillo4
13 rojo4

*/
  for(int i=2;i<14;i=i+1){ // Garantizo que todo este apagado
  	digitalWrite(i,LOW);
  }
  digitalWrite(5,HIGH); // enciendo el primer verde
  digitalWrite(4,HIGH); // Enciendo los demas rojos
  digitalWrite(8,HIGH);
  digitalWrite(13,HIGH);
  delay(2000);			// espero
  digitalWrite(5,LOW);  //apago el verde
  digitalWrite(6,HIGH);	// enciendo el amarillo
  delay(500);			//espero
  
  digitalWrite(6,LOW);	//apagar el amarillo
  digitalWrite(7,HIGH);
  
  digitalWrite(2,HIGH); // segundo semaforo verde
  

  digitalWrite(4,LOW); 	// apago el rojo 2
  delay(2000);			// espero
  digitalWrite(2,LOW); // segundo semaforo verde
  digitalWrite(3,HIGH);	// encender el 2do amarillo
  delay(500);			// espero
  digitalWrite(2,LOW);	// apago ambos
  digitalWrite(3,LOW);
  digitalWrite(4,HIGH); // enciendo el rojo
  
  
  digitalWrite(10,HIGH); // tercer semaforo verde
  digitalWrite(8,LOW);	// apago el rojo 3
  delay(2000);			// espero
  digitalWrite(10,LOW); // tercer semaforo verde
  digitalWrite(9,HIGH);	// encender el 3erdo amarillo
  delay(500);			// espero
  digitalWrite(9,LOW);	// apago ambos
  digitalWrite(10,LOW);
  digitalWrite(8,HIGH);
  
  
  digitalWrite(11,HIGH); // cuarto semaforo verde
  digitalWrite(13,LOW);
  delay(2000);			// espero
  digitalWrite(11,LOW); // tercer semaforo verde
  digitalWrite(12,HIGH);	// encender el 4to amarillo
  delay(500);			// espero
  digitalWrite(11,LOW);	// apago ambos
  digitalWrite(12,LOW);
  digitalWrite(13,HIGH);
  

  
  
}