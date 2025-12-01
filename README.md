# Proyecto Tienda (clienteservidor)

Descripción
-----------
Aplicación servidor/cliente para la tienda (Spring Boot + Thymeleaf). Incluye plantillas, recursos estáticos y soporte básico para H2/MySQL.

Versiones principales
---------------------
- Java: `21` (ver `pom.xml` property `java.version`)
- Spring Boot: `3.5.6` (parent en `pom.xml`)
- Maven: se incluye *Maven Wrapper* (`mvnw` / `mvnw.cmd`)
- Dependencias notables: `H2` (runtime), `MySQL Connector`, `commons-io 2.15.0`, `spring-boot-starter-thymeleaf`.

Requisitos
---------
- JDK 21 instalado y configurado en el sistema (JAVA_HOME apuntando al JDK).
- Git (opcional, para clonar el repo).
- En Windows usar PowerShell; dispone de `mvnw.cmd` para ejecutar Maven sin instalarlo globalmente.

Instalación y ejecución (Windows - PowerShell)
--------------------------------------------
1. Abrir PowerShell en la carpeta `clienteservidorLicoreria`.
2. Construir el proyecto (compila y empaqueta):

```
.\mvnw.cmd clean package
```

3. Ejecutar la aplicación directamente con el wrapper (modo desarrollo):

```
.\mvnw.cmd spring-boot:run
```

4. O ejecutar el JAR generado en `target`:

```
java -jar target\clienteservidor-0.0.1-SNAPSHOT.jar
```

5. Acceder a la aplicación en un navegador en `http://localhost:8080` (puerto por defecto).

Nota: para entornos Unix/macOS usar `./mvnw` en lugar de `mvnw.cmd`.

Configuración (bases de datos y localización)
-------------------------------------------
- El fichero de configuración principal es `src/main/resources/application.properties` (también hay versiones en `target/classes` para el artefacto empaquetado).
- Para pruebas la dependencia H2 está incluida y puede usarse sin configuración adicional; para MySQL debe configurar las propiedades `spring.datasource.url`, `spring.datasource.username`, `spring.datasource.password` en `application.properties`.
- Mensajes de internacionalización están en `src/main/resources/messages*.properties` (`messages.properties`, `messages_en.properties`, `messages_ch.properties`).

Estructura relevante
---------------------
- `src/main/java` : código fuente Java (paquete `com.jorge`).
- `src/main/resources/templates` : plantillas Thymeleaf (`tienda_es.html`, `tienda_en.html`, `tienda_ch.html`, etc.).
- `src/main/resources/static` : archivos estáticos (css, img, js, plantillas_mustache, etc.).
- `pom.xml` : configuración Maven y dependencias.

Pruebas
-------
Ejecutar las pruebas unitarias / de integración:

```
.\mvnw.cmd test
```

Consejos y resoluciones comunes
------------------------------
- Si recibe error de versión de Java, asegúrese de que `java -version` muestre `21` y que su IDE use el JDK 21.
- Para cambiar la base de datos a MySQL actualice `application.properties` con la URL, usuario y contraseña; reinicie la app.
- Para depurar en un IDE (IntelliJ/Eclipse) importe el proyecto como Maven y configure el SDK a Java 21.

Contacto
-------
Para dudas o incidencias revisa el archivo `HELP.md` en esta carpeta o contacta con el autor del repo.

Licencia
--------
Revisar la raíz del repositorio para la información de licencia (si aplica).
