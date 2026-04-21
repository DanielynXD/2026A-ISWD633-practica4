# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus=<número de núcleos>
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus=<lista de núcleos>
```

**¿Como saber el numero de procesadores virtuales que tiene una máquina?**
Podemos usar el comando echo %NUMBER_OF_PROCESSORS% en cmd y un comando docker que es 'docker info' y buscar la línea CPUs.
<img width="528" height="67" alt="image" src="https://github.com/user-attachments/assets/85e9ff92-907d-47fe-a0fe-33c55a36dabc" />
<img width="320" height="60" alt="image" src="https://github.com/user-attachments/assets/b9335827-1731-40e8-880c-4107df86368e" />
<img width="612" height="159" alt="image" src="https://github.com/user-attachments/assets/26848c4e-8118-4fe2-b353-67e8297807b6" />


## Ejemplos
_Puedes copiar y ejecutar directamente cada uno de los comandos_

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine
```
