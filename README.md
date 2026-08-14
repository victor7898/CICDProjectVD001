# CICDProjectVD001
Este repositorio consta de entregables para el proyecto final del curso de ingenieria de datos 
# Descripción del repositorio: CICDProjectVD001

## Descripción general

CICDProjectVD001 es un proyecto orientado a la implementación de prácticas de Integración Continua y Despliegue Continuo (CI/CD) para la automatización del ciclo de vida del desarrollo de software y de los procesos de ingeniería de datos.

El objetivo principal del proyecto es automatizar la validación, compilación, prueba e implementación del código mediante herramientas de control de versiones y orquestación de flujos de trabajo, reduciendo los tiempos de entrega, minimizando los errores manuales y garantizando la calidad del software.

## Objetivos del proyecto

* Automatizar la integración del código.
* Estandarizar el proceso de desarrollo.
* Implementar controles de calidad.
* Ejecutar pruebas automáticas.
* Desplegar los cambios de forma controlada.
* Facilitar la colaboración entre los equipos de desarrollo.

## Arquitectura del proyecto

El flujo de trabajo del repositorio sigue las siguientes etapas:

![](/Workspace/Users/victormauriciodelgadomontoya@hotmail.com/CICDProjectVD001/Evidencias/Arquitectura.png)

1.	Creación de ambiente en azure
- a.	Creación de grupo de recursos VD-PROJECT
- b.	Creación de Azure Databrics 
    - Ambiente de desarrollo  adbPojectVD001dev 
    - Ambiente  Productivo adbPojectVD001Prod
- c.	Creación de storage account adbstoragevd001
    - Creación de container 
        - 1.	Raw
        - 2.	Metastore
        - 3.	metastore-adb
        - 4.	bronze
        - 5.	silver
        - 6.	golden
- d.	Creación de Azure Conector para Azure Databricks
- e.	Creación de Managed Identity dbmanagedidentity
- f.	Asignar Managed Identity a Access Conector
- g.	Permiso de Contributor al ADLS asignando los roles.
    - Storage Account Contributor
    - Storage Blob Data Contributor
    - EventGrid EventSubscription Contributor
    - torage Queue Data Contributor

2.	Creación de ambiente de en databricks.
- a.	Creación de Cluster ClusterProyectVD
- b.	Creación de MetaStore metastoreprojectvd
    - Creación de usuarios
    - Creación de grupos de usuarios
        - 1.	Analytics
        - 2.	DataScientist
        - 3.	DBA
        - 4.	Engineer
- c.	Eliminació de Cluster ClusterProyectVD del ambiente adbPojectVD001dev y creación del adbPojectVD001Prod para ejecución final

3.	Creación repositorio en GitHub para ejecución automática del procedimiento.
- a.	Repositorio CICDProjectVD001
- b.	Conexión entre GitHub y Databricks
    - Creación de secretos 
        - 1.	Host_Origen
        - 2.	Token_Origen
        - 3.	Host_Destino
        - 4.	Token_Destino
- c.	Creación de .YML para ejecución automática 
- d.	Creación de carpetas en para ejecución del .YML
    - github/workflows
    - Dashboard
    - iDatabricks Accreditation
    - Datasets
    - DeltaSharing
    - Evidencias
    - vPrepAmb
    - viProceso
    - Reversion
    - Seguridad
- e.	Creación de Dashboard general por medio de Gini con el fin de tener la información publicada
- f.	Creación de DeltaSharing para gestión de informes externos como PowerBI.
4.	Fin del proceso.


## Tecnologías utilizadas

* Git.
* GitHub.
* GitHub Actions.
* Python.
* YAML.
* Herramientas de automatización.
* Servicios en la nube.

## Estructura del repositorio

* `.github/workflows`: definición de los flujos de integración y despliegue.
* `src`: código fuente del proyecto.
* `tests`: pruebas automatizadas.
* `requirements.txt`: dependencias del proyecto.
* `README.md`: documentación principal.

## Flujo de CI/CD

### Integración continua (CI)

Cada vez que se realiza un cambio en el repositorio:

* Se descarga el código.
* Se instalan las dependencias.
* Se ejecutan las validaciones.
* Se realizan pruebas automáticas.
* Se verifica la calidad del código.

### Despliegue continuo (CD)

Una vez que las pruebas finalizan correctamente:

* Se generan los artefactos.
* Se prepara el entorno.
* Se despliega la nueva versión.
* Se valida el resultado del despliegue.

## Beneficios

* Reducción de errores manuales.
* Mayor velocidad de desarrollo.
* Implementaciones más seguras.
* Mejor control de versiones.
* Mayor trazabilidad.
* Entregas continuas y automatizadas.

## Conclusión

CICDProjectVD001 representa una implementación práctica de los principios de DevOps y CI/CD. El proyecto demuestra cómo automatizar tareas repetitivas, mejorar la calidad del código y optimizar los procesos de desarrollo mediante la integración de herramientas modernas de automatización.

La información se puede evaluar deade un Dashboard completo en el ambiente de Databricks y se crea un delta sharing con el fin de compartir una vista general en PowerBI.
