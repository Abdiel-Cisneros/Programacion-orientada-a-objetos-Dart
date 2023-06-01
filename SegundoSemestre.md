# Actividades Segundo Semestre
![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/UdeC_2L_Blanco.png)
### Jiménez Cisneros Ángel Abdiel ICI 2°B







#### 19 / ABRIL / 2023
---

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/19-04-2023%20DDC.jpg)

#### main.dart

````
void main(List<String> args) {
  var e1 = Estudiante();
  Estudiante e2 = Estudiante();
  e1.nombre = "Juan";
  e1.aNacimiento = 1990;
  e1.reporte(2023);

  e2.nombre = "Pedro";
  e2.aNacimiento = 1991;
  e2.reporte(2022);
}

class Estudiante {
  String nombre = "";
  int? aNacimiento;
  void reporte(int aActual) {
    print("Nombre: ${nombre}");
    print("Edad: ${aActual - aNacimiento!}");
  }
}

````







#### 20 / ABRIL / 2023
---
![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/20-04-2023%20DDC.jpg)

#### main.dart

````
import 'animal.dart';

void main(List<String> args) {
  Animal a1 = new Animal("Perro", "Guau");
  Animal a2 = new Animal("Gato","Miau"); */

 /*
  a1._name = 'Perro';
  a1._sonido = 'Guau';
  a2._name = 'Gato';
  a2._sonido = 'Miau';
 */
 
  Animal a3 = new Animal('Perro', 'Guau');

  print(a3.name);
  print(a3.sonido);
  }
````

````

import 'animal.dart';

void main(List<String> args) {
  Persona p1 = new Persona('Juan', 1998);
  Persona p2 = new Persona('Toño', 1997);

  p1.imprimirEdad(2023);
  p2.imprimirEdad(2023);
}
````
---
###### animal.Dart
````
class Animal {
  String? name;
  String? sonido;
  Animal(String name, String sonido) {
    print('Constructor de Animal');
    this.name = name;
    this.sonido = sonido;
  }
}

// Trabajo de clase

class Persona {
  String? nombre;
  int? aNacimiento;
  Persona(String nombre, int aNacimiento) {
    this.nombre = nombre;
    this.aNacimiento = aNacimiento;
  }

  void imprimirEdad(int aActual) {
    print(
        'La edad de ${this.nombre} tiene ${aActual - this.aNacimiento!} años');
  }
}

````
---







#### "26" /ABRIL / 2023

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/26-04-2023%20DDC.jpg)

#### main.dart
````
/*
Escriba un programa que tenga una clase Figura
que tenga dos propiedades: base, altura
y dos métodos que calculen el área y el perímetro
de un rectángulo
*/
import 'figura.dart';

/* void main(List<String> args) {
  Figura f1 = Figura(10, 20);

  print('Base: ${f1.base}');
  print('Altura: ${f1.altura}');
  print('Altura: ${f1.area()}');
}
 */

void main(List<String> args) {
  var rectangulo = Figura.rectangulo(4, 5);
  Figura cuadrado = Figura.cuadrado(4);

  print('Área Rectangulo: ${rectangulo.areaRectangulo()}');
  print('Área Cuadrado: ${rectangulo.areaCuadrado()}');

  print('Área Rectangulo: ${cuadrado.areaRectangulo()}');
  print('Área Cuadrado: ${cuadrado.areaCuadrado()}');
}

````

#### figura.dart

````
/* class Figura {
  int? base;
  int? altura; */

//constructor 1

/*  Figura(int b, int a) {
    base = b;
    altura = a;
  } */

//constructor 2

/* Figura(int base, int altura) {
    this.base = base;
    this.altura = altura;
  } */

//constructor 3
//Figura(this.base, this.altura);

//constructor 4
/* Figura(int b, int a)
      : base = b,
        altura = a;

  int area() {
    return base! * altura!;
  } */

class Figura {
  int? base;
  int? altura;

  Figura.rectangulo(this.base, this.altura);
  Figura.cuadrado(this.base);

  int areaRectangulo() {
    if (altura == null || base == null) {
      print('No se puede calcular');
      return 0;
    }
    return base! * altura!;
  }

  int areaCuadrado() {
    int res = 0;
    if (base == null) {
      print("No se puede calcular el área de un cuadrado con altura nula");
    } else {
      res = base! * base!;
    }
    return res;
  }
}

````



---

#### 27 / ABRIL / 2023
---

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/27-04-2023%20main1.jpg)

#### main.dart  (main1)

````
import 'shape.dart';

void main(List<String> args) {
  Shape f1 = Shape(10, 5);
  print(f1.getArea());
  f1.base = 15;
  f1.altura = 10;
  print(f1.getArea());
  print(
    '''El area del rectángulo con bse ${f1.getArea()} y altura ${f1.altura}
       es ${f1.getArea()}''',
  );
}

````

#### shape.dart  (Subclase main1)

````
class Shape {
  int? _base;
  int? _altura;

  Shape(this._base, this._altura);

  int getArea() {
    return _calcularArea();
  }

  int _calcularArea() {
    return _base! * _altura!;
  }

  void set Base(int base) {
    _base = base;
  }

//setters
  void set base(int? base) => base = base;
  void set altura(int? altura) => altura = altura;
//getters
  int? get base => _base;
}
````
---



#### main2.dart (main2)

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/27-04-2023%20main2.jpg)

````
import 'Vehicle.dart';

void main(List<String> args) {
  Vehicle v1 = Vehicle(
    'Totoya',
    'Corolla',
    'Rojo',
    'Automatico',
  );

  Vehicle v2 = Vehicle(
    'Honda',
    'Civic',
    'Azul',
    'Manual',
  );

  List<Vehicle> vehicles = [v1, v2];

  vehicles.forEach(
    (vehicle) => vehicle.showVehicle(),
  );
}

````

#### Vehicle.dart

````
class Vehicle {
  String? _brand;
  String? _name;
  String? _color;
  String? _transmition;

  Vehicle(
    this._brand,
    this._name,
    this._color,
    this._transmition,
  );

  void set brand(String brand) => this._brand = brand;
  void set name(String name) => this._name = name;
  void set color(String color) => this._color = color;
  void set transmition(String transmition) => this._transmition = transmition;

  String get brand => this._brand;
  String get name => this._name;
  String get color => this._color;
  String get transmition => this._transmition;

  void showVehicle() {
    print(
      '''\n
    Marca: ${this.brand}
    Nombre: ${this.name}
    Color: ${this.color}
    Transmision: ${this.transmition}
    ''',
    );
  }
}

````

























#### 03 / MAYO / 2023
---
![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/03-05-2023%20DDC.jpg)

#### main.dart

````

/* 
void main(List<String> args) {
  Mueble m1 = Mueble();
  print("Propiedad de instancia m1: ${m1.counter}");
  print("Propiedad de clase mueble: ${Mueble.counterStatic}");
  print("-" * 28);
  Mueble m2 = Mueble();
  print("Propiedad de instancia m2: ${m2.counter}");
  print("Propiedad de clase Mueble: ${Mueble.counterStatic}");
//M1 es una instancia de la clase Mueble
} */

void main(List<String> args) {
  Mueble m1 = Mueble();
  m1.showCounter();
  Mueble.showCounterStatic();
  print("-" * 28);
  Mueble m2 = Mueble();
  m2.showCounter();
  Mueble.showCounterStatic();
//M1 es una instancia de la clase Mueble
}

class Mueble {
  // Propiedad de instancia
  int counter = 0;

  // Propiedad de clase
  static int counterStatic = 0;

  Mueble() {
    counter++;
    counterStatic++;
  }

  // Método de instancia
  void showCounter() {
    print("Propiedad de instancia: $counter");
  }

  // Método de clase
  static void showCounterStatic() {
    print("Propiedad de clase: $counterStatic");
  }
}
````

---

#### granja.dart

````
void main(List<String> args) {
  Animal a1 = Animal("Vaca", 10);
  a1.showAnimal();
  Animal.showAnimalStatic();
  print("-" * 28);
  Animal a2 = Animal("Cerdo", 20);
  a2.showAnimal();
  Animal.showAnimalStatic();
  List<Animal> animales = [a1, a2];
  int suma = 0;
  animales.forEach((element) {
    suma += element.cantidad;
  });
  print("Total de animales: $suma");
}

class Animal {
  //Propiedad de instancia
  String tipoAnimal;
  int cantidad;

  //Propiedad de clase
  static int counterStatic = 0;

  Animal(this.tipoAnimal, this.cantidad) {
    counterStatic++;
  }
  //Método de instancia
  void showAnimal() {
    print("Tipo de animal: $tipoAnimal");
    print("Cantidad: $cantidad");
  }

  // Metodo de clase
  static void showAnimalStatic() {
    print("Cantidad de tipos de animales: $counterStatic");
  }
}
````










#### 04 / MAYO / 2023
---

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/04-05-2023%20DDC.jpg)

#### main.dart

````
import 'caballo.dart';
import 'pato.dart';
import 'animal.dart';
import 'vaca.dart';

void main() {
  Pato pato1 = Pato('Pekines', 10, 'Curvo');
  /* pato1.breed = 'Pekines';
  pato1.quantity = 10;
  pato1.tipo_pico = 'Curvo'; */
  pato1.showProperties();
  print('-' * 28);
  Animal a1 = Animal("Animal", 100);
  /* a1.breed = 'Animal';
  a1.quantity = 100; */

  a1.showProperties();
  print('-' * 28);
  Caballo c1 = Caballo("Azteca", 50, "Café");
  /* ca1.breed = 'Azteca';
  ca1.quantity = 12;
  ca1.color_crin = 'Café'; */
  c1.showProperties();
  c1.quantity = 100;
  print(c1.quantity);
  print('-' * 28);
  c1.showProperties();
  Vaca vaca1 = Vaca('Holstein', 30, 'Negras');
  /* vaca1.breed = 'Holstein';
  vaca1.quantity = 30;
  vaca1.color_manchas = 'Negras'; */
  vaca1.showProperties();
  vaca1.quantity = 40;
}

````
---

#### Clase padre: Animal

````
class Animal {
  String? _breed;
  int? _quantity;
  //Propiedades

  Animal(this._breed, this._quantity);

  String? get breed => _breed;
  int? get quantity => _quantity;

  set breed(String? breed) => _breed = breed;
  set quantity(int? quantity) => _quantity = quantity;

  void showProperties() {
    print('breed: $_breed');
    print('Quantity: $_quantity');
  }
}
````
---

#### Subclase Caballo

````
import 'animal.dart';

class Caballo extends Animal {
  String? _color_crin;

  /*  Caballo(this.color_crin, String? breed, int? quantity)
      : super(breed, quantity); */

  Caballo(super._breed, super._quantity, this._color_crin);

//Super trae directamente las propiedades de la clase Animal
// Se utiliza this para referir a la propiedad del caballo

  // String? melena;
  @override
  void showProperties() {
    super.showProperties();
    print('Color de la melena: $_color_crin');
  }
}

````
---

#### Subclase Pato

````
import 'animal.dart';

class Pato extends Animal {
  String? _tipo_pico;

  Pato(super._breed, super._quantity, this._tipo_pico);

  @override
  void showProperties() {
    super.showProperties();
    print('Tipo de pico: $_tipo_pico');
  }
}

````
---

#### Subclase Vaca

````
import 'animal.dart';

class Vaca extends Animal {
  String? _color_manchas;

  Vaca(super._breed, super._quantity, this._color_manchas);

  @override
  void showProperties() {
    super.showProperties();
    print('Color de manchas: $_color_manchas');
  }
}

````







#### 17 / MAYO / 2023
---

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/17-05-2023.jpg)


#### main.dart

````
void main(List<String> args) {
  final Vehiculo vehiculo = Vehiculo("Rojo", 100);
  Vehiculo.showVehiculo();
  print("Maxima velocidad: ${Vehiculo.maxVelocidad()}");

  final Carro carro = Carro("Azul", 200, "Totoya");
  carro.showVehiculo();
  print("Maxima velocidad: ${Vehiculo.maxVelocidad()}");

  final Carro carroTipo = Carro.tipo("Azul", 200, "Totoya", "Sedan");
  carroTipo.showTipo();
  print("---------");
  carroTipo.showTipo2();
  print("Maxima velocidad: ${carroTipo.maxVelocidad()}");
}

class Vehiculo {
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad) {
    print("Constructor padre Vehiculo");
  }
//Fat arrow =>
  set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = _velocidad;

  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! * 2;

  void showVehiculo() {
    print("Color: $_color");
    print("Velocidad: $_velocidad");
  }
}

class Carro extends Vehiculo {
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca, this._tipo) {
    print("Constructor hijo carro");
  }

  Carro.tipo(super._color, super._velocidad, this._marca, this._tipo) {
    print("Constructor nombrado tipo hijo carro");
  }

  @override
  void showVehiculo() {
    super.showVehiculo();
    print("Marca: $_marca");
  }

  void showTipo() {
    super.showVehiculo();
    print("Marca: $_marca");
    print("Marca: $_tipo");
  }

  void showTipo2() {
    this.showVehiculo();
    print("Tipo: $_tipo");
  }
}

````

#### abstract.dart

````
void main(List<String> args) {
  final Carro jeep = Carro("Rojo", 100, "Jeep", "SUV");
  jeep.showVehiculo();
  jeep.maxVelocidad();

  final Motocicleta yamaha = Motocicleta("Azul", 200, "r6");
  yamaha.showVehiculo();
  yamaha.maxVelocidad();
}

//Las clases abstractas no se pueden instanciar
/* Las clases abstractas se pueden heredar */
abstract class Vehiculo {
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad) {
    print("Constructor padre Vehiculo");
  }

  set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;

  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! * 2;

  void showVehiculo() {
    print("Color: $_color");
    print("Velocidad: $_velocidad");
  }

  // Instancia es una copia de la clase
}

class Carro extends Vehiculo {
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca, this._tipo) {
    print("Constructor hijo Carro");
  }

  @override
  void showVehiculo() {
    super.showVehiculo();
    print("Marca: $_marca");
    print("Tipo: $_tipo");
  }
}

class Motocicleta extends Vehiculo {
  String? _marca;
  Motocicleta(
    super._color,
    super._velocidad,
    this._marca,
  ) {
    print("Constructor hijo Motocicleta");
  }

  @override
  void showVehiculo() {
    super.showVehiculo();
    print("Marca: $_marca");
  }
}

````














#### 18 / MAYO / 2023
---

![image](https://github.com/Abdiel-Cisneros/Programacion-orientada-a-objetos-Dart/blob/main/18-05-2023%20DDC.jpg)

#### main.dart "Mixins"

````
void main(List<String> args) {
  Dolphin flippy = Dolphin();
  flippy.Swim();
}

class Animal {
  Animal() {
    print('Animal constructor');
  }
}

class Mammal extends Animal {
  Mammal() {
    print('Mammal constructor');
  }
}

class Bird extends Animal {
  Bird() {
    print('Bird constructor');
  }
}

class Fish extends Animal {
  Fish() {
    print('Fish constructor');
  }
}

abstract class Swimmer {
  void Swim() {
    print('Swiming');
  }
}

class Dolphin extends Animal with Swimmer {
  Dolphin() : super() {
    print('Dolphin constructor');
  }
}

````
---

#### interfaces.dart

````
//? Interfaces
//* Interfaces are a way to define a contract on a classs
//* Dart does not have syntax for declaring interfaces
//* Allowed code reutilization
//* Pretend simiulate multiple inheritance

void main(List<String> args) {
  ControlRemoto control = ControlRemoto();
  control.subirVolumen();
  control.bajarVolumen();

  Television tv = Television();
  tv.subirVolumen();
  tv.bajarVolumen();
}

class ControlRemoto {
  void subirVolumen() {
    //print('Subir Volumen');
  }

  void bajarVolumen() {
    //print('Bajar Volumen');
  }
}

class Television implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen de la TV');
  }

  @override
  void bajarVolumen() {
    print('Subir Volumen de la TV');
  }
}

class Ipod implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen de la TV');
  }

  @override
  void bajarVolumen() {
    print('Subir Volumen de la TV');
  }
}

class Radio implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen de la TV');
  }

  @override
  void bajarVolumen() {
    print('Subir Volumen de la TV');
  }
}

````
