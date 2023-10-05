# alarmacontraincendios
Alarma contraincendios actividad 2 internet de las cosas. 
// C++ code
// Se colocan 3 variables
int gas = 0; //sirve para que la lectura de gas se guarde
int buzz = 4;
int led = 2;
 
void setup()
{
  pinMode(A5, INPUT);
  pinMode(buzz, OUTPUT);
  //Monitor en Serie 
  Serial.begin(9600);
}

void loop()
{
  gas = analogRead (A5);
  Serial.println(gas);
  
  if (gas >= 300) {
    //La alarma sonara cuando detecte el gas igual o mayor al valor 500
  tone (buzz,1500, 4000);
  delay (500); 
  tone (buzz,5000, 1500);
  delay (1000); 
	} else {
  	//Apagar
  	noTone(buzz);
	}
}
