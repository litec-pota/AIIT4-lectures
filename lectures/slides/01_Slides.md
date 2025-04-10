---
author: DI (FH) Andreas Pötscher
title: Microcontroller Teil 1 Hardware
institute: HTL Litec
navigation: frame
theme: default
colortheme: rose
aspectratio: 169
---


## Pins und Ports

Ein Pin ist Anschluss eines ICs, der mit der Platine verlötet wird.

![Pin eines Microcontrollers](../imgs/pin_eines_microcontrollers.png){ width=50% }

## Pins und Ports

> Die meisten Pins der AVR-Mikrocontroller sind so genannte GPIO-Pins: General Purpose Input
Output Pins – Allgemein verwendbare Ein-/Ausgangs-Pins. Sie können entweder als digitale
Eingänge oder als digitale Ausgänge verwendet werden.

## Pin als Eingang

>* Eine externe Schaltung legt eine Spannung von 0V oder 5V an den Pin.
>* Die Spannung wird vom Microcontroller als logisch 0 oder logisch 1 eingelesen.
>* Verwendung für Taster, Sensoren, ...

## Pin als Ausgang

>* Der Microcontroller legt programmgesteuert eine Spannung von 0V oder 5V an den Pin.
>* Die Spannungungspegel wird vom Microcontroller als logisch 0 oder logisch 1 in der Software gesetzt.
>* Verwendung für LEDs, Relais, Motor, ...

## Pins und Ports

> Üblicherweise sind die meisten Pins eines Mikrocontrollers GPIO-Pins (General Purpose
Input/Output). Sie können entweder als Eingänge oder als Ausgänge verwendet werden.
Das im Mikrocontroller laufende Programm muss jeden verwendeten GPIO-Pin zu einem
Ein- oder zu einem Ausgang programmieren. Das passiert in der Initialisierungsphase des
Programms.

## Ports

>* Microcontrollerpins sind überlicherweise zu Achtergruppen zusammengefasst.
>* Diese Achtergruppen bilden einen **Port**.
>* Ports werden mit einem Buchstaben bezeichnet: PortA, PortB, ....
>* Die Pins werden mit 0 bis 7 durchnummeriert.
>* Der Pin 0 von PortB hat dann die Bezeichnung PB0

## Beispiel Pinout

![Pinbelegung des Atmega 2560](../imgs/ATmega2560_Pinbelegung.png){ width=65% }


## Alternative Funktionen 

>* GPIO Pins können auch alternative Funktion haben.
>* Der Pin kann dann entweder als Eingang, Ausgang oder in seiner alternativen Funktion verwendet werden.
>* Z.B hat der der PIN PE0 die alternative Funktion *RXD0* (Receive Data 0).
>* Beim Arduino Mega werden diese als serielle Schnittstelle verwendet und können damit nicht als GPIO genutzt werden.

## Pin Mapping

![Arduino Mega Pinout Diagramm](../imgs/ARDUINO-Mega-Pinout-Diagram.png){ width=70% }


## GPIO als Ausgang

> Wird vom Programm aus ein GPIO-Pin als Ausgang programmiert, so gibt der Mikrocontroller
entweder einen High- oder einen Low-Pegel aus (5V gegen GND bzw. 0V gegen GND). Vom
Programm aus kann der gewünschte Pegel vorgegeben werden, und zwar durch Schreiben einer
1 bzw. einer 0 in ein Bit in einem Special-Function-Register (oder durch Verwenden einer
Bibliotheks-Funktion).

## GPIO als Ausgang (High Pegel)

Bei einem High Pegel wird der GPIO über einen Schalttransistor mit **5V** verbunden.

![High Pegel](../imgs/High-Pegel.png){ width=70% }

## GPIO als Ausgang (Low Pegel)

Bei einem Low Pegel wird der GPIO über einen Schalttransistor mit **GND** verbunden.

![Low Pegel](../imgs/Low-Pegel.png){ width=70% }

## LED an einem GPIO Pin

>* LEDs müssen immer mit einem Vorwiderstand betrieben werden (ca. 330 $\Omega$, um den LED-Strom auf ca. 10mA zu begrenzen).
>* Es gibt 2 Varianten eine LED anzuschließen.
>* In beiden Fällen muss der GPIO als Ausgang programmiert werden.

## LED an einem GPIO Pin Variante 1

Bei dieser Variante wird mit einer logischen **1** im Programm die LED **eingeschaltet** und mit einer logischen **0 ausgeschaltet**.

![Erste Variante zum Anschließen von Leds](../imgs/LED_Variante1.png)


## LED an einem GPIO Pin Variante 2

Bei dieser Variante wird mit einer logischen **0** im Programm die LED **eingeschaltet** und mit einer logischen **1 ausgeschaltet**.

![Zweite Variante zum Anschließen von Leds](../imgs/LED_Variante2.png)

## Beispiel anschließen von LEDs 

[**Beispiel**](https://wokwi.com/projects/405136729960453121) Schließen Sie die LEDs in beiden Varianten an den Microcontroller und starten Sie die Simulation.


## GPIO als Eingang

> Wird ein GPIO-Pin als Eingang programmiert, muss eine externe Schaltung eine Spannung
von 5V (High-Pegel) oder 0V (Low-Pegel) zwischen Pin und GND erzeugen. Meist geschieht
das, indem die externe Schaltung den Eingangspin des Mikrocontrollers mit VCC oder
mit GND verbindet. Der von der externen Schaltung angelegte Spannungspegel kann vom
Programm eingelesen werden.

## Potentialfreier Eingang

>* Ein verwendeter Eingang darf nicht potenzialfrei bleiben.
>* Das bedeutet es muss immer eine Verbindung entweder mit 5V oder GND hergestellt sein.
>* Falls dies nicht der Fall ist, ist der Zustand undefiniert.
>* Selbst kleinste elektromagnetische Felder können den Eingangszustand verändern.
>* Im Programm sieht es so aus als ob der Eingang zufällig 0 oder 1 ist.

## Anschließen eines Tasters

>* Wenn ein Taster als Eingang verwendet wird muss sicher gestellt werden, dass der Eingang nie potentialfrei ist.
>* Dazu gibt es drei Möglichkeiten.

## Externer pull-down Widerstand

>* Der Taster wird zwischen VCC und Eingangspin geschaltet.
>* Zusätzlich verbindet eine Widerstand (typischerweise 10 $k\Omega$) den Pin mit GND.
>* Wird der Taster gedrückt wird eine logische 1 im Programm gelesen.
>* Wird der Taster nicht gedrückt eine logische 0.

## Externer pull-down Widerstand

![Taster an AVR Mikrocontroller mit pull-down Widerstand](../imgs/Taster_PullDown.png)

## Externer pull-down Widerstand

[**Beispiel**](https://wokwi.com/projects/407265010293395457) Schließen Sie den Taster mit externen pull-down Widerstand an den Microcontroller und starten Sie die Simulation.

## Externer pull-up Widerstand

>* Der Taster wird zwischen GND und Eingangspin geschaltet.
>* Zusätzlich verbindet eine Widerstand (typischerweise 10 $k\Omega$) den Pin mit VCC.
>* Wird der Taster gedrückt wird eine logische 0 im Programm gelesen.
>* Wird der Taster nicht gedrückt eine logische 1.


## Externer pull-up Widerstand

![Taster an AVR Mikrocontroller mit pull-up Widerstand](../imgs/Taster_PullUp.png)


## Externer pull-up Widerstand

[**Beispiel**](https://wokwi.com/projects/407265010293395457) Schließen Sie den Taster mit externen pull-up Widerstand an den Microcontroller und starten Sie die Simulation.


## Interner pull-up Widerstand

![Taster an AVR Mikrocontroller mit internem pull-up Widerstand](../imgs/Taster_InternalPullUp.png)


## Interner pull-up Widerstand

[**Beispiel**](https://wokwi.com/projects/407265010293395457) Schließen Sie den Taster mit internem pull-up Widerstand an den Microcontroller und starten Sie die Simulation.