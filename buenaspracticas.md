
# Best Practices Implemented

Este documento detalla las buenas prácticas de seguridad implementadas en la aplicación para protegerla contra vulnerabilidades comunes y garantizar la seguridad de los datos de los usuarios.

## 1. Cifrado
- **Descripción**: Se ha implementado cifrado AES (Advanced Encryption Standard) para proteger datos sensibles almacenados localmente en la aplicación. Además, todas las comunicaciones de red utilizan TLS (Transport Layer Security) para asegurar que los datos en tránsito estén cifrados y protegidos de ataques de interceptación.
- **Mejora de Seguridad**: El cifrado asegura que, incluso si los datos sensibles (como contraseñas o información personal) son accedidos por un tercero, no podrán ser leídos sin la clave de cifrado. TLS protege las comunicaciones de red, evitando que atacantes puedan espiar o modificar los datos mientras están en tránsito entre el cliente y el servidor.

## 2. Uso de HTTPS
- **Descripción**: Todas las comunicaciones de la aplicación con el servidor utilizan HTTPS (HTTP Secure), que garantiza que los datos transmitidos entre el cliente y el servidor estén cifrados.
- **Mejora de Seguridad**: HTTPS evita ataques de tipo man-in-the-middle (MITM), en los que un atacante intercepta la comunicación entre el cliente y el servidor para robar o manipular datos. Al usar HTTPS, garantizamos que los datos son autenticados y cifrados correctamente.

## 3. Validación y Sanitización de Entradas
- **Descripción**: Todas las entradas proporcionadas por los usuarios son validadas y sanitizadas antes de ser procesadas. Esto incluye validaciones de formato, tipo de datos y longitud, así como sanitización para prevenir la inyección de código malicioso.
- **Mejora de Seguridad**: La validación de entradas evita ataques como inyección de SQL (SQL Injection) y Cross-Site Scripting (XSS), que podrían comprometer los datos del sistema. Al asegurarnos de que solo se procesen entradas válidas y seguras, reducimos el riesgo de que los atacantes utilicen vectores de ataque a través de datos de entrada no controlados.

## 4. Restricciones de Permisos
- **Descripción**: Se han implementado restricciones para que la aplicación no tenga acceso a permisos innecesarios, limitando su exposición a riesgos relacionados con permisos excesivos. Solo se solicitan los permisos mínimos necesarios para el funcionamiento correcto de la aplicación.
- **Mejora de Seguridad**: Minimizar los permisos reduce la superficie de ataque y las posibilidades de que una vulnerabilidad sea explotada a través de funciones del dispositivo que la aplicación no necesita. Esto es una práctica clave para mitigar riesgos innecesarios.

## 5. Deshabilitar ADB Backup
- **Descripción**: La funcionalidad de respaldo a través de ADB (Android Debug Bridge) ha sido deshabilitada para evitar que los datos de la aplicación sean respaldados de forma no segura.
- **Mejora de Seguridad**: Evitar el respaldo de datos a través de ADB previene que un atacante con acceso físico al dispositivo pueda obtener copias de seguridad de la aplicación, lo que podría resultar en una exposición de datos sensibles.

## 6. Protección Contra Capturas de Pantalla
- **Descripción**: Se ha implementado una medida de seguridad para deshabilitar las capturas de pantalla en las vistas sensibles de la aplicación.
- **Mejora de Seguridad**: Esta protección impide que se capturen y compartan de manera accidental o maliciosa imágenes que contengan datos sensibles, como información personal o financiera del usuario.

---

### Conclusión
Estas buenas prácticas aseguran que la aplicación no solo cumpla con los estándares de seguridad actuales, sino que también proteja a los usuarios y sus datos frente a diversas amenazas y ataques comunes. Se recomienda continuar con auditorías de seguridad periódicas para mantener y mejorar la seguridad de la aplicación a medida que evoluciona.
