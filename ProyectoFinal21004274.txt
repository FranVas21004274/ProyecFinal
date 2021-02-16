//Variables utiles 
//Precio base de la cotización, en quetzales, lo puede cambiar
var precio_base = 2000

//Valores de los recargos 
var edad_18 = 0.1 // 10%
var edad_25 = 0.2 // 20%
var edad_50 = 0.3 // 30%

var casado_18 = 0.1 // 10%
var casado_25 = 0.2 // 20%
var casado_50 = 0.3 // 30%

var hijos_recargo = 0.2 // 20%
var propiedades_recargo = 0.35 // 35%
var salario_recargo = 0.05 // 5%

//Recargo
var recargo = 0
var recargo_total = 0

//Precio final 
var precio_final = 0


var bienvenido = parseInt(prompt("Bienvenido Aseguradora TK-U, " + "desea reazliar una cotización"))
var nombre = prompt("Ingrese su nombre, por favor")
var edad = prompt("¿Cuantos años tiene? Ingrese solamente números")
if(edad >=18){
  alert("Puede continuar, el cliente es mayor de edad")
}
var casado = prompt("¿Está casado actualmente?", "si/no")
var edad_conyuge
if("SI" == casado.toUpperCase()){
  edad_conyuge = prompt("¿Que edad tiene su esposo/a? ingrese solo números")
}
var edad_numero = parseInt(edad)
var edad_conyuge_numero = 0
//convirtiendo la edad del cónyuge si se esta casado/a
if("SI" == casado.toUpperCase()){
  edad_conyuge_numero = parseInt(edad_conyuge)
}
var hijos = prompt("¿Tiene hijos o hijas?", "si/no")
var cantidad_hijos
if("SI" == hijos.toUpperCase()){
  cantidad_hijos = prompt("¿Cuantos hijos tiene? Ingrese solo números")
}
var cantidad_numero = parseInt(hijos)
var cantidad_hijos_numero = 0

var propiedades = prompt("¿Tiene propiedades?", "si/no")
var cantidad_propiedades
if("SI" == propiedades.toUpperCase()){
  cantidad_propiedades = prompt("¿Cantidad de propiedades? Ingrese solo números")
}
var cantidad_numero = parseInt(propiedades)
var cantidad_propiedades_numero = 0

var salario = prompt("¿Ingrese Salario?")
var cantidad_salario
if("SI" == salario.toUpperCase()){
  cantidad_salario = prompt("¿Ingrese Salario? Ingrese solo números")
}
var cantidad_numero = parseInt(propiedades)
var cantidad_salario_numero = 0

if(edad_numero>=18 && edad_numero<25){
  recargo = precio_base * edad_18
  recargo_total = recargo_total + recargo
}
if(edad_conyuge>=25 && edad_conyuge<50){
  recargo = precio_base * edad_25
  recargo_total = recargo_total + recargo
}
if(edad_numero>=50){
  recargo = precio_base * edad_50
  recargo_total = recargo_total + recargo
}
  else if(edad_conyuge>=18 && edad_conyuge<25){
  recargo = precio_base * edad_18
  recargo_total = recargo_total + recargo
} else if(edad_conyuge>=25 && edad_conyuge<50){
  recargo = precio_base * edad_25
  recargo_total = recargo_total + recargo
} else if(edad_conyuge>=50){
  recargo = precio_base * edad_50
  recargo_total = recargo_total + recargo
} else if (cantidad_hijos_numero){
  recargo = precio_base * hijos_recargo
  recargo_total = recargo_total + recargo
} else if (cantidad_propiedades_numero){
  recargo = precio_base * propiedades_recargo
  recargo_total = recargo_total +recargo
} else if (cantidad_salario_numero){
  recargo = precio_base * salario_recargo
  recargo_total = recargo_total +recargo
}
precio_final = precio_base + recargo_total

alert ("Para el asegurado "+nombre)
alert ("El recargo total sera de: "+recargo_total)
alert ("El precio sera de: "+precio_final)