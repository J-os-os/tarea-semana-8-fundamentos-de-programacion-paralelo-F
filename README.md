#1)Bucle while: Escribe un programa en Python que utilice un bucle while para imprimir los primeros 5 números naturales.

# Inicializamos la variable 'numero' con el valor 1
numero = 1

# Iniciamos un bucle while que se ejecutará mientras 'numero' sea menor o igual a 5
while numero <= 5:
 # Imprimimos el valor actual de 'numero'
    print(numero)
    
    # Incrementamos 'numero' en 1 para la siguiente iteración
    numero += 1

#2)Bucle do-while: Crea un programa en Python que simule un juego de adivinanza. En este juego, el usuario debe adivinar un número secreto (por ejemplo, 7) y el programa le dará pistas si su adivinanza es demasiado alta o demasiado baja. Utiliza un bucle do-while para asegurarte de que el

def juego_adivinanza():
    # Establecer el número secreto a 2
    numero_secreto = 185
    
    # Inicializar la variable para controlar el bucle
    seguir_jugando = True
    
    while seguir_jugando:
        # Pedir al usuario que adivine el número
        adivinanza = int(input("Adivina el número secreto (entre 1 y 2000): "))
        
        # Comparar la adivinanza con el número secreto
        if adivinanza == numero_secreto:
            print("¡Felicidades, has adivinado el número secreto!")
            
            # Preguntar al usuario si quiere seguir jugando
            respuesta = input("¿Quieres jugar de nuevo? (s/n): ")
            if respuesta.lower() != "s":
                seguir_jugando = False
        elif adivinanza < numero_secreto:
            print("Tu adivinanza es demasiado baja. Inténtalo de nuevo.")
        else:
            print("Tu adivinanza es demasiado alta. Inténtalo de nuevo.")

# Iniciar el juego
juego_adivinanza()


#3)Bucle for: Desarrolla un programa en Python que calcule la suma de los primeros 10 números enteros positivos utilizando un bucle for.

# Inicializamos una variable para almacenar la suma
suma = 0

# Utilizamos un bucle for que itera sobre los números del 1 al 10
# range(1, 11) genera una secuencia de números desde 1 hasta 10 (11 no se incluye)
for i in range(1, 11):
    # En cada iteración, añadimos el número actual (i) a la suma
    suma += i  # Esto es equivalente a: suma = suma + i

# Una vez terminado el bucle, imprimimos el resultado
# Utilizamos una f-string para formatear la salida
print(f"La suma de los primeros 10 números enteros positivos es: {suma}")


#4)(Opcional) Bucle for avanzado: Crea un programa en Python que genere la serie de Fibonacci hasta el décimo término. Utiliza un bucle for para calcular y mostrar la serie.

# Inicializamos los dos primeros términos de la serie
a, b = 0, 1
# 'a' representa el término actual de la serie
# 'b' representa el siguiente término

# Utilizamos un bucle for para generar los 10 primeros términos
print("Serie de Fibonacci hasta el décimo término:")
for i in range(10):
    # Imprimimos el término actual
    print(a, end=" ")
    # El parámetro end=" " hace que los números se impriman en la misma línea, separados por espacios

    # Actualizamos los valores de 'a' y 'b' para el siguiente ciclo
    a, b = b, a + b
    # Esta es una asignación múltiple que equivale a:
    # temp = a
    # a = b
    # b = temp + b
    # Es decir, 'a' toma el valor de 'b', y 'b' toma la suma de los dos números anteriores

    	#5)(Opcional) Bucle personalizado: Diseña un problema interesante que involucre un bucle. Puede ser cualquier cosa, desde cálculos matemáticos hasta manipulación de cadenas. Proporciona un escenario y desarrolla un programa en Python que demuestre cómo resolverlo utilizando un bucle.

# Este código implementa un generador de contraseñas que sigue un patrón "zigzag".
# Crea contraseñas alternando entre letras y números, pero con un twist:
# las letras se seleccionan avanzando desde el inicio del alfabeto,
# mientras que los números se seleccionan retrocediendo desde el final.
# Cuando se llega al final (o inicio) de cada secuencia, se invierte la dirección.

def zigzag_password(letters, numbers, length):
    # Inicializa la contraseña como una cadena vacía
    password = ""
    # Índice para recorrer la cadena de letras, comienza en 0
    letter_index = 0
    # Índice para recorrer la cadena de números, comienza desde el final
    number_index = len(numbers) - 1
    # Dirección inicial para mover el índice de letras (1 = hacia adelante)
    letter_direction = 1
    # Dirección inicial para mover el índice de números (-1 = hacia atrás)
    number_direction = -1

    # Bucle principal para generar la contraseña
    for i in range(length):
        if i % 2 == 0:  # Si el índice es par, agrega una letra
            password += letters[letter_index]
            # Mueve el índice de letras en la dirección actual
            letter_index += letter_direction
            # Cambia la dirección si alcanza el inicio o el final del alfabeto
            if letter_index == 0 or letter_index == len(letters) - 1:
                letter_direction *= -1
        else:  # Si el índice es impar, agrega un número
            password += numbers[number_index]
            # Mueve el índice de números en la dirección actual
            number_index += number_direction
            # Cambia la dirección si alcanza el inicio o el final de los números
            if number_index == 0 or number_index == len(numbers) - 1:
                number_direction *= -1

    # Devuelve la contraseña generada
    return password

# Definición de las cadenas de letras y números a utilizar
letters = "CDEFGHIJK"
numbers = "0123456789"
# Longitud deseada para las contraseñas
password_length = 12

# Genera y muestra la contraseña generada
result = zigzag_password(letters, numbers, password_length)
print("Contraseña generada:", result)





    
