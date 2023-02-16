# Módulo 3: Pods


Creamos un fichero pod.yaml:

``vim pod.yaml``

(Opcional) Es posible crear un Pod directamente

``kubectl run <Nombre-del-Pod> --image=<Nombre-de-la-Imagen>``

Por ejemplo:

``kubectl run pod-nginx --image=nginx``

Podemos crear directamente el Pod desde el fichero yaml:

``kubectl create -f pod.yaml``

Podemos ver el estado en el que se encuentra el Pod:

``kubectl get pods``

Si queremos ver más información sobre los Pods, como por ejemplo, saber en qué nodo del cluster se está ejecutando:

``kubectl get pod -o wide``

Para obtener información más detallada del Pod (equivalente al inspect de docker):

``kubectl describe pod pod-nginx``

Podríamos editar el Pod (requiere conocimientos avanzados) y ver todos los atributos que definen el objeto, la mayoría de ellos con valores asignados automáticamente por el propio Kubernetes y podremos actualizar ciertos valores:

``kubectl edit pod pod-nginx``

Para obtener los registros de eventos del Pod:

``kubectl logs pod-nginx``

Para ejecutar un comando dentro del Pop:

``kubectl exec -it pod-nginx -- /bin/bash``

Podemos acceder al servicio ejecutándose en el Pod, redirigiendo un puerto de localhost al puerto del Pod:

``kubectl port-forward pod-nginx 8080:80``

Para obtener las etiquetas de los Pods que hemos creado:

``kubectl get pods --show-labels``

Añadir etiquetas a un Pod creado:

``kubectl label pods pod-nginx service=web --overwrite=true``

Visualizar los Pods con una etiqueta específica, por ejemplo web:

``kubectl get pods -l service=web``

También, podemos visualizar los valores de las etiquetas como una nueva columna:

``kubectl get pods -Lservice``

Para poder eliminar un Pod:

``kubectl delete pod <Nombre-del-Pod>``

En este ejemplo:

``kubectl delete pod pod-nginx``

