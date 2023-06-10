## CESAR AUGUSTO GONZALEZ INFANTE
# Práctica Nivel del agua

## Programación

```
// defines pins numbers
const int trigPin = 4;
const int echoPin = 12;
const int led1 = 22;
const int led2 = 21;
const int led3 = 19;
const int led4 = 18;

// defines variables
long duration;
int distance;
int safetyDistance;


void setup() {
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
pinMode(led3, OUTPUT);
pinMode(led4, OUTPUT);
Serial.begin(9600); // Starts the serial communication
}


void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);

// Calculating the distance
distance= duration*0.047/2;

safetyDistance = distance;
if (safetyDistance>=0 && safetyDistance<=5)
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=5 && safetyDistance<=10) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=10 && safetyDistance<=15) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=15) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, HIGH);
}
else
{
 digitalWrite(led1,  LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}

// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(distance);
delay (2000);
}
```

## Librerías

En esta ocación no se ocuparon librerías
## Conexión

![](https://github.com/CesarG16/aguanivel/blob/main/eje8.png?raw=true)

## Funcionamiento del programa
Cuando es menos de 5 el nivel del agua se enciende el primer led
![](https://github.com/CesarG16/aguanivel/blob/main/eje9.png?raw=true)
Cuando es menos de 10 el nivel del agua se enciende el segundo led
![](https://github.com/CesarG16/aguanivel/blob/main/eje10.png?raw=true)
Cuando es menos de 15 el nivel del agua se enciende el tercer led
![](https://github.com/CesarG16/aguanivel/blob/main/eje11.png?raw=true)
Cuando es mayor de 15 el nivel del agua se enciende el cuarto led
![](https://github.com/CesarG16/aguanivel/blob/main/eje12.png?raw=true)

## Evidencias

[Página](https://wokwi.com/projects/367189948422624257)


# Créditos

Desarrollado por Ing. Cesar Augusto Gonzalez Infante

- [GitHub](https://github.com/CesarG16)