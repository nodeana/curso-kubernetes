# Módulo 4: Replicaset


Creamos un fichero para el **ReplicaSet** y lo editamos:

``vim nginx-rs.yaml``

Abrimos una terminal paralela, y ejecutamos el comando para visualizar el estado de los Pods actualizándose cada un segundo:

``watch -n 1 kubectl get rs,pods``

Para arrancar el ReplicaSet usamos el comando:

``kubectl apply -f nginx-rs.yaml``

Buscamos el nombre de un pod para eliminar (podemos verlo en la terminal paralela), y ejecutamos el siguiente comando para comprobar el funcionamiento:

``kubectl delete pod <Nombre-Del-Pod>``

Podemos escalar el número de Pods con el comando:

``kubectl scale rs replicaset-nginx --replicas=<Número-de-Pods>``

Para eliminar el ReplicaSet usamos:

``kubectl delete rs replicaset-nginx``

O también:

``kubectl delete -f nginx-rs.yaml``
