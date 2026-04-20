<img width="1132" height="468" alt="Screenshot 2026-04-20 at 16 42 57" src="https://github.com/user-attachments/assets/5ae2bea9-1b91-4862-8183-e1a53517d7d1" />
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
<img width="1415" height="523" alt="Screenshot 2026-04-20 at 16 27 00" src="https://github.com/user-attachments/assets/5957de1f-1dae-4a73-a3cd-14009ba84f38" />
   
2. Dar click en crear
<img width="898" height="308" alt="Screenshot 2026-04-20 at 16 43 40" src="https://github.com/user-attachments/assets/e6869288-bf29-43c6-a03d-c4861cc6bc11" />
 
3. Dar click en crear **new resource group** para crear un nuevo grupo de recursos
<img width="708" height="182" alt="Screenshot 2026-04-20 at 16 46 54" src="https://github.com/user-attachments/assets/19b0440d-48d8-42cd-8478-d513d78e3489" />

4. Luego coloque el nombre de la App usando la convención establecida por Azure
<img width="707" height="89" alt="Screenshot 2026-04-20 at 16 47 28" src="https://github.com/user-attachments/assets/22813390-8f93-4e4d-b2ef-811b7d76fa45" />


5. Luego en **Plan Type** click en **free** para que sea gratuito el despliegue
<img width="667" height="134" alt="Screenshot 2026-04-20 at 16 47 53" src="https://github.com/user-attachments/assets/f3cef627-3525-401c-8b41-25f68c58e0f6" />

6. Asegurese de tener su cuenta de Github para enlazar con Azure
<img width="528" height="142" alt="Screenshot 2026-04-20 at 16 48 27" src="https://github.com/user-attachments/assets/4b92611a-9d1f-402b-ac73-0dca5a71f987" />

7. En Organización elige su cuenta de Github
<img width="700" height="124" alt="Screenshot 2026-04-20 at 16 49 01" src="https://github.com/user-attachments/assets/1977f952-e6af-4ead-a1e5-5b13e77a9771" />

11. Le aparecerán los repositorios que tiene, elija el repositorio
<img width="700" height="124" alt="Screenshot 2026-04-20 at 16 49 01" src="https://github.com/user-attachments/assets/1977f952-e6af-4ead-a1e5-5b13e77a9771" />

12. Seleccione la rama, en este caso **main 0 master**
13. Luego en App Location agregue la ruta del proyecto
14. En Api Location dejelo en blanco
15. Luego en Output coloque la ruta de los archivos compilados listos para servir al navegador
<img width="706" height="288" alt="Screenshot 2026-04-20 at 16 53 16" src="https://github.com/user-attachments/assets/8127773e-011e-4829-b9d8-517abfe96e9b" />

16. Click en **review + create**
<img width="529" height="53" alt="Screenshot 2026-04-20 at 16 53 40" src="https://github.com/user-attachments/assets/5fd42ba9-040b-487b-9359-3239071646c3" />

18. Luego le da en **Go to resource** allí le mostrará los detalles del recurso ya creado
28. Espere unos 2 minutos hasta que en Github Actions establezca la conexión para desplegar la app

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

Error en la aparición de los sprites, se solucionó insertando en las cabeceras de seguridad la cabecera que me permitía mostrar los sprites.

### Capturas
**Configuación final del recurso**
<img width="1664" height="644" alt="Screenshot 2026-04-20 at 16 18 20" src="https://github.com/user-attachments/assets/364d89b2-f75c-4e6e-aea6-f23f3f46614b" />

**App Desplegada**
<img width="1241" height="952" alt="Screenshot 2026-04-20 at 16 19 49" src="https://github.com/user-attachments/assets/d20300f5-2eb1-4eb0-a744-6de1da329772" />

<img width="1647" height="961" alt="Screenshot 2026-04-20 at 16 20 26" src="https://github.com/user-attachments/assets/621b24a4-ebe0-4b5b-b2b5-e560c08326d5" />

**Scaneado de la URL**
<img width="1196" height="943" alt="Screenshot 2026-04-20 at 16 21 03" src="https://github.com/user-attachments/assets/10e4fa03-5d96-4fd5-8725-8d5aaf2655b7" />

**Historial de Actions**<img width="1479" height="824" alt="Screenshot 2026-04-20 at 16 26 12" src="https://github.com/user-attachments/assets/a0f5937b-a3ef-4730-aa4a-e4cd3936dd84" />

**Historial de Commits**
<img width="1275" height="905" alt="Screenshot 2026-04-20 at 16 24 01" src="https://github.com/user-attachments/assets/25c6b38d-2263-4e5c-a7b5-e6f733f721fa" />



