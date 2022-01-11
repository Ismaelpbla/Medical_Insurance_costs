
# Medical Insurance Costs project

This is a learning project from Codecademy. Where are going to analize the medical insurance costs of 1338 inputs.

I am going to use Exploratory Data Analysis to investigate wich ones of the variables have the most incidence in the medical charges.
After this exploration I found that  variable smoker has the most incidence both alone and with other variables like bmi. 



## Authors

- [@Ismaelpbla](https://www.github.com/Ismaelpbla)


## DATA

Para el proyecto de analisis de datos utilizaremos el csv proporcionado por Codecademy: insurance.csv

Un primer vistazo sobre los datos contenidos en ese csv, los podemos ver a continuación:

| id  |age  | sex   |bmi   |children   |smoker   |region   |charges   |
|---|---|---|---|---|---|---|---|
| 0  |19   | female  |27.900   |0   |yes   |southwest   |16884.92400   |
|  1 |  18 |   male|33.770   |1   |no   |southwest   |1725.55230   |
|   2|   28|   male|33.00   |3   |no   |southwest   |4449.46200   |

La información proporcionado en la tabla nos indica:
- age: la edad de la persona que paga el seguro
- sex: el sexo de la persona que paga el seguro
- bmi: el indice de grasa corporal de la persona
- children: la cantidad de hijos/as a su cargo
- smoker: Si la persona es fumadora o no
- region: Region de EEUU a la que pertenece la persona
- charges: Cantidad que le cobra la entidad seguradora al individuo


## METHODS

Usaremos el metodo de analisis exploratorio estadistico de los datos. Haciendo un primer analisis de cada una de las variables, y posteriomente viendo la relación que hay entre ellas

- Analisis de variables cuantitativas: Metodo kde y Boxplots
- Analisis de variables cualitativas: Metodo countplot e Histogramas
- Relacion entre variables cuantitativas y cualitativas: Metodo Lmplot, Violin plots
## ANALYSIS

Las variables cuantitativas de este proyecto son: bmi y charges. Sobre ellas se aplicó el metodo kde obteniendo lo siguiente

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/kdeplot.png)

Como se puede apreciar en la figura, la distribución del bmi es completamente normal mientas que la de charges presenta una asimetria, debida a la presencia de outliers tal y como se aprecia en los boxplots

Las variables cualitativas del proyecto son: sex, smoker, region, age y children.

Los tres primeros se han proyectado mediante graficos de barras con el metodo countplots

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/30f03294866592c7d06d106013ca365eaeb948c2/Figures/countplot.png)

En este caso puede observarse que en nuestra base de datos existe una mayor cantidad de personas de la region sudeste, que la proporcion de hombres y mujeres es similar y que la proporcion de fumadores es significativamente mayor que la de los no fumadores

Las otra variable cualitativa:age se ha proyectado a través de un histograma.

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/6388dcca73616fe1ff045287ebc8cfdc906b9513/Figures/histogram.png)

En estas figuras pueden observarse: Que los rangos de edad son muy diversos pero que sobretodo destaca la población joven cercana a los 20 años. Por otro lado se observa que existe una gran cantidad de gente sin hijos, aunque no es despreciable la cantidad de gente que tiene 1, 2 o hasta 3 hijos. Siendo muy pequeño el porcentaje de personas con 4 o mas hijos

### Relationship between variables

Como hemos podido ver al proyectar la variable de charges, existen personas que pagan una tasa mayor por su seguro que otras. Si observamos en detalle los outliers de esta variable:

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges_outliers.png)

En la figura puede verse, primero a la izquierda un zoom de la parte derecha de la primera figura. El siguiente grafico es el resultado de eliminar todos aquellos valores inferiores a 30000 para mostrar unicamente los valores extremos de charges. Finalmente se han proyectado estos valores en un boxplot.

Como puede apreciarse en la figura la distribución de los outliers de charges tienen una distribución normal. De esta forma podriamos tratarlos como un grupo aparte, un grupo de personas que pagan mas por su seguro. La pregunta es ¿Por qué? Veamoslo comparando las diferentes variables cualitativas en los dos grupos.

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/countplot2.png)


En esta figura pueden observarse diferencias en la distribución de la variables cualitativas en los dos grupos que hemos definido:
- La distribucion de edades es similar pero parece que existen dos grupos de edad entre 40 y 50 años y mayores a 60 años que es mas frecuente en el segundo grupo que en el primero.
- En el primer grupo existe mayor paridad (similar numero de hombres y de mujeres), no es el caso del segundo grupo en el que hay mas hombres que mujeres.
- Una de las variables en las que se observa mayor diferencia es en la de smoker. El numero de personas fumadoras en el primer grupo es muy pequeño en comparación con el de no fumadoras, mientras que en el segundo grupo es todo lo contrario
- En el primer grupo la cantidad de personas de las diferentes regiones esta bastante bien distribuida. En el segundo caso hay una mayor cantidad de personas del sudeste
- En el caso de los hijos puede observarse como la distribución es similar en ambos grupos, aunque en el segundo caso hay mayor cantidad de personas con 2 hijos que con 1.

Si hacemos una comparativa con violinplots obtendremos mayor información si cabe:

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/violin_plot2.png)

- No se observan diferencias significativas al comparar la distribución segun los sexos en ambos grupos
- Se vuelve a observar la diferencia notable entre numero de fumadores en un grupo y en otro. En el segun grupo además cabe destacar que los no fumadores no presentan valores muy lejos de la media y la mediana. Mientras que el de los fumadores sí. Esto quiere decir que los no fumadores, independientemente de las otras variables suelen pagar lo mismo, mientras que los fumadores tienen una mayor variabilidad en lo que pagan.
- Es curioso como en el segundo grupo puede observarse una distribución bimodal para las personas que viven en la soutwest region, algo que no se ve en el resto de regiones.
- La distribución del numero de hijos con respecto a los charges, es mas o menos normal excepto en el caso de personas sin hijos del primer grupo. En este caso se ve una clara disposición bimodal.

Finalmente vamos a ver como se relacionan las dos variables cuantitativas: bmi y charges. Para ello proyectaremos dos graficas una para el primer grupo y otra para el segundo:

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges%20vs%20bmi%20standar.png)

![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges%20vs%20bmi%20outliers.png)

En la figura de arriba hemos proyectado los valores bmi y charges para el primer grupo, en la figura de abajo hemos proyectado lo mismo para el segundo grupo.
No obstante la información que obtenemos de estas figuras no es del todo relevante, hasta que proyectamos una tercera variable: smoker. Cuando hacemos este vemos dos cosas:
- Que en el primer grupo hay dos concentraciones de puntos unos (los fumadores) pagan significativamente mas que los otros (naranjas). En ambos cuanto mayor grasa corporal (bmi) tienes, mas vas a pagar, ya que existe una correlación positiva en ambas rectas. Sin embargo la recta que define la relación entre charges y bmi tiene una pendiente mayor en el grupo de fumadores que en el de no fumadores.
- Que el segundo grupo esta compuesta mayoritariamente por fumadoresteniendo una relación positiva entre bmi y charges. Observese que aunque hay pocos no fumadores y la población por lo tanto no es significativa, la pendiente de la recta es similar a la obtenida en el grupo anterior.
## CONCLUSIONS

El analisis de los datos nos hace establecer varias conclusiones. La primera, y mas obvia es que no todo el mundo paga lo mismo por su seguro. Pero no solamente sabemos eso de los datos, sabemos además
que existe un numero de personas que paga significativamente más que el resto. Y de hecho eso lo hemos podido ver en la figura a y en la figura d.

La pregunta que suscita esto es ¿Por qué ese grupo de personas paga mas cantidad que el resto? Para ello, y a través de las comparaciones de las diferentes variables entre el grupo que paga mas y el grupo que paga menos (figuras e y f)
se puede ver como, pese a las diferecias observables en todas las variables la que mas destaca es la variable smoker. Esta variable de hecho es practicamente opuesta en un grupo y en otro, es decir, que mientras en un grupo la mayoría son
no fumadores, en el otro son fumadores.

Esto no acaba aqui si no que además podemos ver como el hecho de ser fumador o no tambien influencia significativamente en lo que pagas, sobretodo si tu indice de masa corporal (bmi) es elevado (figura g)

¿Por qué hay un grupo de personas que significativamente pagan mas que otras? Se puede responder que, aunque otras variables como el numero de hijos/as (children) o la edad (age) incrementen el precio del seguro, es la variable smoker la que mas influencia dicho precio.
De hecho tal y como se puede ver en la figura z, la mayor parte de las personas que componen el grupo que más paga, son fumadoras.

La influencia de la variable smoker es tal, que cuando se se le suman otras variables como el bmi, se puede observar como una persona fumadora cuanto mayor bmi tiene va a pagar hasta dos veces más que otra persona no fumadora con el mismo bmi.
