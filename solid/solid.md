# Solid

SOLID é um acrônimo que consolida 5 itens que são considerados como boas práticas no mundo do desenvolvimento orientado a objetos. Foi criado por Robert C. Martin, o Uncle Bob.

SRP = Single Responsibility Principle
OCP = Open-closed Responsability Principle
LSP = Liskov Substitution Principle
ISP = Interface Segregation Principle
DIP = Dependecy Inversion Principle



## Single Responsibility Principle

Uma classe deve ter uma responsabilidade. Deve ter apenas um, e apenas um, motivo pra mudar.


``` Python
class Quadrado:
    
  def __init__(self, comprimento_lado=0):
    self.comprimento_lado = comprimento_lado
  def calcula_area(self):
    return self.comprimento_lado ** 2
  def desenhar(self):
    # Desenha um quadrado
    pass
```

A classe acima tem duas funcionalidades diferentes pra Quadrado.


``` Python
class CalculaQuadrado:
    def __init__(self, comprimento_lado=0):
        self.comprimento_lado = comprimento_lado
    def calcula_area(self):
        return self.comprimento_lado * 2
class DesenhaQuadrado:
    
    def desenha(self):
        # Desenha um quadrado
        pass
```

## Open-closed Responsability Principle

“Software entities … should be open for extension but closed for modification”

Ao invés de colocar tudo dentro de uma classe, cria-se uma base da classe e se estende isso pra outros componentes. Isso impede que ela aumente de tamanho e responsabilidade quando se precisar adicionar modificações. 


``` Python
import numpy as np
from abc import ABC, abstractmethod

class Operations(ABC):
    '''Operations'''
    @abstractmethod
    def operation():
        pass

class Mean(Operations):
    '''Compute Max'''
    def operation(list_):
        print(f"The mean is {np.mean(list_)}") 

class Max(Operations):
    '''Compute Max'''
    def operation(list_):
        print(f"The max is {np.max(list_)}") 
```


### Referencias

https://medium.com/@viniciuschan/solid-com-python-entendendo-os-5-princ%C3%ADpios-na-pr%C3%A1tica-f2af330b7751

https://towardsdatascience.com/solid-coding-in-python-1281392a6a94