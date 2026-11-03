# Discretas_2_Ejercicio_2

Programa de consola escrito en Python que solicita un número entero positivo y determina si es **primo**, **compuesto** o si no pertenece a ninguna de esas categorías (el caso del número 1).

## Requisitos

- Python 3
- No requiere instalar paquetes adicionales; utiliza el módulo estándar `math`.

## Cómo ejecutar

Desde la carpeta del proyecto, ejecuta:

```bash
python Codigo.py
```

El programa pedirá un entero positivo. Después mostrará si es primo o compuesto. Para el número 1, indicará que no es ni primo ni compuesto.

## ¿Cómo funciona?

El código está organizado en dos funciones y un bloque principal:

### `obtener_entero_positivo()`

Solicita un valor mediante la consola y lo convierte a entero con `int()`. Si la conversión falla, muestra un mensaje de entrada inválida y vuelve a pedirlo. También pretende comprobar que el valor sea positivo antes de devolverlo.

### `determinar_primo(n)`

Clasifica el número recibido:

1. Si `n` es 1, devuelve el texto `"neither"`, ya que 1 no es primo ni compuesto.
2. Calcula la raíz cuadrada de `n` y la redondea hacia abajo. Para decidir si un número tiene divisores basta revisar hasta ese límite.
3. Comprueba primero divisibilidad entre 2, 3 y 5.
4. Revisa posibles divisores mayores que 5, usando una secuencia de saltos para omitir números divisibles por 2, 3 o 5.
5. Si encuentra un divisor, devuelve `False` (compuesto); si no encuentra ninguno, devuelve `True` (primo).

### Bloque principal

La condición `if __name__ == "__main__":` ejecuta el programa cuando `Codigo.py` se inicia directamente. Muestra el título, obtiene el número, llama a `determinar_primo()` y presenta el resultado correspondiente.

## Nota sobre el código actual

En `obtener_entero_positivo()`, `n` ya es un entero después de ejecutar `int(entrada)`. Por eso, la llamada `n.is_integer()` provoca un error (`AttributeError`): ese método no está disponible para valores de tipo `int`. Para que la validación funcione, basta con cambiar la condición `if n > 0 and n.is_integer():` por `if n > 0:`. Hasta aplicar ese ajuste, el programa no llegará a clasificar una entrada válida.
