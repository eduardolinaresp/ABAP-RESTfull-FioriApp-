# ABAPRestFullFioriApp
ABAP-RESTfull-FioriApp 

# 1 En SCP subscribirse al servicio SAP Business Application Studio 
    
    Selecionar el espacio y desde el menú de la izquierda seleccionar SUBSCRIPTION bsucar el SAP Business Application Studio y activar

# 2 En SCP agregar Trust Configuration
 
## 2.1 Selecionar desde el menú de la izquierda seleccionar Security/Trust Configuration
## 2.2 Selecionar Default identity provider
## 2.3 Ingresar el email de nuestra cuenta y presionar el botón Show Assignments.
## 2.4 Presionar el botón Assign Role Collection y agregar el rol Business_Application_Studio_Developer.
## 2.5 Abrir Business Application Studio.
## 2.6 Crear un nuevo espacio e indicar el tipo de aplicacion FIORI a crear. una vez creado, click sobre el espacio.
## 2.7 una vez abierto el SAP Business Application Studio, Open Workspace, selecionar proyectsy abrir.
## 2.8 organizar el space en Cloud Foundry.
### 2.8.1 desde la izquierda abajo, clickear mensaje The organization and space in Cloud Foundry have not been set.
### 2.8.2 se abre una barra de navegacion arriba al centro del editor. Selecionar el endpoint por defaulr de Cloud Foundry y presionar enter.
### 2.8.3 Inresar email y password para autenticarnos y presionar enter.
### 2.8.4 Selecionar nuestra global account que aparece por default.
### 2.8.5 Selecionar nuestra espacio que aparece por default.
## 2.9 Crear list report object page
### 2.9.1 Desde los menus del editor Select View > Find Command.Buscar y escoger Yeoman UI Generators.
### 2.9.2 Desde la pagina proporcionada selecionar SAP Fiori elements application and click Start.
### 2.9.3 Select List Report Object Page and click Next.
### 2.9.4 Configurar data source, system and service: 
#### 2.9.4.1 Data source: Connect to an SAP System
#### 2.9.4.2 System: ABAP Environment on SAP Cloud Platform
#### 2.9.4.3 ABAP Environment: default_abap-trial
#### 2.9.4.4 Service: ZUI_C_TRAVEL_M_ELP(1) - odata v2
### 2.9.5 Una vez completado el punto anterior dar NEXT y selecionar la entidad principal TravelProcessor y luego NEXT.
### 2.9.6 Configure project attributes:
#### 2.9.6.1 Name: ztravel_app_elp
#### 2.9.6.2 Title: Travel App ELP
#### 2.9.6.3 Description: A Fiori ELP application.
### 2.9.7 Una vez completado el punto anterior dar FINISH.
### 2.9.8 El sistema comenzará a compilar las dependencias, al terminar nos preguntará
         the project has been generated. What would you like to do with it?
### 2.9.9 El sistema nos pregunta si queremos abrir la APP, pero cancelamos el wizard.
### 2.9.10 En la barra izquierda del SAP Business Application Studio, presionamos el ultimo icono "Run configuration" que tiene forma de "Play"
### 2.9.11 El editor cambia la perspectiva, escogemos el script  Start ztravel_app_elp y le damos "Play".
    Nota: También se puede abrir un terminal y ejecutar por la via npm start.
### 2.9.12 El sistema abre el terminal y muestra el proceso de compilacion, al terminar le damos expose and opend cuando aparezca la siguiente pregunta: 
     service is listening to port 8080. Click "Expose and Open" to access the service externally, and preview it in a new tab.
### 2.9.13 El sistema abre una nueva pagina en el navegador, selecionamos la carpeta test/y selecionamos flpSandbox.html.
### 2.9.14 El sistema abre el sandbox launpad donde aparece nuestra APP.

### 2.10 Deploy your application
#### 2.10.1 Selecionar el primer icono del SAP Business Application Studio 
     Nos muestra nuesto directorios del espacio. selecionamos nuestra APP, le damos boton derecho y seleccionamos la opción Open in Terminal 
#### 2.10.2 para agregar contenido al Fiori Launchpad 
     ingresamos este comando en el terminal npx fiori add flp-config.
#### 2.10.3 la shell nos solicita los siguientes parametros.
     Semantic Object: ztravel_app_elp
     Action: display
     Title: Travel App ELP
     Subtitle (optional): press enter
#### 2.10.4 Ir a eclipse buscar nuestro package y abrir el transport organizer.
     Selecionamos y copiamos la orden de transporte modificable del proyecto backend. en este caso es TRLK900903
#### 2.10.5 Volver a SCP y desde el terminal agregar el siguiente comando:
     npx fiori add deploy-config
##### 2.10.5.1 la shell nos solicita los siguientes parametros.
      Please choose the target: ABAP
      Is this an SAP Cloud Platform system?: Y
      Destination: press enter for default
      Name: press enter for default
      Package: ztravel_app_el1
      Transport Request: TRLK900903
      Generate standalone index.html during deployment: y

##### 2.10.5.2 En la shell ingresar el comando 
      npm run deploy

#### 2.10.6 Volver a Eclipse y realizar lo siguiente:
##### 2.10.6.1 Verificar que se haya creado las siguientes librerias:
       BSP library y SAP Fiori Launchpad app descriptor item folder.
##### 2.10.6.2 Create IAM App and business catalog.
##### 2.10.6.2.1 Right-click your package and select New > Other Repository Object.
##### 2.10.6.2.2 Search for IAM App, select it and click Next >.
##### 2.10.6.2.3 Create a new IAM App:
        Name: ZTRAVEL_IAM_ELP
        Description: IAM App
##### 2.10.6.2.4 En el dialogo new IAM click finish, luego Select Services and add a new one.

##### 2.10.6.2.5 En el dialogo Find Services, selecionar: 
    Service Type: OData V2
    Service Name: ZUI_C_TRAVEL_M_ELP_0001

    NOTA: GRabar y activar IAM App









# 4 Tutoriales generales FIORI RAP on cloud 

    seguir el Tutorial 7 of 7 de la siguiente documentación

    https://developers.sap.com/tutorials/abap-environment-deploy-cf-production.html






