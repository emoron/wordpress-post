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

