# Estrategias comerciales con datos

El objetivo de este proyecto es estimar la cantidad de personas que tuvieron la oportunidad de ver la pantalla en cada hora del día. A esto lo llamamos audiencia potencial, es decir, personas que pasaron por la zona y podrían haber visto el anuncio. No indica cuántas personas efectivamente miraron la pantalla ni cuantas recordaron el anuncio. 

Se detectan seis clases de objetos con un modelo pre entrenado: personas, camiones, buses, motos y bicicletas, que estén en circulación por la zona. La cámara ve a los peatones y a quienes van en moto o bicicleta. No ve a quienes viajan dentro de autos y buses, a esas personas las estimamos con un supuesto de ocupantes por vehículo. 

Contamos objetos que pasan, no objetos que se ven. El video es una sucesión de imágenes. Una persona que tarda en cruzar aparece en varias imágenes; si contáramos lo que se ve en cada imagen, la contaríamos más de una vez. Por esto seguimos a cada objeto de una imagen a la siguiente y le asignamos un número de identificación, para contarlo una sola vez. 

Un objeto (persona, auto, bus, camión, moto o bicicleta) se cuenta si el sistema lo sigue durante al menos 1 segundo. Los registros de menos de 1 segundo suelen ser errores: pedazos de un objeto que el sistema perdió de vista y volvió a encontrar, o falsas detecciones. Las personas que esperan el bus también se cuentan, porque están expuestas a la pantalla. Esta regla no distingue a los vehículos estacionados de los que circulan, por lo que estos también se cuentan; lo analizamos como una limitación.

