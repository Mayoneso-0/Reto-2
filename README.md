## Reto 2
Diagrama de clases de una fabrica de ultiles escolares.


---
config:
  theme: redux-dark
---
classDiagram
direction TB
    class Fabrica {
	    +Pedidos
	    +DescripcionPedidos
	    +Trabajadores
	    +Maquinas
	    +producirEsfero()
	    +producirLapiz()
	    +producirMarcador()
	    +producirColor()
    }
    class Cliente {
    }
    class MaquinaLapices {
	    +Cantidad
	    +Forma
	    +GradoMina
    }
    class MaquinaMarcadores {
	    +Cantidad
	    +Color
	    +TipoTinta
    }
    class MaquinaEsferos {
	    +Cantidad
	    +Color
	    +TipoTinta
	    +TamañoPunta
    }
    class MaquinaColores {
	    +Cantidad
	    +Color
	    +Forma
    }
    class Empaquetar {
	    +TamañoCaja
	    +MaterialCaja
	    +enviar()
    }

    Cliente "Pedido" --|> Fabrica
    Fabrica --|> MaquinaEsferos : ProducirEsfero()
    Fabrica --|> MaquinaLapices : ProducirLapiz()
    Fabrica --|> MaquinaMarcadores : ProducirMarcador()
    Fabrica --|> MaquinaColores : ProducirColor()
    MaquinaEsferos --|> Empaquetar
    MaquinaMarcadores --|> Empaquetar
    MaquinaColores --|> Empaquetar
    MaquinaLapices --|> Empaquetar
    Fabrica --|> Empaquetar
