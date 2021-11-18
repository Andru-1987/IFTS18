# Ejercicio tipo 2 Parcial

# Cada año se desarrolla el campeonato nacional de tiro con arco y flecha. 
# Se desea reemplazar el sistema de seguimiento y control de los participantes
# por un programa escrito en Python.

# Que es lo que sabemos del concurso:
# Pueden participar hombres y mujeres de todas las edades.
# Cada participante podrá realizar 1 disparo (obligatorio).
# Se dispara a un blanco cuyo centro coincide con el origen de coordenadas de un eje cartesiano (x, y). La mejor puntuación la obtiene el disparo más cercano al origen.
# Cada participante tiene un número único que lo identifica del resto.
# El radio del tablero es de 80 cm.

# 1)Mostrar al ganador (Nro Participante, Nombre, Apellido y Mejor disparo).
# 2)Informar quien fue el último (Nro Participante, Nombre, Apellido y Mejor disparo).
# 3)Informar cuantos participantes formaron parte del concurso.
# 4)Informar cuantos hombres formaron parte del concurso.
# 5)Informar edad promedio de las mujeres.
# 6)Informar el promedio de todos los disparos.




def tiroAlTablero(x,y):

    import math

    distancia=round(math.sqrt(x**2+y**2),2)

    return distancia

def validarNumero(numero):
    import re
    # Permite valores positivos
    user_format=re.compile(r'^[0-9]*$')
    valido=re.match(user_format,numero)

    while valido==None or numero=='':
      numero=input('Ingrese data valida ')
      valido=re.match(user_format,numero)

    return int(numero)

def validarNumeroString(numero):
    import re
    # Permite valores positivos
    user_format=re.compile(r'^[0-9]*$')
    valido=re.match(user_format,numero)

    while valido==None or numero=='':
      numero=input('Ingrese data valida ')
      valido=re.match(user_format,numero)

    return numero

def cadena(string):
    import re
    # Permite valores positivos
    user_format=re.compile(r'^[A-z_Ññ]*$')
    valido=re.match(user_format,string)

    while valido==None or string=='':
      string=input('Ingrese data válida ')
      valido=re.match(user_format,string)

    return string

def participantesLista():

    listaDeParticipantes=[]

    while True:

        participante={}

        idParticipante=validarNumeroString(input('Ingrese #ID participante: '))
        if idParticipante=='999':
            break
        nombre=cadena(input('Ingrese nombre: ')).lower().capitalize()
        apellido=cadena(input('Ingrese apellido: ')).lower().capitalize()

        edad=validarNumero(input('Ingrese edad: '))
        sexo=input('Ingrese sexo "h/m":' ).lower()
        disparoX=validarNumero(input('Ingrese distancia de X al centro del tablero: '))
        disparoY=validarNumero(input('Ingrese distancia de Y al centro del tablero: '))
        disparo=tiroAlTablero(disparoX,disparoY)

        listaData=['idParticipante','nombre', 'apellido','edad', 'sexo', 'disparo']
        listaValores=[int(idParticipante),nombre,apellido,edad,sexo,disparo]

        for part in listaData:
            index=listaData.index(part)
            participante[part]=listaValores[index]

        listaDeParticipantes.append(participante)

    return listaDeParticipantes

def mostrarGanador(listaDeParticipantes):
    # Punto1
    mejorDisparo=listaDeParticipantes[0].get('disparo')
    nombre=listaDeParticipantes[0].get('nombre')
    apellido=listaDeParticipantes[0].get('apellido')

    for n in listaDeParticipantes:
        if n['disparo']<mejorDisparo:
            nombre=n['nombre']
            apellido=n['apellido']
            mejorDisparo=n['disparo']


    print(f'El ganador fue {apellido}, {nombre} y la distancia a su disparo fue de: {mejorDisparo}')

def mostrarPerdedor(listaDeParticipantes):
    # Punto2
    peorDisparo=listaDeParticipantes[0].get('disparo')
    nombre=listaDeParticipantes[0].get('nombre')
    apellido=listaDeParticipantes[0].get('apellido')

    for n in listaDeParticipantes:
        if n['disparo']>peorDisparo:
            nombre=n['nombre']
            apellido=n['apellido']
            peorDisparo==n['disparo']

    print(f'El perdedor fue {apellido}, {nombre} y la distancia a su disparo fue de: {peorDisparo}')

def participantes(listaDeParticipantes):
    # Punto3
    cantidadParticipantes=len(listaDeParticipantes)
    print(f'Cantidad de participantes en el concurso : {cantidadParticipantes}')

def cantidadHombres(listaDeParticipantes):
    # punto 4
    accumulador=0
    for n in listaDeParticipantes:
        if n.get('sexo')=='h':
            accumulador+=1
    if accumulador==0:
        print('No hubo hombres en el concurso')
    else:
        print(f'Cantidad de participantes de sexo masculino: {accumulador}')

def promedioMujeres(listaDeParticipantes):
    # punto 5
    contMujeres=0
    accEdad=0

    for n in listaDeParticipantes:
        if n.get('sexo')=='m':
          contMujeres+=1
          accEdad+=n.get('edad')

    if contMujeres==0:
        print('No hubo mujeres en el concurso')
    else:
        promedioEdad=round(float(accEdad/contMujeres),2)
        print(f'El promedio de edad de las mujeres es de : {promedioEdad}')

def promedioDisparos(listaDeParticipantes):
    # punto 5
    
    accValorDisparos=0

    for n in listaDeParticipantes:
      accValorDisparos+=n.get('disparo')



    promedio=round(float(accValorDisparos/len(listaDeParticipantes)),2)
    print(f'El promedio de valor en los disparos fue de: {promedio}')



def main():

    print('Gracias por usar el programa Concurso de Tiro')

    listaDeParticipantes=participantesLista()
    mostrarGanador(listaDeParticipantes)
    mostrarPerdedor(listaDeParticipantes)
    participantes(listaDeParticipantes)
    cantidadHombres(listaDeParticipantes)
    promedioMujeres(listaDeParticipantes)
    promedioDisparos(listaDeParticipantes)

    print('Gracias!')

main()
