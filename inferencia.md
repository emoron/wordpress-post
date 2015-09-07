# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo ser� una implementaci�n directa del concenpo de implicaci�n: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**funciC3n** B?IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en lC3gica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en l�gica propocisional    

_simbolos_  $$\leftarrow$$ una lista de s�mbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   
