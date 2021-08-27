# Unidad 1 - Introducción a utilización de MAC y OS X

## Clase 2: Julio 31 del 2021

### Suma de dos números enteros

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017
import Foundation

// Definicion de variables de manera explicita
var str = "Hola mundo!"

// Definicion de variables de manera implicita
var valor1:Int = 3
var valor2:Int = 4
var result:Int = 0

result = valor1 + valor2

print("La suma de \(valor1) mas \(valor2), es igual a: \(result)")

```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c2e1_suma_de_dos_numeros.zip)
    

## Clase 3: Agosto 14 del 2021

### Suma de dos números 

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017
import Foundation

// Declaracion de una constante
let a = 0

var numeroUno = 2
var numeroDos = 3

var totalSuma = numeroUno + numeroDos

numeroUno = numeroUno + 1
numeroDos = numeroDos + 1

totalSuma = numeroUno + numeroDos

print("Total suma: \(totalSuma)")
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c3e1_suma_de_dos_numeros.zip)

### Estructura if

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017
import Foundation

var numero : Int = 5

var valor1 = 4
var valor2 = 5

// Flujo de control
if (valor1 < valor2) { // Operadores logicos: <, >, ==, !=, <=, >=
    print("Si")
} else {
    print("No")
}
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c3e2_etructura_if.zip)

### Calculo de las 4 operaciones básicas

De dos números cualquiera, el usuario decide que operación realizara. Opción de operación 

- S = Suma
- R = Resta
- M = Multiplicación
- D = División

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017

var opcion = "D"

var valor1 = 1.5
var valor2 = 5.0
var result = 0.0

if (opcion == "S") {
    result = valor1 + valor2
}
if (opcion == "R") {
    result = valor1 - valor2
}
if (opcion == "M") {
    result = valor1 * valor2
}
if (opcion == "D") {
    if (valor2 != 0){
        result = valor1 / valor2
    } else {
        print("No se puede dividir entre cero.")
    }
}

print("El resultado de la operacion es: \(result)")
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c3e3_operaciones_basicas.zip)

### Calculo de interés simple 

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017

var I : Double = 0.0
var c : Double = 0.0
var i : Double = 0.0
var t : Double = 0.0


c = 5000.00
i = 12.0
t = 3.0
I = c * ( i / 100 ) * t 

print(I)
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c3e4_interes_simple.zip)

### Estructura repetitiva for

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017

for i in 1...100 {
    print("Iteracion: \(i)")
}
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c3e5_estructura_for.zip)

## Calse 4: Agosto 21 del  2021

### Tabla de multiplicar

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017
import Foundation

var tabla = 5

for i in 1...10 {
  print("\(tabla)x\(i)=\(i*tabla)")
}
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c4e1_tabla_de_multiplicar.zip)

### Calculo de comisión de venta 

| Monto de venta | %S/M. Venta |
| :------------: | :---------: |
| 0 a 300.99 | 2    |
| 301 a 500.99 | 3    |
| 501 a 750.99 | 3.5  |
| 751 a 999.99 | 4    |
| 1000 a mas | 4.5  |

```swift linenums="1"
// Hecho por: Miguel Oswaldo Escobar Cuellar
// Carnet: 25-0729-2017
import Foundation

var venta : Double = 0.0
var comision : Double = 0.0
var porcentaje : Double = 0.0

venta = 175.45

if (venta <= 300.99) {
    porcentaje = 0.02
}
if (venta >= 301 && venta <= 500.99) {
    porcentaje = 0.03
}
if (venta >= 501 && venta <= 750.99) {
    porcentaje = 0.035
}
if (venta >= 751 && venta <= 999.99) {
    porcentaje = 0.04
}
if (venta >= 1000) {
    porcentaje = 0.045
}

comision = venta * porcentaje

print("Por una venta de \(venta) la comision es de \(comision)")
```

???+ todo "Descargar"
    Tipo de proyecto: Swift Playground<br>Creado en: online.swiftplayground.run<br>[Descargar proyecto](/../src/unidad1/c4e2_calculo_de_comision_por_venta.zip)