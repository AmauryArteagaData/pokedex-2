# Despliegue de la Pokedex en Azure
Proyecto: Pokedex Angular
Plataforma: Microsoft Azure
Repositorio: https://github.com/AmauryArteagaData/pokedex-2/tree/main

### 1. Requisitos previos
- Node.js >= 14
- Angular CLI (npm install -g @angular/cli)
- Cuenta de Microsoft Azure Student

### 2. Clonación del repositorio
Use los comandos 
git clone https://github.com/AmauryArteagaData/pokedex-2.git
npm install
ng serve (para correr el programa)

### 3. Configuración de Seguridad
Se crea el archivo **staticwebapp.config.json** para agregar los headers de seguridad.
Se agreagaron los siguientes headers:
- Strict Transport Security
- Referrer Policy
- X-Content-Type-Options
- Content-Security-Policy
- X-Frame-Options
- Permissions-Policy

### 4. Creación de Static Web App
1. Dar click en el apartado Static Web App
2. Dar click en crear
3. Dar click en crear **new resource group** para crear un nuevo grupo de recursos
4. Luego coloque el nombre de la App usando la convención establecida por Azure
5. Luego en **Plan Type** click en **free** para que sea gratuito el despliegue
6. Asegurese de tener su cuenta de Github para enlazar con Azure
7. En Organización elige su cuenta de Github
8. Le aparecerán los repositorios que tiene, elija el repositorio
9. Seleccione la rama, en este caso **main**
10. Luego en App Location agregue la ruta del proyecto
11. En Api Location dejelo en blanco
12. Luego en Output coloque la ruta de los archivos compilados listos para servir al navegador
13. Click en **review + create**
14. Luego le da en **Go to resource** allí le mostrará los detalles del recurso ya creado
15. Espere unos 2 minutos hasta que en Github Actions establezca la conexión para desplegar la app

# Reflexión Técnica
**¿Qué vulnerabilidades previenen los encabezados implementados?**
Los encabezados de seguridad añaden una capa adicional de protección sin modificar el código de la aplicación, estas son las vulnerabilidades que previenen el uso correcto de los encabezados.

- Cross-Site Scripting (XSS): El encabezado Content-Security-Policy (CSP) indica al navegador qué recursos puede cargar, bloqueando scripts maliciosos.
- ⁠Fuga de información de referencia: Referrer-Policy controla qué información se envía al navegar entre sitios.
- ⁠Comunicaciones inseguras: Strict-Transport-Security (HSTS) fuerza el uso de HTTPS, evitando ataques de tipo downgrade.

**¿Qué aprendiste sobre la y relación entre despliegue y seguridad?**
En el contexto actual de la tecnología, el software, apps, la protección, la seguridad se ha vuelto muy importante. Puedes tener el mejor código del mundo, pero si no tienes buenas prácticas de seguridad expones servicios muy importantes, el despliegue no es el final del desarrollo, es la fase más crítica ya que se define y expone el modelo de seguridad real del sistema. Por otro lado en la seguridad web se define el como se va a proteger las vulnerabilidades del sistema encontrados en el despliegue.

**¿Qué desafios encontraste en el proceso?**
Problemas con los headers, ya que son esenciales para la seguridad, mi desafio fue que al configurarlos me dañaban el despliegue de la app con un error 500 (fallo del lado del servidor)

Error en las imagenes, las imagenes no se muestran al inicio