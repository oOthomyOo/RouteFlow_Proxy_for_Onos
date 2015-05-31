# RouteFlow_Proxy_for_Onos

#  Aviso
Este es un avance del proyecto de Google summer of code 2015 titulado RouteFlow Proxy for Onos.
Cualquier consulta, ayuda, aporte, comentario, critica sobre este tema sera aceptado coordialmente, para asi poder realizar unaversion actualizada de la misma

#  Bienvenidos
Esta versión de RouteFlow es una versión de desarrolladores destinados a evaluar RouteFlow para proporcionar servicios de enrutamiento IP virtualizados en uno o más interruptores OpenFlow.
 
Usted puede aprender más sobre RouteFlow en el siguiente Blog (http://routeflowproxyforonos.blogspot.com/)

 
#  Visión general de distribución
 RouteFlow es una distribución compuesta por tres aplicaciones básicas: RFClient, RFServer y RFProxy.
 
 * RFClient ejecuta como un demonio en la máquina virtual (VM), la detección de cambios en el Linux ARP y tablas de enrutamiento. Información de enrutamiento se envía al RFServer cuando hay una actualización.
 
 * RFServer es una aplicación independiente que administra las máquinas virtuales corriendo los demonios RFClient. El RFServer mantiene la asignación entre las instancias RFClient VM y las interfaces y los interruptores correspondientes y puertos. Se conecta a RFProxy encomendarle que sobre cuándo configurar flujos y también para configurar el vSwitch abierto para mantener la conectividad en el entorno virtual formado por el conjunto de máquinas virtuales.
 
 * RFProxy es una aplicación (por POX y otros controladores) responsable de las interacciones con los switches OpenFlow (identificados por datapaths) a través del protocolo OpenFlow. Se escucha a las instrucciones del RFServer y notifica sobre los eventos en la red. Recomendamos ejecutar POX cuando usted está experimentando y probando su red. Otras implementaciones en diferentes controladores estarán disponibles en breve.
 
También hay una biblioteca de funciones comunes (rflib). Tiene implementaciones del IPC, utilidades como tipos personalizados para IP y direcciones MAC manipulación y creación de mensajes OpenFlow.
 
