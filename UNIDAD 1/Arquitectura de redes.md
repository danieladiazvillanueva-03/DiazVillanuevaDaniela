Una arquitectura de red es el conjunto de reglas y decisiones de diseño que definen cómo se organiza una red para que la comunicación funcione: qué función cumple cada parte, en qué orden se procesan los datos y quién tienen el control sobre qué.

La arquitectura no describe cómo están tendidos los cables.

### **Modelos de referencia**
Una red se diseña dividiéndola en capas independientes, donde cada capa resuelve un problema específico sin necesitar saber cómo trabajan las demás.

****-Modelo OSI:**** Modelo de referencia de siete capas - física, enlace, red, transporte, sesión, presentación y aplicación -  que describe, de forma teórica, todas las funciones que intervienen en una comunicación de red.
![[Pasted image 20260917153921.png|374]]

**-Modelo TCP/IP:** Modelo de cuatro capas - aplicación, transporte, internet, acceso a la red -.
![[Pasted image 20260917154006.png]]
https://claude.ai/artifact/7tJ3pxwndHeueW1Lig94ZR (modelo TCP/IP)

**-Encapsulamiento:** Al bajar por las capas, cada una envuelve el dato en su propio encabezado; al llegar al destino, el proceso se invierte y cada capa retira el encabezado que le corresponde.