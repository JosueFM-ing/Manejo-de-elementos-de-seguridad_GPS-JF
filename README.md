
# Google Maps Application - README

## Descripción General

Este archivo describe las vulnerabilidades de seguridad identificadas en la aplicación de Google Maps y las mejoras implementadas para mitigar estos problemas. Además, se proporcionan instrucciones sobre cómo ejecutar la aplicación de forma segura.

## Vulnerabilidades Identificadas

Durante el análisis de seguridad realizado con la herramienta Quixxi Vulnerability Test, se encontraron las siguientes vulnerabilidades críticas:

1. **V2 Data Storage and Privacy**:
   - ADB Backup permitido (CWE-530, CWE-312) - Severidad: Media
   - Falta de protección contra capturas de pantalla y compartición de pantalla (CWE-200) - Severidad: Media
   - La aplicación no se difumina en segundo plano (CWE-200) - Severidad: Media

2. **V3 Cryptography**:
   - Implementación débil de Java Hash Code (CWE-327) - Severidad: Advertencia

3. **V6 Platform Interactions**:
   - Exportación incorrecta del Broadcast Receiver (CWE-927, CWE-925) - Severidad: Alta

4. **V7 Code Quality and Build Settings**:
   - Aplicación depurable (CWE-215) - Severidad: Media
   - Información de depuración disponible (CWE-215) - Severidad: Media
   - Falta de verificación de la fuente de descarga (CWE-610) - Severidad: Baja

5. **V8 Resilience Requirements**:
   - La aplicación se ejecuta en dispositivos rooteados (CWE-2018-9582) - Severidad: Media
   - La aplicación se ejecuta en emuladores (CWE-2017-4896) - Severidad: Baja

## Mejoras Implementadas

Se han realizado las siguientes mejoras en la aplicación para mitigar las vulnerabilidades identificadas:

1. **Deshabilitación de ADB Backup**: ADB Backup se ha deshabilitado para evitar accesos no autorizados a datos de respaldo.
2. **Protección de Pantalla**: Se ha implementado protección contra capturas de pantalla y compartición en áreas sensibles de la aplicación.
3. **Difuminado en Segundo Plano**: La aplicación se bloquea o se difumina cuando pasa al segundo plano, protegiendo así la privacidad del usuario.
4. **Mejora de Criptografía**: Se ha reforzado la implementación de hash en Java para evitar vulnerabilidades criptográficas.
5. **Restricciones en Broadcast Receiver**: Los Broadcast Receivers están ahora correctamente configurados para evitar exportaciones indebidas.
6. **Configuración de Debugging**: Se ha deshabilitado el modo depuración en las versiones de producción para prevenir fugas de información.
7. **Verificación de la Fuente de Descarga**: Se han implementado controles de descarga seguros para validar las fuentes de descarga.
8. **Protección contra Ejecución en Dispositivos Rooteados**: Se ha bloqueado la ejecución en dispositivos rooteados o emuladores para mejorar la seguridad.

## Ejecución Segura de la Aplicación

Para ejecutar la aplicación de forma segura, sigue las siguientes recomendaciones:

1. **Instalación en Dispositivos Seguros**: Asegúrate de instalar la aplicación solo en dispositivos que no estén rooteados o en emuladores.
2. **Actualización Regular**: Mantén la aplicación actualizada para garantizar que las últimas mejoras de seguridad estén implementadas.
3. **Evitar Herramientas de Depuración**: No ejecutes la aplicación en un entorno de depuración a menos que sea necesario para desarrollo.
4. **Monitoreo de Permisos**: Revisa y administra los permisos solicitados por la aplicación para asegurar que no se otorguen accesos innecesarios.

---

## Reporte de Vulnerabilidades

El reporte detallado de vulnerabilidades puede ser encontrado en el archivo `vulnerability_report.pdf` adjunto.
