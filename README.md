# Mecatronica-2023-2024
This is the repository for my personal work for the Mechatronics class.

# Bitácora Personal: Mecatronica-2023-2024

Esta es la wiki de mi trabajo personal en el proyecto de mecatrónica. Para facilitar la exposición de mis evidencias, se mostrará una lista en las áreas en las que estuve más involucrado, ya que en realidad, los tres integrantes del equipo participamos en todas en realidad.

## Elementos:
* Lluvia de ideas  
En la fase inicial del proyecto, nos sumergimos en una lluvia de ideas para explorar diversas posibilidades y encontrar la mejor opción para nuestro proyecto de mecatrónica. Cada miembro del equipo compartió sus pensamientos y preferencias, lo que nos permitió refinar y seleccionar una idea que nos entusiasmara a todos.

* Diseño y obtención de los materiales  
Con la idea principal en mente, nos embarcamos en la fase de diseño y planificación. Trabajamos en la creación de esquemas detallados para los circuitos eléctricos y las piezas mecánicas del robot. Además, nos dedicamos a la búsqueda y adquisición de los materiales necesarios para la construcción del prototipo.

* Diseño eléctrico  
En esta etapa, cada uno de nosotros se centró en el diseño eléctrico de diferentes componentes del proyecto. Se delinearon los circuitos, se seleccionaron los componentes electrónicos y se elaboró un plan para la integración eficiente de todos los elementos. La comunicación constante fue clave para garantizar la coherencia en todo el sistema.

* Programación  
Con el diseño eléctrico en su lugar, nos sumergimos en la programación del robot. Desarrollamos el código necesario para controlar los motores, sensores y la comunicación. La colaboración estrecha permitió resolver desafíos de compatibilidad entre hardware y software, asegurando un funcionamiento fluido del robot. Incluyendo así el funcionamiento de los 2 tipos de programación implementados.

* Pruebas finales  
Llegamos a la fase crucial de las pruebas finales, donde pusimos a prueba nuestro robot. Detectamos y corregimos posibles problemas, ajustamos parámetros y optimizamos el rendimiento general. Las pruebas rigurosas garantizaron que nuestro proyecto cumpliera con nuestros objetivos.

## Conclusión:
Durante el desarrollo de JugueTruckBot y a través de la colaboración y la dedicación de cada miembro del equipo, logramos desarrollar un robot funcional que refleja el resultado de nuestras habilidades y conocimientos combinados. Este registro sirve como testimonio de nuestro progreso y aprendizaje a lo largo de este emocionante proyecto. 

```c++
//Line Tracking IO define
#define LT_R !digitalRead(10)
#define LT_M !digitalRead(4)
#define LT_L !digitalRead(2)

#define ENA 5
#define ENB 6
#define IN1 7
#define IN2 8
#define IN3 9
#define IN4 11

int irSense = 3;
int val = 0;

#define carSpeed 150

void forward(){
  analogWrite(ENA, carSpeed);
  analogWrite(ENB, carSpeed);
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
  Serial.println("go forward!");
}

void back(){
  analogWrite(ENA, carSpeed);
  analogWrite(ENB, carSpeed);
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
  Serial.println("go back!");
}

void left(){
  analogWrite(ENA, carSpeed);
  analogWrite(ENB, carSpeed);
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
  Serial.println("go left!");
}

void right(){
  analogWrite(ENA, carSpeed);
  analogWrite(ENB, carSpeed);
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW); 
  Serial.println("go right!");
} 

void stop(){
   digitalWrite(ENA, LOW);
   digitalWrite(ENB, LOW);
   Serial.println("Stop!");
} 

void setup(){
  Serial.begin(9600);
  pinMode(10,INPUT);
  pinMode(4,INPUT);
  pinMode(2,INPUT);
  pinMode(irSense, INPUT);
}

void loop() {
  val = digitalRead(irSense);
  if(val == 0){
    stop();
  }
  else if(LT_M){
    forward();
  }
  else if(LT_R) { 
    right();
    //while(LT_R);                             
  }   
  else if(LT_L) {
    left();
    //while(LT_L);  
  }
}
```

## Imagen en fichero local

![](Logo-urjc.png)


## Imagen en URL

![](https://upload.wikimedia.org/wikipedia/commons/2/2f/CC_BY-SA_3.0.png)
