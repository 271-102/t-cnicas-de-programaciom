# tecnicas-de-programaciom
casandra muyolema 
# Abstracción: Mostrar solo funcionalidades esenciales, ocultando detalles complejos.

from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sonido(self):
        pass

class Perro(Animal):
    def sonido(self):
        return "Guau"

class Gato(Animal):
    def sonido(self):
        return "Miau"

# Uso:
def hacer_sonar(animal: Animal):
    print(animal.sonido())

perro = Perro()
gato = Gato()

hacer_sonar(perro)  # Guau
hacer_sonar(gato)   # Miau
# Encapsulación: Ocultar atributos privados, controlar acceso mediante métodos.

class CuentaBancaria:
    def __init__(self, titular, saldo):
        self.titular = titular
        self.__saldo = saldo  # atributo privado

    def depositar(self, cantidad):
        if cantidad > 0:
            self.__saldo += cantidad

    def retirar(self, cantidad):
        if 0 < cantidad <= self.__saldo:
            self.__saldo -= cantidad

    def mostrar_saldo(self):
        return self.__saldo

# Uso:
cuenta = CuentaBancaria("Juan", 1000)
cuenta.depositar(500)
cuenta.retirar(200)
print(cuenta.mostrar_saldo())  # 1300
# Herencia: Crear clases que heredan atributos y métodos de otras.

class Vehiculo:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo

    def mostrar_info(self):
        print(f"Marca: {self.marca}, Modelo: {self.modelo}")

class Auto(Vehiculo):
    def __init__(self, marca, modelo, puertas):
        super().__init__(marca, modelo)
        self.puertas = puertas

    def mostrar_info(self):
        super().mostrar_info()
        print(f"Puertas: {self.puertas}")

# Uso:
auto = Auto("Toyota", "Corolla", 4)
auto.mostrar_info()
# Polimorfismo: Diferentes clases usan métodos con el mismo nombre pero comportamientos distintos.

class Ave:
    def volar(self):
        print("El ave está volando")

class Pinguino(Ave):
    def volar(self):
        print("Los pingüinos no vuelan")

class Aguila(Ave):
    def volar(self):
        print("El águila vuela alto")

# Uso:
def mostrar_vuelo(ave):
    ave.volar()

pinguino = Pinguino()
aguila = Aguila()

mostrar_vuelo(pinguino)  # Los pingüinos no vuelan
mostrar_vuelo(aguila)    # El águila vuela alto
/abstraccion/abstraccion.py
/encapsulacion/encapsulacion.py
/herencia/herencia.py
/polimorfismo/polimorfismo.py
README.md

