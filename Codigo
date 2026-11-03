import math # Libreria para usar la función sqrt() y floor()

# Función para obtener un número entero positivo del usuario y volver a pedirlo si la entrada es inválida
def obtener_entero_positivo():
    while True:
        entrada = input("Ingresa un número entero positivo: ")
        try:
            n = int(entrada)
            if n > 0 and n.is_integer(): # Verifica si el número es un entero positivo
                return int(n)
            else:
                print("El número debe ser un entero y mayor o igual a 1.")
        except ValueError:
            print("Entrada inválida. Debes ingresar un número.")

# Función para determinar si un número es primo, compuesto o ninguno
def determinar_primo(n):
    # Caso especial para el número 1
    if n == 1:
        return "neither"

    limite = math.floor(math.sqrt(n)) # Calcula el límite para la verificación de factores

    # Verifica los factores base 2, 3 y 5
    factores_base = [2, 3, 5]
    for factor in factores_base:
        if factor <= limite:
            if n % factor == 0:
                if n == factor:
                    return True
                return False
        else:
            return True

    # Verificación de factores mayores usando el patrón de saltos 4, 2, 4, 2, 4, 6, 2, 6
    divisor = 7
    saltos = [4, 2, 4, 2, 4, 6, 2, 6]
    indice_salto = 0

    # Verifica los factores mayores que 5
    while divisor <= limite:
        if n % divisor == 0:
            return False
        divisor += saltos[indice_salto]
        indice_salto = (indice_salto + 1) % len(saltos)

    return True

# Bloque principal del programa
if __name__ == "__main__":
    print("=== PROGRAMA VERIFICADOR DE NÚMEROS PRIMOS ===")
    numero = obtener_entero_positivo()
    
    resultado = determinar_primo(numero)
    
    if resultado == "neither": # Caso especial para el número 1
        print(f"El número {numero} no es ni primo ni compuesto.")
    elif resultado: # El número es primo si resultado es True
        print(f"El número {numero} es primo.")
    else: # El número es compuesto si resultado es False
        print(f"El número {numero} es compuesto.")
