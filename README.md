# python_si
# pregunta1
```r
import random

def generar_numeros_aleatorios(cantidad=10):
    """Genera una lista de números aleatorios y la imprime."""
    numeros = [random.randint(1, 100) for _ in range(cantidad)]
    print("Números aleatorios generados:", numeros)
    return numeros

def filtrar_numeros_no_repetidos(numeros):
    """Filtra los números no repetidos y los imprime."""
    numeros_no_repetidos = list(set(numeros))
    print("Números no repetidos:", numeros_no_repetidos)
    return numeros_no_repetidos

def ordenar_numeros(numeros):
    """Ordena los números de mayor a menor y de menor a mayor, e imprime ambos."""
    orden_mayor_a_menor = sorted(numeros, reverse=True)
    orden_menor_a_mayor = sorted(numeros)
    print("Ordenados de mayor a menor:", orden_mayor_a_menor)
    print("Ordenados de menor a mayor:", orden_menor_a_menor)
    return orden_mayor_a_menor, orden_menor_a_menor

def mayor_par(numeros):
    """Indica el mayor número par de la lista y lo imprime."""
    pares = [num for num in numeros if num % 2 == 0]
    mayor_par = max(pares) if pares else None
    print("Mayor número par:", mayor_par)
    return mayor_par

def main():
    """Función principal que ejecuta todas las funciones."""
    numeros = generar_numeros_aleatorios()
    numeros_no_repetidos = filtrar_numeros_no_repetidos(numeros)
    ordenar_numeros(numeros_no_repetidos)
    mayor_par(numeros_no_repetidos)

if __numeros__ == "__main__":
    main()
```

# pregunta2
```r
from datetime import datetime

def conteo(func):
    """Decorador que cuenta los parámetros de la función."""
    def wrapper(*args):
        # Contar la cantidad de parámetros
        num_params = len(args)

        if num_params > 1:
            result = func(*args)
            print(f"La función '{func.__name__}' fue ejecutada.")
            return result
        else:
            print("Se requiere más de un parámetro para procesar la función.")
            return None

    return wrapper

@conteo
def registrar_persona(edad, nombre):
    """Registra una persona y captura la hora y minuto."""
    hora_actual = datetime.now()
    hora = hora_actual.strftime("%H")
    minuto = hora_actual.strftime("%M")
    print(f"Registrado: Nombre: {nombre}, Edad: {edad}, Hora: {hora}, Minuto: {minuto}")

@conteo
def calcular_media(nota1, nota2, nota3, nota4):
    """Calcula la media de 4 notas."""
    media = (nota1 + nota2 + nota3 + nota4) / 4
    print(f"La media de las notas es: {media:.2f}")
    return media

# Ejemplo de uso
registrar_persona(25, "Alicia")
registrar_persona(30)  # Este caso debería mostrar un mensaje de error

calcular_media(15, 18, 20, 22)
calcular_media(10, 12)  # Este caso debería mostrar un mensaje de error
```
# pregunta3
```r

import time

def tiempo_ejecucion(func):
    """Decorador que mide el tiempo de ejecución de una función."""
    def wrapper(*args, **kwargs):
        inicio = time.time()  # Tiempo de inicio
        result = func(*args, **kwargs)
        fin = time.time()  # Tiempo de fin
        print(f"Tiempo de ejecución de '{func.__name__}': {fin - inicio:.4f} segundos.")
        return result
    return wrapper

@tiempo_ejecucion
def mayor_numero(*numeros):
    """Encuentra el mayor número de una lista de números."""
    if not numeros:
        print("No se proporcionaron números.")
        return None
    mayor = max(numeros)
    print(f"El mayor número es: {mayor}")
    return mayor

# Ejemplos de uso
mayor_numero(5, 10, 15, 2, 8)
mayor_numero(100, 50, 200, 75)
mayor_numero(-10, -5, -3, -20, -1)
```


