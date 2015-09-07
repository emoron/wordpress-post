# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo ser� una implementaci�n directa del concenpo de implicaci�n: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**funci�n** �IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en lC3gica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en l�gica propocisional    

_simbolos_  $$\leftarrow$$ una lista de s�mbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   

## Equivalencia, validez y satisfactibilidad
La **equivalencia l�gica** presenta dos sentencias $$\alpha$$ y $$\beta$$ son equivalentes l�gicamente si tienen los mismos valores de verdad en el mismo conjunto de modelos. Este concepto se representa con $$\alpha \Leftrightarrow \beta$$. Por ejemplo, podemos observar facilmente mediante una tabla que $$ P \wedge Q$$ y $$Q \vee P$$ son equivalentes l�gicamente.
Una definici�n alternativa de equivalencia l�gica es la siguiente: para dos sentencias $$\alpha$$ y $$\beta$$ cualesquiera,   
$$\alpha \equiv \beta $$ si y solo si $$\alpha \models  \beta$$ y $$\beta \models \alpha$$. (Recuerde que $$ \models $$ significa implicaci�n).

