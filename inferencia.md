# Agentes Lógicos
El componente principal de un agente basado en conocimiento es su base de conocimiento. Usualmente una BC es un conjunto de sentencias, similares a las sentencias en inglés, u otros lenguajes naturales. Cada sentencia se presenta en un lenguaje denominado, lenguaje de representación de conocimiento. Y se representa alguna aserción acerca del mundo, debe haber un mecanismo para añadir nuevas sentencias a la base de conocimiento, y uno para preguntar qué se sabe en la base de conocimiento. Los nombres estándar para estas dos tareas son Decir y Preguntar, respectivamente. Ambas tareas requieren realizar inferencia, es decir, derivar nuevas sentencias a partir de las antiguas.
Lógica
Conceptos Fundamentales
Una lógica nos permite definir la semántica del lenguaje. Si lo relacionamos con el lenguaje hablado, la semántica trata "el significado" de las sentencias. En lógica, esta definición bastante más precisa
Lógica Proposicional
La sintaxis de la lógica proposicional nos define las sentencias que se pueden construir. Las sentencias atómicas (es decir, los elementos sintácticos indivisibles) se componen de un único símbolo proposicional. Cada uno de estos símbolos representa una proposición que puede ser verdadera o falsa. Utilizaremos letras mayúsculas para estos símbolos: P, Q, R y siguientes. Los nombres de los símbolos suelen ser arbitrarios pero a menudo se escogen de manera que tengan algún sentido mnemotécnico para el lector.

Las sentencias complejas se construyen a partir de sentencias más simples mediante el uso de la conectivas lógicas, que son las siguientes:
$\neg$  (no). Una sentencia como W1,3 se denomina negación de $$W_{1,3}$$. Un Literal puede ser una sentencia atómica ( un literal positivo )  o una sentencia atómica negada (un literal negativo).   
$$\wedge$$ (y) Una sentencia que tenga como conectiva principal , como es (W1,3 H3,1), se denomina conjunción. sus componentes son los conjuntores. 

$$\vee$$ (o). Una sentencia que utiliza la conectiva , como es $$(W_{1,3} H_{3,1})W_{2,2}$$, es una disyunción de los disyuntores $$(W_{1,3}H_{3,1})$$ y $$W_{2,2}$$.  
$$\Rightarrow$$ (implica). Una sentencia como $$(W_{1,3}H_{3,1})W_{2,2} $$ se denomina implicación (o condicional). Su premisa es $$W_{1,3}H_{3,1}$$ y su conclusión o consecuente es $$W_{2,2}$$. Las implicaciones se conocen como reglas o afirmaciones si-entonces. Algunas veces, en otros libros el símbolo de la implicación se representa mediante $$\cup$$ o $$\cap$$ .


# Inferencia
Recordemos que el objetivo de la inferencia es decidir si $$BC |= \alpha$$ para alguna $$\alpha$$. Por ejemplo se deduce $$H_{2,2}$$. Nuestro primer algoritmo será una implementación directa del concenpo de implicación: enumerar los modelos y averiguar si $$\alpha$$ es verdadera en cada modelo en el que la **BC** es verdadera.   

**función** ¿IMPLICACIONES-EN-TV?(BC,$$\alpha$$) **devuelve** verdadero o falso   
**entradas:** BC, la base de conocimiento, una sentencia en lógica propocisional
$$\alpha$$, la sentencia implicada, una sentencia en lógica propocisional    

_simbolos_  $$\leftarrow$$ una lista de símbolos propocisionales de la BC y $$\alpha$$   
**devuelve**  Comprobar-TV(BC,$$\alpha$$)   

## Equivalencia, validez y satisfactibilidad
La **equivalencia lógica** presenta dos sentencias $$\alpha$$ y $$\beta$$ son equivalentes lógicamente si tienen los mismos valores de verdad en el mismo conjunto de modelos. Este concepto se representa con $$\alpha \Leftrightarrow \beta$$. Por ejemplo, podemos observar facilmente mediante una tabla que $$ P \wedge Q$$ y $$Q \vee P$$ son equivalentes lógicamente.
Una definición alternativa de equivalencia lógica es la siguiente: para dos sentencias $$\alpha$$ y $$\beta$$ cualesquiera,   
$$\alpha \equiv \beta $$ si y solo si $$\alpha \models  \beta$$ y $$\beta \models \alpha$$. (Recuerde que $$ \models $$ significa implicación).

El segundo concepto que requerimos es el de **validez**. Una sentencia es válida si es verdadera en todos los modelos. Por ejemplo, la sentencia $$P \wedge \neg P$$ es una sentencia válida. Las sentencias válidas se conocen como **tautologías** son necesariamente verdaderas y por lo tanto vacias de significado.
¿Que utilidad tienen las sentencias válidad? De nuestra definición podemos derivar el **teorema de la deducción** de la siguiente manera:   

_Para cualquier sentencia_ $$\alpha$$ y $$\beta$$, $$\alpha \equiv \beta$$, _si y solo si la sentencia__ $$(\alpha \Rightarrow \beta)$$ __es válida_   

El último concepto que requerimos es el de **satisfactibilidad**. Una sentencia es satisfactoria si es verdadera para _algún_ modelo. Por ejemplo, en la base de conocimiento ya mostrada, $$R_1 \wedge R_2 \wedge R_3 \wedge R_4 \wedge R_5 $$ es _satisfacible_ por que hay tres modelos en los que es verdadera. Si una sentencia $$\alpha$$ es verdadera en un modelo _m_ , entonces decimos que _m_ **satisface** $$\alpha$$, o que _m_ **es un modelo de** $$\alpha$$. 

Las _satisfactibilidad_ se puede averiguar enumerando los modelos posibles hasta que uno satisface la sentencia. La determinación de la _satisfactibilidad_ de sentencias en lógica proposicional fue el primer problema que se demostró que era NP-completo.

| $$\alpha \wedge \beta$$| $$\equiv$$ |$$\beta \wedge \alpha$$ Conmutatividad de $$\wedge$$ |
|---------------------------------|---------|---------------------------------------------------------------------------------------------------------|
| $$\alpha \vee \beta$$                        | $$\equiv$$ | $$\beta \vee \alpha$$ Conmutatividad de $$\vee$$                                                            |
| $$((\alpha \wedge \beta) \wedge \gamma )$$   | $$\equiv$$ | $$(\alpha \wedge (\beta \wedge \gamma )$$ Asociatividad de $$\wedge$$                                       |
| $$((\alpha \vee \beta) \wedge \gamma )$$     | $$\equiv$$ | $$(\alpha \vee (\beta \vee \gamma )$$ Asociatividad de $$\vee$$                                             |
| $$\neg (  \neg \alpha )    $$                | $$\equiv$$ | $$\alpha$$ Eliminación de la doble negación                                                               |
| $$( \alpha \Leftarrow \beta)$$               | $$\equiv$$ | $$(\neg \beta \Leftarrow \neg \alpha)$$ Contraposición                                                    |
| $$( \alpha \Leftarrow \beta)$$               | $$\equiv$$ | $$( \neg \alpha \vee \beta)$$  Eliminación de la implicación                                              |
| $$( \alpha \Leftrightarrow \beta)$$          | $$\equiv$$ | $$(( \alpha \Rightarrow \beta) \wedge ( \beta \leftarrow \alpha))$$                                        |
| $$ \neg ( \alpha \wedge \beta)$$             | $$\equiv$$ | $$( \neg \alpha \vee \neg \beta)$$   Ley de Morgan                                                        |
| $$ \neg ( \alpha \vee \beta )$$              | $$\equiv$$ | $$ ( \neg alpha \wedge  \neg \beta)$$  Ley de Morgan                                                      |
| $$( \alpha \wedge ( \beta \vee \gamma ) )$$ | $$\equiv$$ | $$ ((\alpha \wedge \beta) \vee ( \alpha \wedge \gamma )) $$ Distribución de $$ \wedge $$ respecto a $$\vee $$ |
| $$(\alpha \vee ( \beta \wedge \gamma ))$$  |   $$\equiv$$      | $$((\alpha \vee \beta) \wedge ( \alpha \vee \beta )) $$                                                   |

## Patrones de razonamiento en lógica proposicional
Existen las llamadas **reglas de inferencia**, la más conocida es la llamada **Modus Ponens** que se escribe como sigue:   

$$\frac{\alpha \Rightarrow \beta,    \alpha }{\beta}$$   
La notación nos dice que, cada vez que encontramos dos sentencias en la forma $$\alpha \Rightarrow \beta$$ y $$\alpha$$, entonces la sentencia $$\beta$$ puede ser inferida. Por ejemplo, si tenemos $$(WumpusEnFrente \wedge WumpusVivo)$$, entonces se puede inferir $$Disparar$$.
Otra regla de inferencia util es la **Eliminación-$$\wedge$$** que expresa que, de una conjunción se puede inferir cualquiera de sus conjuntores:   

$$\frac{\alpha \vee \beta}{\alpha}$$

Por ejemplo, de $$(WumpusEnFrente \vee WumpusVivo)$$, se puede inferir $$WumpusVivo$$. Teniendo en cuenta los posibles valores de verdad de $$\alpha$$
y $$\beta$$ se pueden observar fácilmente, de una sóla vez, que el Modus Ponens y la Eliminación-$$\wedge$$ son reglas sólidas.


