# BPN Atlas: lanzamiento

## Alcance de esta adaptación

Identidad BPN sobre la aplicación completa: cubo original, tipografías, paleta, encabezado, bienvenida, carga y paneles. La navegación global, fuentes, escenas, mapas y herramientas del proyecto base siguen disponibles. La bienvenida está en español; esta versión no es una traducción completa de los controles técnicos.

El origen se acredita en la interfaz y en el README. LICENSE, THIRD_PARTY_NOTICES.md, DATA_SOURCES.md y los avisos de los datasets conservan sus autores y términos.

## Ejecución local

```sh
npm ci
npm run doctor
npm run dev
```

Abre http://localhost:4173. No necesitas claves para comenzar. Para ver la bienvenida de nuevo, abre http://localhost:4173/?welcome=1 sin un fragmento de vista compartida.

## Verificación

```sh
npm run format:check
npm run check:boundaries
npm test
npm run build
```

La build genera dist. El directorio incluye el cliente y sus assets; no reemplaza al servidor de proveedores. La disponibilidad real de fuentes debe comprobarse por separado, con las claves que se decida habilitar.

## Despliegue completo

La aplicación usa rutas /api y /mcp servidas por módulos Node. Un hosting exclusivamente estático no conserva todas sus capacidades: varias fuentes, cachés y voz requieren el backend. El destino debe elegirse antes de implementar su adaptador de producción. No publicar un servidor de desarrollo como servicio definitivo.

Para el destino elegido, mantener los límites y la protección de rutas originales, deshabilitar la configuración local de claves para visitantes remotos y configurar las credenciales sólo como secretos del servidor. Los tokens de mapas que lleguen al navegador deben restringirse al dominio definitivo. Leer SECURITY.md para el modelo de compartición original.

Verificar las licencias de las capas incluidas para el uso público y promocional previsto. La concesión MIT del código no cubre los datasets ni los modelos. DATA_SOURCES.md identifica, entre otros, datos con restricciones no comerciales.

## Estado de publicación

Esta guía no declara un despliegue público. El enlace de GitHub distribuye el código; el enlace local permite revisar la aplicación en esta computadora. Un lanzamiento web requiere un destino de hosting, su implementación y verificación del servicio publicado.
