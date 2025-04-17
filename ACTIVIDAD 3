/******************************************************************************

Autor: Briseyda Ramirez Garcia
Fecha: 15 de abril de 2025
Programa en C++ que realiza el calculo del RFC de acuerdo con las reglas del SAT 

*******************************************************************************/
#include <iostream> //Biblioteca estandar para entradas y salidas en C++
#include <string> //Biblioteca para manipulacion de cadenas (std::string)

// Funcion para obtener la primera vocal interna del apellido paterno
char obtenerPrimeraVocalInterna(const std::string& str) {
    // Recorremos la cadena desde el segundo caracter (indice 1) hasta el final
    for (size_t i=1; i < str.length(); ++i ){
        char c = str[i]; // Se obtiene el caracter actual de la cadena
        
        // Se verifica si el caracter es una vocal mayuscula
        if (c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U')
        return c; // Regresa la primera vocar interna encontrada
    }
    return 'x'; // Si no se encuentra ninguna vocal interna, se devuelve una x
}

// Funcion para calcular el RFC con base en los datos personales
std::string calcularRFC(const std::string& nombre, const std::string& apellidoPaterno, const std::string& apellidoMaterno, const std::string& fechaNacimiento){
    std::string rfc; //Variable para almacenar el RFC resultante
    
    // Se obtiene la primera letra del apellido paterno
    char letrainicial = apellidoPaterno[0];
    
    // Se obtiene la primera vocal interna del apellido paterno
    char PrimeraVocalInterna = obtenerPrimeraVocalInterna(apellidoPaterno);
    
    // Se obtiene la inicial del apellido materno, si no existe se usa una X
    char inicialApellidoMaterno = (!apellidoMaterno.empty()) ? apellidoMaterno[0] : 'X';
    
    // Se obtiene la inical del nombre
    char inicialNombre = nombre[0];
    
    // Se obtiene los ultimos dos digitos del año de nacimiento (posicion 2 y 3)
    std::string anio = fechaNacimiento.substr(2,2);
    
    // Se obtiene el mes de nacimiento (posicion 5 y 6)
    std::string mes = fechaNacimiento.substr(5,2);
    
    // Se obtiene el dia de nacimiento (posicion 8 y 9)
    std::string dia = fechaNacimiento.substr(8,2);
    
    // Se construye el RFC concatenando los valores obtenidos
    rfc = letrainicial;
    rfc += PrimeraVocalInterna;
    rfc += inicialApellidoMaterno;
    rfc += inicialNombre;
    rfc += anio;
    rfc += mes;
    rfc += dia;
    
    return rfc; // Se obtiene el RFC generado
    
}

int main (){
    std::string nombre, apellidoPaterno, apellidoMaterno, fechaNacimiento;
    
    // Solicita el nombre del usuario
    std::cout << "Ingrese el nombre: ";
    std::getline(std::cin, nombre); // Captura toda la linea del nombre
    
    // Solicita el apellido paterno
    std::cout << "Ingrese el apellido paterno: ";
    std::getline(std::cin, apellidoPaterno);
    
    // Solicita el apellido materno, permitiendo que el usuario deje vacio
    std::cout << "Ingrese el apellido materno (Si no tiene presione enter): ";
    std::getline(std::cin, apellidoMaterno);
    
    // Se solicita la fecha de nacimiento en formato YYYY-MM-DD
    std::cout << "Ingrese la fecha de nacimiento (YYYY-MM-DD): ";
    std::getline(std::cin, fechaNacimiento);
    
    // Se calcula el RFC utilizando la funcion calcular RFC
    std::string rfc = calcularRFC(nombre, apellidoPaterno, apellidoMaterno, fechaNacimiento);
    
    // S e muestra el RFC generado
    std::cout << "RFC: " << rfc << std::endl;
    
    return 0; // Finaliza el programa
}
