# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo será una implementación directa del concenpo de implicación: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**función** ¿IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en lC3gica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en lógica propocisional    

_simbolos_  $$\leftarrow$$ una lista de símbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   

## Equivalencia, validez y satisfactibilidad
La **equivalencia lógica** presenta dos sentencias $$\alpha$$ y $$\beta$$ son equivalentes lógicamente si tienen los mismos valores de verdad en el mismo conjunto de modelos. Este concepto se representa con $$\alpha \Leftrightarrow \beta$$. Por ejemplo, podemos observar facilmente mediante una tabla que $$ P \wedge Q$$ y $$Q \vee P$$ son equivalentes lógicamente.
Una definición alternativa de equivalencia lógica es la siguiente: para dos sentencias $$\alpha$$ y $$\beta$$ cualesquiera,   
$$\alpha \equiv \beta $$ si y solo si $$\alpha \models  \beta$$ y $$\beta \models \alpha$$. (Recuerde que $$ \models $$ significa implicación).

