# Observaciones Laboratorio No. :8ball:

## Preguntas :page_facing_up:

**1. ¿Qué relación encuentra entre el número de elementos en el árbol y la altura del árbol?**

Después de analizar la relación entre el número de nodos (1177) y la altura del árbol (29) es posible observar que el árbol se encuentra desbalanceado e incompleto, dado que en un BST balanceado esta relación 
está dada por las fórmulas ```n = 2^(h+1)-1``` que determina el número máximo de nodos que pueden guardarse en un árbol de altura ```h``` y ```h = floor(log2n)``` que determina la altura mínima para un árbol con
```n``` nodos.

**2. ¿Si tuviera que responder esa misma consulta y la información estuviera en tablas de hash y no en un BST, cree que el tiempo de respuesta sería mayor o menor? ¿Por qué?**

Pese a que la tabla de hash permite acceder a los valores de una llave en una complejidad constante ```O(1)```, para realizar esta consulta se tendría que acceder a cada llave y verificar
si se encuentra dentro del rango, de modo que la complejidad de esta consulta resultaría ser lineal ```O(n)``` en el peor de los casos. En ese sentido, el BST garantiza una complejidad temporal menor para esta 
consulta al encontrarse ordenadas por llaves.

**3. ¿Qué operación del TAD se utiliza para retornar una lista con la información encontrada en un rango de fechas?**

Como se puede observar a continuación, la operación utilizada para retornar una lista con la información encontrada dentro de un rango de fechas 
es ```om.values()```

```python
def getCrimesByRange(analyzer, initialDate, finalDate):
    """
    Retorna el numero de crimenes en un rago de fechas.
    """
    lst = om.values(analyzer['dateIndex'], initialDate, finalDate)
    totcrimes = 0
    for lstdate in lt.iterator(lst):
        totcrimes += lt.size(lstdate['lstcrimes'])
    return totcrimes
```

La función ```values(map, keylo, keyhi)``` del ADT orderedmap recibe por parámetro el map ordenado y un rango dado por un límite inferior ```keylo``` y un límite superior ```keyhi```.
