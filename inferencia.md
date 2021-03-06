# Agentes L�gicos
El componente principal de un agente basado en conocimiento es su base de conocimiento. Usualmente una BC es un conjunto de sentencias, similares a las sentencias en ingl�s, u otros lenguajes naturales. Cada sentencia se presenta en un lenguaje denominado, lenguaje de representaci�n de conocimiento. Y se representa alguna aserci�n acerca del mundo, debe haber un mecanismo para a�adir nuevas sentencias a la base de conocimiento, y uno para preguntar qu� se sabe en la base de conocimiento. Los nombres est�ndar para estas dos tareas son Decir y Preguntar, respectivamente. Ambas tareas requieren realizar inferencia, es decir, derivar nuevas sentencias a partir de las antiguas.
L�gica
Conceptos Fundamentales
Una l�gica nos permite definir la sem�ntica del lenguaje. Si lo relacionamos con el lenguaje hablado, la sem�ntica trata "el significado" de las sentencias. En l�gica, esta definici�n bastante m�s precisa
L�gica Proposicional
La sintaxis de la l�gica proposicional nos define las sentencias que se pueden construir. Las sentencias at�micas (es decir, los elementos sint�cticos indivisibles) se componen de un �nico s�mbolo proposicional. Cada uno de estos s�mbolos representa una proposici�n que puede ser verdadera o falsa. Utilizaremos letras may�sculas para estos s�mbolos: P, Q, R y siguientes. Los nombres de los s�mbolos suelen ser arbitrarios pero a menudo se escogen de manera que tengan alg�n sentido mnemot�cnico para el lector.

Las sentencias complejas se construyen a partir de sentencias m�s simples mediante el uso de la conectivas l�gicas, que son las siguientes:
$\neg$  (no). Una sentencia como W1,3 se denomina negaci�n de $$W_{1,3}$$. Un Literal puede ser una sentencia at�mica ( un literal positivo )  o una sentencia at�mica negada (un literal negativo).   
$$\wedge$$ (y) Una sentencia que tenga como conectiva principal , como es (W1,3 H3,1), se denomina conjunci�n. sus componentes son los conjuntores. 

$$\vee$$ (o). Una sentencia que utiliza la conectiva , como es $$(W_{1,3} H_{3,1})W_{2,2}$$, es una disyunci�n de los disyuntores $$(W_{1,3}H_{3,1})$$ y $$W_{2,2}$$.  
$$\Rightarrow$$ (implica). Una sentencia como $$(W_{1,3}H_{3,1})W_{2,2} $$ se denomina implicaci�n (o condicional). Su premisa es $$W_{1,3}H_{3,1}$$ y su conclusi�n o consecuente es $$W_{2,2}$$. Las implicaciones se conocen como reglas o afirmaciones si-entonces. Algunas veces, en otros libros el s�mbolo de la implicaci�n se representa mediante $$\cup$$ o $$\cap$$ .


# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo ser� una implementaci�n directa del concenpo de implicaci�n: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**funci�n** �IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en l�gica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en l�gica propocisional    

_simbolos_  $$\leftarrow$$ una lista de s�mbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   

## Equivalencia, validez y satisfactibilidad
La **equivalencia l�gica** presenta dos sentencias $$\alpha$$ y $$\beta$$ son equivalentes l�gicamente si tienen los mismos valores de verdad en el mismo conjunto de modelos. Este concepto se representa con $$\alpha \Leftrightarrow \beta$$. Por ejemplo, podemos observar facilmente mediante una tabla que $$ P \wedge Q$$ y $$Q \vee P$$ son equivalentes l�gicamente.
Una definici�n alternativa de equivalencia l�gica es la siguiente: para dos sentencias $$\alpha$$ y $$\beta$$ cualesquiera,   
$$\alpha \equiv \beta $$ si y solo si $$\alpha \models  \beta$$ y $$\beta \models \alpha$$. (Recuerde que $$ \models $$ significa implicaci�n).

El segundo concepto que requerimos es el de **validez**. Una sentencia es v�lida si es verdadera en todos los modelos. Por ejemplo, la sentencia $$P \wedge \neg P$$ es una sentencia v�lida. Las sentencias v�lidas se conocen como **tautolog�as** son necesariamente verdaderas y por lo tanto vacias de significado.
�Que utilidad tienen las sentencias v�lidad? De nuestra definici�n podemos derivar el **teorema de la deducci�n** de la siguiente manera:   

_Para cualquier sentencia_ $$\alpha$$ y $$\beta$$, $$\alpha \equiv \beta$$, _si y solo si la sentencia__ $$(\alpha \Rightarrow \beta)$$ __es v�lida_   

El �ltimo concepto que requerimos es el de **satisfactibilidad**. Una sentencia es satisfactoria si es verdadera para _alg�n_ modelo. Por ejemplo, en la base de conocimiento ya mostrada, $$R_1 \wedge R_2 \wedge R_3 \wedge R_4 \wedge R_5 $$ es _satisfacible_ por que hay tres modelos en los que es verdadera. Si una sentencia $$\alpha$$ es verdadera en un modelo _m_ , entonces decimos que _m_ **satisface** $$\alpha$$, o que _m_ **es un modelo de** $$\alpha$$. 

Las _satisfactibilidad_ se puede averiguar enumerando los modelos posibles hasta que uno satisface la sentencia. La determinaci�n de la _satisfactibilidad_ de sentencias en l�gica proposicional fue el primer problema que se demostr� que era NP-completo.

| $$\alpha \wedge \beta$$| $$\equiv$$ |$$\beta \wedge \alpha$$ Conmutatividad de $$\wedge$$ |
|---------------------------------|---------|---------------------------------------------------------------------------------------------------------|
| $$\alpha \vee \beta$$                        | $$\equiv$$ | $$\beta \vee \alpha$$ Conmutatividad de $$\vee$$                                                            |
| $$((\alpha \wedge \beta) \wedge \gamma )$$   | $$\equiv$$ | $$(\alpha \wedge (\beta \wedge \gamma )$$ Asociatividad de $$\wedge$$                                       |
| $$((\alpha \vee \beta) \wedge \gamma )$$     | $$\equiv$$ | $$(\alpha \vee (\beta \vee \gamma )$$ Asociatividad de $$\vee$$                                             |
| $$\neg (  \neg \alpha )    $$                | $$\equiv$$ | $$\alpha$$ Eliminaci�n de la doble negaci�n                                                               |
| $$( \alpha \Leftarrow \beta)$$               | $$\equiv$$ | $$(\neg \beta \Leftarrow \neg \alpha)$$ Contraposici�n                                                    |
| $$( \alpha \Leftarrow \beta)$$               | $$\equiv$$ | $$( \neg \alpha \vee \beta)$$  Eliminaci�n de la implicaci�n                                              |
| $$( \alpha \Leftrightarrow \beta)$$          | $$\equiv$$ | $$(( \alpha \Rightarrow \beta) \wedge ( \beta \leftarrow \alpha))$$                                        |
| $$ \neg ( \alpha \wedge \beta)$$             | $$\equiv$$ | $$( \neg \alpha \vee \neg \beta)$$   Ley de Morgan                                                        |
| $$ \neg ( \alpha \vee \beta )$$              | $$\equiv$$ | $$ ( \neg alpha \wedge  \neg \beta)$$  Ley de Morgan                                                      |
| $$( \alpha \wedge ( \beta \vee \gamma ) )$$ | $$\equiv$$ | $$ ((\alpha \wedge \beta) \vee ( \alpha \wedge \gamma )) $$ Distribuci�n de $$ \wedge $$ respecto a $$\vee $$ |
| $$(\alpha \vee ( \beta \wedge \gamma ))$$  |   $$\equiv$$      | $$((\alpha \vee \beta) \wedge ( \alpha \vee \beta )) $$                                                   |

## Patrones de razonamiento en l�gica proposicional
Existen las llamadas **reglas de inferencia**, la m�s conocida es la llamada **Modus Ponens** que se escribe como sigue:   

$$\frac{\alpha \Rightarrow \beta,    \alpha }{\beta}$$   
La notaci�n nos dice que, cada vez que encontramos dos sentencias en la forma $$\alpha \Rightarrow \beta$$ y $$\alpha$$, entonces la sentencia $$\beta$$ puede ser inferida. Por ejemplo, si tenemos $$(WumpusEnFrente \wedge WumpusVivo)$$, entonces se puede inferir $$Disparar$$.
Otra regla de inferencia util es la **Eliminaci�n-$$\wedge$$** que expresa que, de una conjunci�n se puede inferir cualquiera de sus conjuntores:   

$$\frac{\alpha \vee \beta}{\alpha}$$

Por ejemplo, de $$(WumpusEnFrente \vee WumpusVivo)$$, se puede inferir $$WumpusVivo$$. Teniendo en cuenta los posibles valores de verdad de $$\alpha$$
y $$\beta$$ se pueden observar f�cilmente, de una s�la vez, que el Modus Ponens y la Eliminaci�n-$$\wedge$$ son reglas s�lidas.

## Un algoritmo de resoluci�n

**funci�n** Resoluci�n-LP(BC,$$\alpha$$) **devuelve** *verdadero* o *falso*   
 **entradas** BC, la base de conocimiento, una sentencia en l�gica proposicional $$\alpha$$, la petici�n, una sentencia en l�gica proposicional.   
 *cl�usulas* $$\leftarrow$$ el conjunto de cl�usulas de BC $$\wedge \neg \alpha$$ en representaci�n FNC   
 *nueva* $$\leftarrow$$ {}   
 **bucle hacer**
 **para cada** $$C_i$$,$$C_j$$ **en** cl�usulas **hacer**  
 *resolventes* $$\leftarrow$$ contiene la cl�usula vac�a **entonces devolver** *verdadero*   
 *nueva* $$\leftarrow$$ *nueva*  $$\cup$$ *resolventes*   
 **si** *nueva* $$\subseteq$$ *cl�usulas* **entonces devolver** *falso*  
 *cl�usulas* $$\leftarrow$$ *cl�usulas* $$\cup$$ *nueva*

