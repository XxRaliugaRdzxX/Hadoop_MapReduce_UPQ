# Equipo 6: La Suite TeraSort en Hadoop Mapreduce

## 1. Exploracion del Benchmark
La suite TeraSort mide el rendimiento del cluster procesando registros sinteticos de 100 bytes mediante 3 comandos en cadena:
- **'teragen'**: Genera datos aleatorios.
- **'terasort'**: Ordena los registros por su clave usando MapReduce.
-**'teravalidate'**: Verifica que el ordenamiento sea perfecto.

## 2. Instrucciones de Ejecucion (Reproducibilidad)

### dentro del contenedor ('hadoophadoop)

hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar teragen 10000 /tmp/teragen-input
hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar terasort /tmp/teragen-input /temp/terasort-output
hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar teravalidate /tmp/terasort-output /tmp/teravalidate-output
cat /tmp/teravalidate-output/part-r-00000
