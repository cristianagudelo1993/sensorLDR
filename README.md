# sensorLDR

/*11-12-2015*/

#include <Servo.h> 
Servo myservo;

void setup() 
{ 
  myservo.attach(PC_4); 
} 

void loop()
{
  // Declaracion de la entradas analogicas compuestas por los divisores de tension para conocer la posicion relativa del sol
   int R1 = analogRead(PB_5); 
   int R2 = analogRead(PE_5); 
   int R3 = analogRead(PD_0); 
   int R4 = analogRead(PE_2);
   int R5 = analogRead(PD_1); 
   
  //Secuencia de los angulos del panel segun el mayor valor de voltaje

  if (R1>R2 && R1>R3 && R1>R4 && R1>R5) //Pregunta si R1 es mayor que todos los demas voltajes
       {
         myservo.write(20); //posiciona el servo en el primer angulo      
       }
       else
         {
           if (R2>R1 && R2>R3 && R2>R4 && R2>R5)//Pregunta si R2 es mayor que todos los demas voltajes
       {
         myservo.write(55); //posiciona el servo en el segundo angulo       
      
       }
       else 
       {
         if (R3>R1 && R3>R2 && R3>R4 && R3>R5)//Pregunta si R3 es mayor que todos los demas voltajes
       {
         myservo.write(90); //posiciona el servo en el tercer angulo      
           
       }
       else
         {
           if (R4>R1 && R4>R2 && R4>R3 && R4>R5)//Pregunta si R4 es mayor que todos los demas voltajes
       {
         myservo.write(125); //posiciona el servo en el cuarto angulo   
       
       }
       else
         {
           if (R5>R1 && R5>R2 && R5>R3 && R5>R4)//Pregunta si R1 es mayor que todos los demas voltajes
       {
         myservo.write(160); //posiciona el servo en el quinto angulo       
   
       }
         }
         }
       }
         }
}

