https://capital.com/referafriend?c=kaec2x7i&pid=referral&src=inviteFriends&license=BAHEditar

Avance
Cargando vista previa 

#Este es un flujo de trabajo básico para ayudarle a comenzar con Acciones.

nombre:CI

#Controla cuándo se ejecutará el flujo de trabajo
en:
  #Activa el flujo de trabajo en eventos de solicitud push o pull, pero solo para la rama "principal"
  empujar:
    sucursales:[ "principal" ]
  solicitud de extracción:
    sucursales:[ "principal" ]

  #Le permite ejecutar este flujo de trabajo manualmente desde la pestaña Acciones
  envío_flujo de trabajo:

#Una ejecución de flujo de trabajo se compone de uno o más trabajos que se pueden ejecutar de forma secuencial o en paralelo.
trabajos:
  #Este flujo de trabajo contiene un único trabajo llamado "compilación"
  construir:
    #El tipo de corredor en el que se ejecutará el trabajo.
    se ejecuta en:ubuntu-último

    #Los pasos representan una secuencia de tareas que se ejecutarán como parte del trabajo.
    pasos:
      #Revisa tu repositorio en $GITHUB_WORKSPACE, para que tu trabajo pueda acceder a él
      -usos:acciones/pago@v4

      #Ejecuta un solo comando usando el shell de corredores
      -nombre:Ejecute un script de una línea
        correr:echo ¡Hola mundo!

      #Ejecuta un conjunto de comandos usando el shell de corredores
      -nombre:Ejecutar un script de varias líneas
        correr:|
          echo Añade otras acciones para construir,
          haga una prueba de eco e implemente su proyecto.
