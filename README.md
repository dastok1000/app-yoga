# Yoga Reservas

Prototipo local de reservas para un estudio de yoga, al estilo Momoyoga. Se ejecuta solo en tu PC (`http://127.0.0.1:8795`), sin internet y sin instalar nada.

**Versión actual:** 0.1.1-pub

## Descarga

- Archivo: [yoga-reservas-0.1.1-pub-windows.zip](https://github.com/dastok1000/app-yoga/releases/download/v0.1.1-pub/yoga-reservas-0.1.1-pub-windows.zip)
- Tamaño: 35.014.737 bytes (33,4 MiB)
- SHA-256: `d4bdc404013269ddbc4a79e85fb31f5a87e06a49261fe44fc7642c4199e9a841`
- Release: [v0.1.1-pub](https://github.com/dastok1000/app-yoga/releases/tag/v0.1.1-pub)

### Comprobar el hash

En el Símbolo del sistema (cmd):

```
certutil -hashfile yoga-reservas-0.1.1-pub-windows.zip SHA256
```

En PowerShell:

```
Get-FileHash yoga-reservas-0.1.1-pub-windows.zip -Algorithm SHA256
```

El resultado debe coincidir con el SHA-256 de arriba.

## Avisos importantes

- **Es un prototipo.** Los pagos están simulados: no se cobra nada ni se conecta a ninguna pasarela real. Los avisos se guardan en la app y en `data\avisos.log`; no se envían correos ni SMS.
- **Windows puede mostrar SmartScreen** al abrir un `.bat` descargado de internet. Si has comprobado el hash y confías en la descarga, elige «Más información» y «Ejecutar de todas formas».
- El ZIP incluye el runtime oficial de **Node.js v24.22.1** para Windows (x64). La licencia de Node (MIT y licencias de terceros) está en `yoga-reservas/runtime/LICENSE`.

## Instalación

1. Descomprime el ZIP entero en una carpeta.
2. Haz doble clic en **Abrir.bat**. Se abre una consola (el servidor) y el navegador en `http://127.0.0.1:8795/`. Escucha solo en este PC. El puerto se puede cambiar con `YOGA_PORT`.
3. En el **primer arranque no hay usuarios**. La app te pide que crees la cuenta de administración (email y contraseña, que solo tú conoces). El horario empieza vacío: después podrás dar de alta profesores y clases. Las salas Sala Sol y Sala Luna ya vienen creadas.
4. Deja la ventana abierta mientras uses la app; ciérrala (o Ctrl+C) para parar.

## Actualizar sin perder datos (U1–U3)

1. **U1.** Cierra la app y espera a que desaparezca la ventana.
2. **U2.** Copia la carpeta `data\` entera (incluidos `yoga.db`, `yoga.db-wal`, `yoga.db-shm` y `avisos.log` si existen) a la carpeta de la versión nueva. No abras la versión nueva en otra carpeta antes de tener los datos copiados: se crearía una base vacía.
3. **U3.** Entonces ejecuta `Abrir.bat` de la carpeta nueva.

No uses `Restablecer-datos.bat` al actualizar: borra todos los datos. Ese archivo no crea usuarios de ejemplo; el siguiente arranque vuelve a pedir el alta del administrador.

## Qué hay en este repositorio

Este repositorio acompaña la release pública. El programa listo para usar está en el ZIP de la release (incluye el runtime de Node para Windows). Las notas de la versión están en la [release v0.1.1-pub](https://github.com/dastok1000/app-yoga/releases/tag/v0.1.1-pub).

## Aviso de uso

Puedes descargar este prototipo y ejecutarlo en tu propio PC. Se ofrece tal cual, sin garantía de ningún tipo. El paquete está marcado como `UNLICENSED`: todos los derechos reservados; no se concede ninguna otra licencia. No lo uses para cobrar a alumnos reales mientras los pagos sigan simulados.

Node.js se distribuye con su propia licencia (MIT y licencias de terceros). Consulta `yoga-reservas/runtime/LICENSE` dentro del ZIP.
