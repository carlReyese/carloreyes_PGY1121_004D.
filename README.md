# carloreyes_PGY1121_004D.

from os import system
import random
registro=[]
programa=0
def grabar():
    marca=''
    precio=0
    vehiculo={}
    fecha_multa=''
    vehi_multas=[]
    tipo=str(input("\n Ingrese tipo de vehiculo: "))
    patente=str(input("\n Ingrese patente del vehiculo:"))
    fecha_vehi=str(input("\n Ingrese la fecha registro del vehiculo"))
    nom_dueno=str(input("\n Ingrese el nombre del dueño"))
    opcion_mult=int(input("\n¿usted tiene multas? \n 1) si 2)no \n elija una opción"))
    if opcion_mult==1:
        fecha_multa=str(input('Ingrese la fecha de la multa'))
        monto_multa=int(input('\nIngrese el monto de la multa:3'))
    system("cls")
    while len(marca)<2 or len(marca)>15:
        marca=str(input("\n Ingrese la marca del vehiculo: "))
    while precio<5_000_000:
        precio=int(input("\n Ingrese el valor del vehiculo: $"))

    vehiculo['tipo']=tipo
    vehiculo['patente']=patente
    vehiculo['fecha_vehi']=fecha_vehi
    vehiculo['nom_dueno']=nom_dueno
    vehiculo['marca']=marca
    vehiculo['precio']=precio
    vehiculo['multas']=vehi_multas
    vehiculo['fecha_multa']=fecha_multa
    vehiculo['monto_multa']=monto_multa
    registro.append(vehiculo)
    system("cls")

def buscar():
    patente=str(input("\n Ingrese la patente del vehiculo: "))
    system("cls")
    for i in registro:
        if(i['patente']==patente):
            print('\n*********************')
            print('\nvehichulo')
            print('Tipo vehiculo:', i ['tipo'])
            print('Nombre dueño:',i['nom_dueno'])
            print('Fecha registro:', i['fecha_vehi'])
            print('Marca vehiculo:', i['marca'])
            print('Precio vehiculo:', i['precio'])
            print('\n*********************')

def certificado():
    print('\nCertificados')
    patente=str(input('\nIngrese el numero de patente:'))
    system("cls")

    for i in registro:
        if(i['patente']==patente):
            print('\n***Certificado Emision contaminante*****')
            print('\n*********Vehiculo**********')
            print('     Tipo Vehiculo:', i['tipo'])
            print('     Nombre Dueño:',  i['nom_dueno'])
            print('     Fecha Registro:',i['fecha_vehi'] )
            print('     Marca Vehiculo:', i['marca'])
            print('***********APROBADO*************')
            print('\n***certificado de anotaciones***')
            print('\n*********Vehiculo**********')
            print('     Tipo Vehiculo:', i['tipo'])
            print('     Nombre Dueño:',  i['nom_dueno'])
            print('     Fecha Registro:',i['fecha_vehi'] )
            print('     Marca Vehiculo:', i['marca'])
            print('***********APROBADO*************')
            if len(i['multas'])>0:
                print('\n ------------------------------')
                print('Este vehiculo posee multas')
                print('\n ------------------------------')
                for x in i['multas']:
                    print('\n**********************')
                    print('\n Multas pendiente')
                    print('\nMonto pendiente : $', x ['multa'])
                    print('\nFecha de la multa:', x ['fecha_multa'])
                    print('\n**********************')

print('\nBienvenido a Auto Seguro')
while programa==0:
    print('\n1) Ingresar datos del Vehiculo')
    print('\n2 Buscar informacion')
    print('\n3 Certificados')
    print('\n4 Salir')
    opcion=int(input('\n Seleccione una Opcion'))
    system("cls")

    match opcion:
        case 1:
            grabar()
        case 2:
            buscar()
        case 3:
            certificado()
        case 4:
            print('\nGracias por Usar este Programa')
            print('\nCarlo Reyes. version 2.1.0')
            programa=4
