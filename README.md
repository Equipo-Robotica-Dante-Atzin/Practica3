# Práctica 3
## Integrantes
- Dante Mejía Silva
- Atzin Morales Alejandre

## Introducción

En los robots Epson, como el Epson C4, el comando GO se utiliza para controlar el movimiento del robot, permite la programación de robots para realizar movimientos rápidos y directos entre dos puntos, sin necesidad de seguir una trayectoria específica. Se enfoca principalmente en la velocidad, lo que lo convierte en una opción ideal en situaciones donde el tiempo es un factor clave y la precisión del recorrido no es esencial.

**Usos y ventajas:**

- **Velocidad:** Permite al robot desplazarse de un punto a otro de manera rápida, reduciendo tiempos de ciclo en procesos industriales.
- **Trayectoria no controlada:** No se preocupa por seguir una trayectoria precisa, lo que facilita movimientos rápidos cuando la ruta no es crítica.
- **Optimización de procesos:** Es ideal para optimizar procesos en los que la rapidez de los movimientos entre posiciones es más importante que la exactitud del desplazamiento.
- **Simplicidad:** Al no requerir el cálculo de trayectorias complejas, su implementación es más sencilla y rápida.
- **Reducción de tiempos muertos:** Minimiza los tiempos de inactividad entre operaciones, aumentando la eficiencia de la producción.

En términos generales, el comando GO se utiliza en aplicaciones donde la velocidad es prioritaria, como el traslado de piezas entre estaciones de trabajo, el transporte de herramientas o el movimiento entre zonas seguras dentro de un entorno controlado. [1]


## Instrucciones

Primero, se analizó la trayectoria que debía seguir el robot Epson. Esta consistía en los siguientes pasos: inicialmente, el robot debía agarrar un fusible y colocarlo en una caja situada debajo de su brazo. Luego, debía tomar otro fusible, ubicado en el lado opuesto al del primer fusible, y colocarlo en la posición del primer fusible retirado. Finalmente, el fusible que se encontraba en la caja era nuevamente tomado para ser colocado en la posición del segundo fusible. Al mismo tiempo se guardaban todas la posiciones analizadas.

![Imagen de WhatsApp 2024-09-06 a las 21 07 07_ce4dab11](https://github.com/user-attachments/assets/fcbd7f5a-f674-4506-a0c9-0d850a1aba28)

Con esta secuencia definida, se procedió a programar el robot utilizando el software Epson RC+, logrando el siguiente resultado:
```
Function main
Home
Go primero
On 2
Go segundo
Off 2
Go primero
Home
Go tercero
On 2
Go levantartres
Go cuarto
Go quinto
Off 2
Go cuarto
Home
Go primero
Go segundo
On 2
Go primero
Home
Go tercero
Off 2
Home
Go cuarto
Go quinto
On 2
Go cuarto
Home
Fend
```

Primeramente, se colocó el brazo en la posición de “Home”.

![image](https://github.com/user-attachments/assets/a9802f0f-37f8-452f-9dea-7b1c052624fb)

Después cuidadosamente tratando de evitar una colisión se movió el brazo a la posición “primero”, la cual corresponde al punto donde el brazo está encima del fusible, es decir, las coordenadas X y Y son las correctas, sin embargo, el brazo en la coordenada Z se encuentra desplazado un poco hacia arriba.

La posición “segundo” corresponde al punto donde el brazo toma el fusible, es decir, se coloca se disminuye en Z para bajar el brazo. Para tomar el brazo es necesario cerrar la pinza del brazo, esto mediante el comando “off 2”.

![Imagen de WhatsApp 2024-09-06 a las 21 07 07_e71102f8](https://github.com/user-attachments/assets/f7a782be-a488-47b8-ae2a-bee92c794c26)

Una vez tomado el fusible se regresa el brazo a la posición “primero” y después a “Home”.

Ahora, es necesario soltar el fusible encima de la caja, por lo que se toma la posición “tercero” la cual corresponde a donde el brazo se encuentra encima de la caja y posteriormente se suelta el fusible mediante el comando “on 2”.

![image](https://github.com/user-attachments/assets/5fdee821-d9a1-4b85-a74d-5a547e87f3c4)

Una vez ubicado el primer fusible encima de la caja es necesario alzar un poco el brazo, de esta manera evitamos tirar erroneamente al suelo el fusible.

Después cuidadosamente tratando de evitar una colisión se movió el brazo a la posición “cuarto”, la cual corresponde al punto donde el brazo está encima del segundo fusible, es decir, las coordenadas X y Y son las correctas, sin embargo, el brazo en la coordenada Z se encuentra desplazado un poco hacia arriba.

La posición “quinto” corresponde al punto donde el brazo toma el segundo fusible, es decir, se coloca se disminuye en Z para bajar el brazo. Para tomar el brazo es necesario cerrar la pinza del brazo, esto mediante el comando “off 2”.

Para finalizar se siguó en la misma sintonía de programación para continuar la trayectoria previamente analizada. Concretando con éxito una trayectoria más compleja y extensa utilizando el brazo robótico.

## Conclusiones

***Atzin Morales Alejandre:*** El comando GO es un comando de movimiento que prioriza la velocidad sobre la precisión en la trayectoria, ya que solo interpola entre el punto inicial y el final, siendo útil cuando la rapidez es más importante que la exactitud. 

El laboratorio de robótica destacó la relevancia de interactuar directamente con el brazo robótico para obtener resultados precisos en la programación de movimientos. Al usar el brazo para una tarea simple, como tomar y soltar un fusible, permitió poder identificar la importancia de coordinar bien los movimientos y el control de la pinza mediante los comandos adecuados. Esto garantiza no solo la correcta ejecución de la tarea, sino también la repetitividad del proceso. 

Por último, la práctica demostró la importancia de una programación cuidadosa al definir los puntos, asegurando que el brazo siga las trayectorias previstas con precisión y sin colisiones, lo que mejora la eficiencia en aplicaciones industriales.


***Dante Mejía Silva:*** 
En conclusión, la práctica de laboratorio en robótica permitió programar y ejecutar de manera eficiente una secuencia compleja con el robot Epson. A través de la planificación cuidadosa de las trayectorias, se logró que el robot tomara y moviera fusibles con precisión, evitando colisiones y errores. La correcta manipulación de las coordenadas X, Y y Z, así como el uso de comandos para controlar la pinza, fueron claves para garantizar la seguridad y efectividad del proceso.

La programación en el software Epson RC+ permitió definir y ajustar cada posición, logrando la automatización de la tarea. La secuencia más compleja, como el intercambio de fusibles y su reposicionamiento, fue implementada exitosamente, lo que demuestra un entendimiento sólido de las operaciones del robot y la capacidad de ejecutar movimientos precisos. En resumen, la práctica cumplió con los objetivos planteados y proporcionó una experiencia valiosa en la programación y control de robots industriales.

## Referencias Bibliográficas 

[1] 	EpsonCompany, «Especialistas en automatización industrial». 2024, https://www.epson.es/es_ES/robots
