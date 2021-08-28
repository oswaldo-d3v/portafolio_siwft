# Swift 4 for Absolute Develop Apps for iOS Beginners
## Capitulo 1: Convertirse en una gran desarrolladora de iOS

### Cuestionario

1. ¿Por qué es tan importante dedicar tiempo a los requisitos de sus usuarios? En esta etapa se definen las características que el usuario desea en la App, tener en claro esto ayuda a enfocarnos y no desarrollar cosas que el usuario no necesita.
2. ¿Cuál es la diferencia entre los requisitos de diseño y un algoritmo? Los requisitos de diseño son completamente visuales es decir la paleta de colores que se utilizara, iconos, diseño de pantallas etc. Mientras que un algoritmo es una serie de pasos lógicos que dan solución a un problema.
3. ¿Cuál es la diferencia entre un método y una propiedad? Un método realiza una acción, como podría ser mostrar un mensaje, calcular un numero, solicitar un dato, mientras un propiedad almacena información por ejemplo una cadena, un numero o un objeto complejo.
4. ¿Qué es un error? Un comportamiento no deseado que se produce bajo ciertas circunstancias. 
5. ¿Qué es el estado? Es un indicador, un valor que bajo un contexto nos trasmite cierta información.

### Creación de un algoritmo 

Descripción: Escriba un algoritmo sobre cómo funciona una máquina de refrescos desde el momento en que se inserta una moneda hasta que se dispensa refresco. Suponga que el precio de un refresco es de 80 centavos.

1. La maquina estaría a la espera de monedas asta que se depositen por lo menos 80 centavos 
2. Si el monto es mayor o igual a 80 centavos mostraría un mensaje preguntando que refresco desea
3. Validaría si hay existencias del refresco solicitado 
   1. Si hay existencias entregaría el refresco
   2. Si no hay existencias volveria al paso 2
4. La maquina evaluara el monto ingresado menos 80 centavos
   1. Si el resultado es mayor a 0 entregara el vuelto
5. Volverá al paso 1

### Requisitos de diseño

Descripción: Escriba los requisitos de diseño para una aplicación que ejecutará la máquina de refrescos.

1. El usuario debe de poder ver los refrescos en todo momento
2. El usuario debe de tener un botón claro por cada refresco
3. Se debe de indicar al usuario en donde colocar las monedas 
4. La maquina debe de contar con un espacio para entregar el refresco
5.  La maquina debe de contar con un espacio para entregar el vuelto

## Capitulo 2: Conceptos básicos de programación

### Ejercicio 

Descripción: Amplíe su área de juegos agregando una línea de código que imprima cualquier texto que elija.

```swift
// Miguel Oswaldo Escobar Cuellar
// 25-0729-2017
import Foundation

var str = "Hello, playground"
print(str)

var nombre = "Miguel Oswaldo"
print(nombre)
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/lc2e1_imprimir_mensaje.zip)


## Capitulo 3: Todo se trata de los datos

### Multiplicación de dos numero enteros

```swift
// Miguel Oswaldo Escobar Cuellar
// 25-0729-2017
import Foundation

var num1 = 9
var num2 = 5
var result = num1 * num2

print("\(num1)*\(num2)=\(result)")
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/lc3e1_multiplicando_dos_numeros.zip)

### Cuadrado de un valor decimal

```swift
// Miguel Oswaldo Escobar Cuellar
// 25-0729-2017
import Foundation

var num1 = 9.5
var cuadrado = num1 * num1
print("El cuadrado de \(num1), es: \(cuadrado))")
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/lc3e2_cuadrado_de_un_numero_decimal.zip)

### Resta de dos números decimales con resultado entero

```swift
// Miguel Oswaldo Escobar Cuellar
// 25-0729-2017
import Foundation

var num1 = 9.5
var num2 = 2.1
var result = Int(num1 - num2)

print("\(num1) - \(num2) = \(result)")
```
???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/lc3e3_resta_dos_decimales_igual_un_entero.zip)