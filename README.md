# XPATH-1stProject
    A partir del archivo enunciado.xml, accede a los siguientes elementos:
    
####  Ejercicio 1. Haz el listado de todos los nodos o elementos 'Year'. Da 3 formas de hacerlo.
        1. /PubmedArticle//Year
        2. //Year
        3. /PubmedArticle/MedlineCitation//Year

####  Ejercicio 2. Acceda al atributo 'Version' y el atributo 'ValidYN'.
        @Version|//@ValidYN
        
####  Ejercicio 3.  Conteo cuántos 'ForeName' tenemos en total.
        count(//ForeName)

####  Ejercicio 4.  Conteo cuántos 'ForeName' y 'LastName' tenemos en total conjuntamente
        count(//ForeName)+count(//LastName)

####  Ejercicio 5. Acceda a los tres números del 'MedlinePgn'. ¿Cómo se haría para acceder a los dos últimos?
        Para mostrar los tres números primeros: substring(//MedlinePgn,1,3)
        Para mostrar los dos últimos: substring(//MedlinePgn,5,2)

####  Ejercicio 6. Muestras los 'Year' menores de 2000 y mayores de 1500.
        *[Año<2000 y Año>1500]/Año

####  Ejercicio 7. Muestras la media aritmética de los 'Year' menores de 2000 (redondeo por arriba). 
        ceiling(avg(//*[Year<2000]/Year))

####  Ejercicio 8. Da el formato de 'DataCompleted': MM/DD/YYYY (Indicación: "concatenante").
        //DateCompleted/concat(Day,'/',Month,'/',Year)

####  Ejercicio 9. Haz la concatenación de las primeras letras de los valores de 'LastName', 'ForeName' e 'Iniciales'. Ejemplo: Si 'Pepito', 'Fef' 'PF' → el resultado será: 'PFP'.
        //*[LastName|ForeName|Initials]/concat(substring(LastName,1,1),substring(ForeName,1,1),substring(Initials,1,1))

####  Ejercicio 10. Muestre los elementos que tienen el nombre de longitud 8.
        //*[string-length(name())=8]

####  Ejercicio 11. Hizo la traducción de los valores 'Y' a 'N' en los atributos 'ValidYN'.
        //Author/@ValidYN/translate('Y','Y','N')

####  Ejercicio 12. Muestre los autores que están en la posición entre 2 y 3.
        //Author[position()=2 to 3]
