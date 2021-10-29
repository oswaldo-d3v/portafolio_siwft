# Unidad 3 - Programación Orientada a Objetos con Swift
## Clase 1: Septiembre 25 del 2021
### Uso de UISegmentedControl

```swift
import UIKit

class ViewController: UIViewController {
    

    @IBOutlet weak var txtvalor1: UITextField!
    @IBOutlet weak var txtvalor2: UITextField!
    @IBOutlet weak var lblresultado: UILabel!

    @IBOutlet weak var btncalcular: UIButton!
    @IBOutlet weak var segopciones: UISegmentedControl!
    @IBOutlet weak var btnsegmento: UIButton!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    @IBAction func calcular(_ sender: UIButton) {
        var vl_valor1:String=""
        var vl_valor2:String=""
        var vl_resultado:Double=0.0
        var opcionselec:Int=0
        vl_valor1=txtvalor1.text!
        vl_valor2=txtvalor2.text!
        opcionselec=segopciones.selectedSegmentIndex
        
        //Suma
        if opcionselec==0{
            vl_resultado = Double(vl_valor1)! + Double(vl_valor2)!
        }
        
        //Resta
        if opcionselec==1{
            vl_resultado = Double(vl_valor1)! - Double(vl_valor2)!
        }
        
        //Multiplicacion
        if opcionselec==2{
            vl_resultado = Double(vl_valor1)! * Double(vl_valor2)!
        }
        
        //Division
        if opcionselec==3{
            vl_resultado = Double(vl_valor1)! / Double(vl_valor2)!
        }
        
        lblresultado.text=String(vl_resultado)
    }
}
```

![](/../src/unidad3/e1.png)

???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad3/clase20210925a.zip)

## Clase 2: Octubre 9 del 2021
### Uso de UIPickerView
```swift
import UIKit

class ViewController: UIViewController, UIPickerViewDelegate, UIPickerViewDataSource {

    @IBOutlet weak var pickerView: UIPickerView!
    @IBOutlet weak var myLabel: UILabel!
    
    let pickerData = ["Toyota", "Ford", "Daewoo", "Nissan"]
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        pickerView.dataSource=self
        pickerView.delegate=self
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    //MARK: - Objeto PickerView seccion datasource y delegete
    //MARK: DataSources
    func numberOfComponents(in pickerView: UIPickerView) -> Int {
        return 1
    }
    
    func pickerView(_ pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
        return pickerData.count
    }
    
    //MARK: Delegates
    func pickerView(_ pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String? {
        return pickerData[row]
    }
    
    func pickerView(_ pickerView: UIPickerView, didSelectRow row: Int, inComponent component: Int) {
        myLabel.text=pickerData[row]
    }

}
```

![](/../src/unidad3/e2.png)

???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad3/clase20211009a.zip)

### Uso de UIPickerView 2
=== "ViewController.swift"
    ```swift
    import UIKit


    class ViewController: UIViewController, UIPickerViewDelegate, UIPickerViewDataSource {

        @IBOutlet weak var txtSalario: UITextField!
        @IBOutlet weak var pickerPago: UIPickerView!
        @IBOutlet weak var lblImpuesto: UILabel!
        @IBOutlet weak var lblopcion: UILabel!
        
        var objimpuestoRenta=impuestoRenta()
        
        let pickerData = ["Mensual", "Quincenal", "Semanal" ]
        
        override func viewDidLoad() {
            super.viewDidLoad()
            // Do any additional setup after loading the view, typically from a nib.
            pickerPago.dataSource=self
            pickerPago.delegate=self
        }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
        
        @IBAction func calcularImpuesto(_ sender: UIButton) {
            var resultado:Double=0.00
            var vsalarioD:Double=0.00
            var vopcion:String=""
            var vsalario:String=""
            vsalario=txtSalario.text!
            vsalarioD=Double(vsalario)!
            //var vsalario:NSString=""
            //vsalario=txtSalario.text as! NSString
            vopcion=lblopcion.text!
            
            
            if vopcion == "Mensual"{
                resultado=objimpuestoRenta.Mensual(pvalor: vsalarioD)
            }
            
            if vopcion == "Quincenal"{
                resultado=objimpuestoRenta.Quincenal(pvalor: vsalarioD)
            }
            
            if vopcion == "Semanal"{
                resultado=objimpuestoRenta.Semanal(pvalor: vsalarioD)
            }
            lblImpuesto.text = String(resultado)
            //resultado=objimpuestoRenta.
        }
        
        
        //MARK:Datasources
        func numberOfComponents(in pickerView: UIPickerView) -> Int {
            return 1
        }
        
        func pickerView(_ pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
            return pickerData.count
        }
        
        func pickerView(_ pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String? {
            return pickerData[row]
        }
        
        func pickerView(_ pickerView: UIPickerView, didSelectRow row: Int, inComponent component: Int) {
            lblopcion.text = pickerData[row]
        }
    }
    ```
=== "impuestoRenta.swift"
    ```swift
    import Foundation
    // Metodo para calculo de renta
    // para Mensual
    // para Quincenal
    // para Semanal

    class impuestoRenta {

        func Semanal(pvalor:Double) -> Double{
            var impuesto:Double=0.00
            if(pvalor >= 0.01 && pvalor <= 118.00){
                impuesto=0.00
            }
            if(pvalor >= 118.01 && pvalor <= 223.81){
                impuesto=((pvalor - 118.00) * 0.10) + 4.42
            }
            if(pvalor >= 223.82 && pvalor <= 509.52){
                impuesto=((pvalor - 223.81) * 0.20) + 15.00
            }
            if(pvalor >= 509.53){
                impuesto=((pvalor - 509.52) * 0.30) + 72.14
            }
            return impuesto
        }

        func Quincenal(pvalor:Double) -> Double{
            var impuesto:Double=0.00
            if(pvalor >= 0.01 && pvalor <= 236.00){
                impuesto=0.00
            }
            if(pvalor >= 236.01 && pvalor <= 447.62){
                impuesto=((pvalor - 236.00) * 0.10) + 8.83
            }
            if(pvalor >= 447.63 && pvalor <= 1019.05){
                impuesto=((pvalor - 447.62) * 0.20) + 30.00
            }
            if(pvalor >= 1019.06){
                impuesto=((pvalor - 1019.05) * 0.30) + 144.28
            }
            return impuesto
        }

        func Mensual(pvalor:Double) -> Double{
            var impuesto:Double=0.00
            if(pvalor >= 0.01 && pvalor <= 472.00){
                impuesto=0.00
            }
            if(pvalor >= 472.01 && pvalor <= 895.24){
                impuesto=((pvalor - 472.00) * 0.10) + 17.67
            }
            if(pvalor >= 895.25 && pvalor <= 2038.10){
                impuesto=((pvalor - 895.24) * 0.20) + 60.00
            }
            if(pvalor >= 2038.11){
                impuesto=((pvalor - 2038.10) * 0.30) + 288.57
            }
            return impuesto
        }
    }
    ```

![](/../src/unidad3/e3.png)

???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad3/clase20211009b.zip)

## Clase 3: Octubre 16 del 2021
### Multiples pantallas

=== "ViewController.swift"

    ```swift
    import UIKit

    class ViewController: UIViewController {
        @IBOutlet weak var lbletiqueta1: UILabel!
        
        override func viewDidLoad() {
            super.viewDidLoad()
            lbletiqueta1.text="Ventana 1"
        }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
    }
    ```

=== "tercera.swift"
    ```swift
    import UIKit

    class tercera: UIViewController {

        @IBOutlet weak var lbletiqueta3: UILabel!
        
        override func viewDidLoad() {
            super.viewDidLoad()

            // Do any additional setup after loading the view.
            lbletiqueta3.text="Ventana 3"
        }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
    }
    ```

=== "segunda.swift"
    ```swift
    import UIKit

    class segunda: UIViewController {

        
        @IBOutlet weak var lbletiqueta2: UILabel!
        override func viewDidLoad() {
            super.viewDidLoad()

            // Do any additional setup after loading the view.
            
            lbletiqueta2.text="Ventana 2"
        }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }

    }
    ```
![](/../src/unidad3/e4.png)

???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad3/clase20211016.zip)

### Multiples pantallas 2

=== "ViewController.swift"
    ```swift
    import UIKit

    class ViewController: UIViewController {
        
        @IBOutlet weak var txtnombre: UITextField!
        
        var dato2:String="None"
        
        
        override func viewDidLoad() {
            super.viewDidLoad()
            // Do any additional setup after loading the view, typically from a nib.
            txtnombre.text=dato2    }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }

        override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
            let viewController2 = segue.destination as! ViewController2
            viewController2.dato1 = txtnombre.text!
        }
    }
    ```

=== "ViewController2.swift"
    ```swift
    import UIKit

    class ViewController2: UIViewController {

        @IBOutlet weak var lblnombre: UILabel!
        var dato1:String="None-change"
        
        override func viewDidLoad() {
            super.viewDidLoad()
            // Do any additional setup after loading the view.
            lblnombre.text=dato1
        }

        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
        

        
        // MARK: - Navigation

        // In a storyboard-based application, you will often want to do a little preparation before navigation
        override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
            // Get the new view controller using segue.destinationViewController.
            // Pass the selected object to the new view controller.
            let viewController = segue.destination as! ViewController
            viewController.dato2="De ventana 2"
        }
    }
    ```
![](/../src/unidad3/e5.png)


???+ todo "Descargar"
    Tipo de proyecto: Single View App<br>Creado en: Xcode 9.4<br>[Descargar proyecto](/../src/unidad3/clase20211016b.zip)
