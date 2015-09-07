# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo será una implementación directa del concenpo de implicación: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**función** ¿IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en lógica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en lógica propocisional    

_simbolos_  $$\leftarrow$$ una lista de símbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   
