# El equipo Aston Martin de F1 te acaba de fichar para que ayudes con la estrategía de la próxima carrera.
# El tiempo medio por vuelta es de 1 min y 30 segundos por cada vuelta que demos
# desgastamos un 1.15% la vida de los neumáticos y el tiempo por vuelta aumenta en 2 decimas por cada vuelta.
# Cuando hacemos una parada volvemos a tener las ruedas al 100% y a dar la vuelta
# en 1'30''. Escribe una función en python que devuelva cuanto tiempo tardará el piloto en dar n vueltas
# parando cuando los neumáticos lleguen a un porcentaje x de desgaste.
# siendo las vueltas y el porcentaje de desgaste parámetros iniciales de la función.

# iniciamos definiendo la función
def calcular_tiempo_total(vueltas, porcentaje_desgaste_max):
    tiempo_por_vuelta = 90 
    desgaste = 0 
    tiempo_total = 0  
    parada_boxes = 25 
    aumento_tiempo_por_vuelta = 0.2  
# bucle para que se sume el tiempo de la vuelta al tiempo total
    for vueltas in range(1, vueltas + 1):
        tiempo_total += tiempo_por_vuelta
        desgaste += 1.15  
# Si el desgaste es mayor al máximo desgaste hacemos parada en boxes y se reinicia el tiempo de vuelta a 90.
        if desgaste >= porcentaje_desgaste_max:
            tiempo_total += parada_boxes
            desgaste = 0
            tiempo_por_vuelta = 90  
        

        tiempo_por_vuelta += aumento_tiempo_por_vuelta
    
# Devolvemos resultado en minutos
    tiempo_total_minutos = tiempo_total / 60
    return tiempo_total_minutos
# Ponemos los parámetros
vueltas = 60
porcentaje_desgaste_max = 50  
resultado = calcular_tiempo_total(vueltas, porcentaje_desgaste_max)
print("El tiempo total es:", resultado, "minutos")
