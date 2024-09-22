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

if __name__ == "__main__":
    main()
