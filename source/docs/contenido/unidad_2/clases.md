# Unidad 2 - Programando con Swift

## Clase 1: Agosto 28 del 2021

### Introducción a proyectos command line tool

```swift
// Miguel Oswaldo Escobar Cuellar
// 25-0729-2017
import Foundation

print("Hello World")

var val1 = 0
var val2 = 5
var resultado = val1 + val2

print("El resultado de la operacion es: \(resultado)")

if val2 == 5 {
    print("Es un valor de cinco.")
}


var venta = 600 + val1 + val2 + val1 + val2
```

???+ todo "Descargar"
    Tipo de proyecto: Command line tool<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/28 de agosto.zip)

## Clase 2: Septiembre 4 del 2021

### RandomNumber 2

 Ejercicio: Mejorar programa de libro de texto de nombre RandomNumber, incorporando una funcion para leer, desde teclado lo ingresado por el usuario, reduciendo asi numero de lineas y ootimizando asi como reutilizando codigo, es de criterio de los participantes, incorporar parametros asi como retorno de dato, en la definicion de la funcion

```swift
/* Nombre: Miguel Oswaldo Escbar Cuellar
   Carnet: 25-0729-2017
   Fecha : Septiembre 4, 2021  
*/

import Foundation


var randomNumber = 1
var continueGuessing = true
var keepPlaying = true
var input = ""

func capturaUsuario() -> String
{
    input = NSString(data: FileHandle.standardInput.availableData, encoding: String.Encoding.utf8.rawValue)! as String
    input = input.replacingOccurrences(of: "\n", with: "")
    return input
}

while keepPlaying {
    randomNumber = Int(arc4random_uniform(101))
    print("The random number to guess is: \(randomNumber)")
    while continueGuessing {
        print("Pick a number between 0 and 100.")
        input = capturaUsuario()
        if let userGuess = Int(input){
            if userGuess >= 0 && userGuess <= 100 {
                if userGuess == randomNumber {
                    continueGuessing = false
                    print("Correct number!")
                }
                else if userGuess > randomNumber {
                    print ("Your guess is too high!")
                }
                else {
                    print("Your guess is too low!")
                }
            }
            else {
                print ("No esta en el rango")
            }
        }
        else {
            print("Invalid guess, plese try again.")
        }
    }

    print("Play Again? Y or N")
    input = capturaUsuario()
    
    if input == "N" || input == "n" {
        keepPlaying = false
    }
    continueGuessing = true

}
```

???+ todo "Descargar"
    Tipo de proyecto: Command line tool<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/04 de septiembre.zip)

## Clase 3 : Septiembre 11 del 2021

### Funciones y clases

=== "main.swift"

    ``` swift
    import Foundation

    // Miguel Oswaldo Escobar Cuellar
    // 25-0729-2017

    var objcalculo:calculo=calculo()
    objcalculo.v1 = 5
    objcalculo.v2 = 0
    print(objcalculo.sumar())
    print(objcalculo.restar())
    print(objcalculo.multiplicar())
    print(objcalculo.dividir())
    print(objcalculo.error)

    var objcustomer:customer=customer()
    objcustomer.city = "San Salvador"
    print(objcustomer.city) 
    ```

=== "calculo.swift"
    ``` swift
    import Foundation

    // Miguel Oswaldo Escobar Cuellar
    // 25-0729-2017

    class calculo {
        //Definimos las propiedades
        var v1:Int = 0
        var v2:Int = 0
        var error:String = ""
        
        func sumar() -> Int {
            var resultado:Int = 0
            resultado = v1 + v2
            return resultado
        }
        
        func restar() -> Int {
            var resultado:Int = 0
            resultado = v1 - v2
            return resultado
        }
        
        func multiplicar() -> Int {
            var resultado:Int = 0
            resultado = v1 * v2
            return resultado
        }
        
        func dividir() -> Double {
            var resultado:Double = 0
            if (v2 != 0){
                resultado = Double(v1) / Double(v2)
            } else {
                error="Error: No se puede dividir entre 0"
                resultado = -1
            }
            return resultado
        }
    }

    class customer {
        
        var firsName = ""
        var lastName = ""
        var addressLine1 = ""
        var addressLine2 = ""
        var city = ""
        var state = ""
        var zip = ""
        var phoneNumber = ""
        var emailAddress = ""
        var favoriteGenre = ""
        
    }
    ```

???+ todo "Descargar"
    Tipo de proyecto: Command line tool<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/11 de septiembre.zip)

## Clase 4 : Septiembre 18 del 2021 

### Introduccion a Single View App

```swift
import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var lblmensaje: UILabel!
    @IBOutlet weak var btncambiar: UIButton!
    
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    @IBAction func cambiando(_ sender: UIButton) {        lblmensaje.text="Prueba de mensaje"
    }
}
```

???+ todo "Descargar"
    Tipo de proyecto: Command line tool<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/18 de septiembre.zip)