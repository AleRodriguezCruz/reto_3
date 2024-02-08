# reto_3

#reto 3
#longitud de la cadena de caracteres
def longitud(cadena, min, max):
    if len(cadena) >= min and len(cadena) <= max:
        return True
    else:
        return False

#Validacion de número de teléfono
def validar_telefono(telefono):
    while True:
        if telefono.isdigit() and len(telefono) == 10:
            return True
        else:
            print('Error: El número de teléfono debe tener 10 dígitos.')
            telefono = input('Ingrese un número de teléfono válido: ')

#cantidad de usuarios a registrar
nuevos_usuarios = int(input('Ingrese la cantidad de nuevos usuarios que desea registrar: '))
#creamos la lista para almacenar los usuarios inicia vacia
ids_usuarios = []

# Ciclo para registrar 
for i in range(nuevos_usuarios):
    print('Ingrese los datos del usuario ' + str(i + 1) + ':')
    nombre = input('Nombre: ')
    apellidos = input('Apellidos: ')
    telefono = input('Teléfono: ')
    email = input('Correo electrónico: ')

    # Validar los datos ingresados
    while not longitud(nombre, 5, 50) or not longitud(apellidos, 5, 50) or not longitud(email, 5, 50) or not validar_telefono(telefono):
        print('Error: Los datos ingresados no son válidos. Por favor, inténtelo de nuevo.')
        print('Ingrese los datos del usuario ' + str(i + 1) + ':')
        nombre = input('Nombre: ')
        apellidos = input('Apellidos: ')
        telefono = input('Teléfono: ')
        email = input('Correo electrónico: ')

    # Generamos el ID único 
    id_usuario = i + 1

    # Agregamos a la lista
    ids_usuarios.append(id_usuario)

    print('El usuario ' + nombre + ' ' + apellidos + ' ha sido registrado con éxito.')

# Imprime la lista de IDs 
print('IDs de los usuarios registrados exitosamente: ' + str(ids_usuarios))
