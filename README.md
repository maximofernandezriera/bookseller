# Kata del bookseller

* https://www.codewars.com/kata/54dc6f5a224c26032800005c

##  OBJETIVO: Un librero que tiene muchos libros clasificados en 26 categorías etiquetadas A, B, C, …, Z. Cada libro tiene un código de al menos 3 caracteres. El primer carácter de un código es una letra mayúscula que define la categoría del libro. En la lista de existencias del librero, cada código va seguido de un espacio y de un número entero positivo, que indica la cantidad de libros de este código en stock

### Almacenamiento de datos: Se utiliza un HashMap para almacenar el stock por categoría. Esto permite un acceso más rápido a los datos mediante claves.

### Verificación de existencia: Se utiliza la función contiene la clave del HashMap para verificar si una categoría ya existe en el HashMap.

###entajas de usar HashMap:

### Eficiencia: Buscar y acceder a elementos en un HashMap es generalmente más rápido que en un array, especialmente cuando se manejan grandes cantidades de datos.

#### Claridad: El uso de un HashMap para asociar categorías con cantidades puede hacer el código más legible y fácil de entender.

# PSEUDOCÓDIGO

        Función stockList(listaDeCodigos, listaDeCategorias):
        
          SI listaDeCodigos está vacía O listaDeCategorias está vacía ENTONCES
            DEVOLVER "" 
          FIN SI
        
          Crear un HashMap llamado stockPorCategoria
        
          PARA CADA codigo EN listaDeCodigos HACER:
            categoria = primer caracter de codigo
            cantidad = obtener el número del código (después del espacio)
            
            SI stockPorCategoria contiene la clave categoria ENTONCES
              stockPorCategoria[categoria] = stockPorCategoria[categoria] + cantidad
            SINO
              stockPorCategoria[categoria] = cantidad
            FIN SI
          FIN PARA
        
          Crear una lista llamada resultado
        
          PARA CADA categoria EN listaDeCategorias HACER:
            SI stockPorCategoria contiene la clave categoria ENTONCES
              cantidad = stockPorCategoria[categoria]
            SINO
              cantidad = 0
            FIN SI
        
            Añadir a resultado la cadena "(categoria : cantidad)" 
          FIN PARA
        
          Unir los elementos de la lista resultado con " - "
          DEVOLVER la cadena resultante
        
        FIN Función
