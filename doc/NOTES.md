


Tomando como referencia (API) las operaciones ofrecidas por Terraform:

- init, inicializar entorno.
- plan, generar plan de ejecución (dry-run)
- validate, valida la defición proporcionada.
- apply, aplica el plan definido (descriptive).
- destroy
- show (current state or saved desired state)
- refresh (current state)

Operador para GitOps

- Deployment
    - Observe
    - Deploy
- Environment Repository
    - Observe
    - Write

Con los requisitos descritos por GitOps:
- Declarative
- Versioned and Immutable
- Pulled Automatically
- Continuously Reconciled


Tres tipos de repositorio
- Infra Definition
- App
    - App Code
    - App Infra Definition

Workload -> Product
Environment -> Infrastructure
Deployment - > Environment + Workload
Workspace -> Workload + Environments


Se describen varios "dominios":

- Estructura general (Resource)
- Producto (Workload), representa una agrupación de funcionalidades soportadas por software desplegadas en una estructura física.
    - Workload
        - Service (App)
        - MicroService
    - (*)Instance
    - Hosted in ...
    - Implemented by ...
- Software (software), representa el software que implementa las funcionalidades ofrecidas por un sevicio.
    - SofwareItem
    - SoftwareItemDescriptor (Spec)

- Entorno (Environment), representa la infraestura de sistemas requerida para desplegar el software que implementa los servicios.
    - EnvironmentItem
        - System (elemento donde se despliega el software)
            - Type: Physical, Virtual, Container, Other(k8s)
            - Rol: Server, Device
            - Config (Host Image, connectivity, etc.)
        - Virtual
            - references physical
            - Requirements
        - Physical
            - requirements
        - Container
            - references other containers

- Hardware (hardware), describe los dispositivos que forman parte de la infraestructura requerida para desplegar el software.
    - HardwareItem
        - Network
        - Runtime: Bare, Containers, Virtual Machines
        - Hardware
            - Type: Server, Device, Node
            - Architecture
            - OS
            - Disk
            - Memory
            - Disk

Servicios externos? Servicios requeridos cuando no dependen de la implementación. Modelados como servicios dentro de la estructura.
Un producto puede ser un servicio?