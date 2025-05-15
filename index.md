# H
## O
### L
#### A
##### Q
###### U

Agregue titulos


![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


```
def decimal_a_otro(valor, base):
    if base == 2:
        return bin(valor)[2:]
    elif base == 8:
        return oct(valor)[2:]
    elif base == 16:
        return hex(valor)[2:].upper()
    elif base == 36:
        digitos = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
        resultado = ""
        while valor > 0:
            resultado = digitos[valor % 36] + resultado
            valor //= 36
        return resultado
    else:
        return "Base no soportada."

def otro_a_decimal(valor, base):
    if base == 2:
        return int(valor, 2)
    elif base == 8:
        return int(valor, 8)
    elif base == 16:
        return int(valor, 16)
    elif base == 36:
        digitos = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
        valor = valor.upper()
        return sum(digitos.index(char) * (36 ** i) for i, char in enumerate(reversed(valor)))
    else:
        return "Base no soportada."

def menu():
    print("Bienvenido al convertidor de bases.")
    print("1. Decimal a otra base")
    print("2. Otra base a decimal")
    opcion = int(input("Elija una opción: "))

    if opcion == 1:
        valor = int(input("Ingrese el número decimal: "))
        print("Elija la base a la que desea convertir:")
        print("2. Binario")
        print("8. Octal")
        print("16. Hexadecimal")
        print("36. Base-36")
        base = int(input("Base: "))
        print(f"Resultado: {decimal_a_otro(valor, base)}")
    elif opcion == 2:
        base = int(input("Ingrese la base de su número: "))
        valor = input("Ingrese el número: ")
        print(f"Resultado en decimal: {otro_a_decimal(valor, base)}")
    else:
        print("Opción no válida.")

if __name__ == "__main__":
    menu()
```
