# Swift 4 for Absolute Develop Apps for iOS Beginners
## Capitulo 4: Tomando decisiones, Programa Flujo y diseño de aplicaciones
**Ejercicios:**

* Extienda la aplicación del generador de números aleatorios para imprimir en la consola cuántas veces el usuario
adivinado antes de adivinar el número aleatorio correcto.
* Extienda la aplicación del generador de números aleatorios para imprimir en la consola cuántas veces el usuario
jugó la aplicación. Imprima este valor en la consola cuando el usuario salga de la aplicación.

```swift
import Foundation

var randomNumber = 1
var continueGuessing = true
var keepPlaying = true
var input = ""

var intentos = 0
var partidas = 0

while keepPlaying {
    partidas = partidas + 1
    randomNumber = Int(arc4random_uniform(101))
    print("El numero aleatorio es: \(randomNumber)")
    while continueGuessing {
        print("Adivina el numero entre 0 y 100: ")
        input = NSString(data: FileHandle.standardInput.availableData, encoding: String.Encoding.utf8.rawValue)! as String
        input = input.replacingOccurrences(of: "\n", with: "", options: NSString.CompareOptions.literal, range: nil)
        if let userGuess = Int(input) {
            intentos = intentos + 1
            if userGuess == randomNumber {
                continueGuessing = false
                print("Correcto!")
                print("Numero de intentos \(intentos)")
                intentos = 0
            } else if userGuess < randomNumber {
                print("Es un numero mayor")
            } else {
                print("Es un numero menor")
            }
            
        } else {
            print("El valor ingresado no es valido")
        }
    }
    
    print("Seguir jugando? S/N")
    input = NSString(data: FileHandle.standardInput.availableData, encoding: String.Encoding.utf8.rawValue)! as String
    input = input.replacingOccurrences(of: "\n", with: "", options: NSString.CompareOptions.literal, range: nil)
    
    if input == "N" || input == "n" {
        keepPlaying = false
        print("Partidas jugadas \(partidas)")
    }
    continueGuessing = true
}
```

![](/../src/unidad2/Screenshot_1.png)

???+ todo "Descargar"
    Tipo de proyecto: Command line tool<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/Capitulo4.zip)

## Capitulo 5: Programación orientada a objetos con Swift

**Ejercicios:**

* Intente crear los archivos de clase para el resto de las clases que asignó.
* Mapee una clase de autor. Elija el tipo de información que necesitaría almacenar sobre
un autor.

Para los atrevidos y avanzados:

* Intente crear una superclase llamada PrintedMaterial Map con las propiedades que una clase
podría tener.
* Crear clases para los otros tipos de materiales impresos que pueda tener una tienda.

=== "Book.swift"

    ``` swift
    import Foundation

    class Book {
        var Autor = ""
        var Publisher = ""
        var Genre = ""
        var YearPublished = ""
        var NumberOfPages = ""
        var Edition = ""
        var Price = ""
    }
    ```

=== "BookStore.swift"

    ``` swift
    import Foundation

    class BookStore {
        var Name = ""
        var Address1 = ""
        var Address2 = ""
        var City = ""
        var State = ""
        var Zip = ""
        var PhoneNumber = ""
        var Logo = ""
    }
    ```
=== "Customer.swift"

    ``` swift
    import Foundation

    class Custumer : NSObject {
        var firstName = ""
        var lastName = ""
        var addressLine1 = ""
        var addressLine2 = ""
        var city = ""
        var state = ""
        var zip = ""
        var phoneNumber = ""
        var emailAddress = ""
        var favoriteGenre = ""
        
        func listPurchaseHistory() -> [String] {
            return ["Purchase 1", "Purchase 2"]
        }    
    }
    ```

=== "Scale.swift"

    ``` swift
    import Foundation

    class Sale {
        var Custumer = ""
        var Book = ""
        var Date = ""
        var Time = ""
        var Amount = ""
        var PaymentType = ""
    }
    ```

=== "Madera.swift"

    ``` swift
    import Foundation

    class Madera {
        
    }
    ```

=== "Mesa.swift"

    ``` swift
    import Foundation

    class Mesa {
        
    }
    ```

???+ todo "Descargar"
    Tipo de proyecto: Master-Detail App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/Capitulo5.zip)

## Capitulo 6 : Aprendiendo Swift y Xcode
 ** Ejercicios: ** 

* Borre el texto predeterminado de "Etiqueta" en el programa y vuelva a ejecutar el ejemplo.

* Cambie el tamaño del objeto Etiqueta en la interfaz para que sea más pequeño en ancho. Como hace eso
afectar su mensaje de texto?

* Elimine la conexión de salida de referencia de la etiqueta y vuelva a ejecutar el proyecto. ¿Lo que sucede?

* Si crees que tienes el truco de esto, agrega un nuevo botón y etiqueta a la

* Objeto ViewController y a la interfaz. Cambie la etiqueta para que no muestre su
nombre para mostrar algo más.

```swift
import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var nameLabel: UILabel!
    
    @IBAction func showName(_ sender: UIButton) {
        nameLabel.text = "My Name is Brad"
    }
    
    
    @IBOutlet weak var label2: UILabel!
    
    @IBAction func newButton(_ sender: UIButton) {
        label2.text = "Hola Mundo"
    }
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
}
```
![](/../src/unidad2/Screenshot_2.png)

???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad2/Capitulo6.zip)
