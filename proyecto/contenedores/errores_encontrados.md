🐳 Documentación de Errores y Soluciones
⚠️ Error 1 — Problema de indentación YAML
yaml.scanner.ScannerError: while scanning a simple key
  in "./docker-compose.yml", line 48, column 1
could not find expected ':'
  in "./docker-compose.yml", line 49, column 1

🔍 Detectado con:

docker-compose up -d

🧠 Causa:

Al copiar y pegar el archivo había un texto en el medio del yml que rompía la sintaxis, este era el texto:

"Crear el archivo en contenedores/docker-compose.yml:

⚠️ NOTA IMPORTANTE: Este archivo contiene errores intencionales..."


✅ Solución:

✂️ Borrar el texto.

🔧 Ajustar la indentación que se había perdido al copiar y pegar.

⚠️ Error 2 — Volumen declarado incorrectamente
ERROR: Named volume "grafana-data:/var/lib/grafana:rw" is used in service "grafana"
but no declaration was found in the volumes section.

🔍 Detectado con:

docker-compose up -d

🧠 Causa:

El servicio usaba el volumen grafana-data, pero en la sección volumes: estaba declarado como grafana-storage.

✅ Solución:

Renombrar el volumen declarado a:

volumes:
  grafana-data:

⚠️ Error 3 — Network inexistente
ERROR: Service "redis" uses an undefined network "monitoring-network"

🔍 Detectado con:

docker-compose up -d

🧠 Causa:

El servicio redis intentaba usar la red monitoring-network, pero la red declarada realmente era:

networks:
  monitoring:

✅ Solución:

Corregir el servicio para que utilice:

networks:
  - monitoring

⚠️ Error 4 — KeyError: 'ContainerConfig'
ERROR: for 76515411f9b7_loki-practica  'ContainerConfig'

🔍 Detectado con:

docker-compose up -d

🧠 Causa:

docker-compose (con guion) es la versión vieja escrita en Python, con plugins obsoletos que no soportan imágenes modernas (Grafana, Loki, etc.).
Esto genera errores como KeyError: 'ContainerConfig'.

✅ Solución:

Usar la versión moderna:

docker compose up -d


(sin guion — forma actual, incluida en Docker Engine y mucho más compatible)

⚠️ Error 5 — Conflicto de nombres de contenedores
Error response from daemon: Conflict. The container name "/76515411f9b7_loki-practica"
is already in use...

🔍 Detectado con:

docker compose up -d

🧠 Causa:

El contenedor correspondiente a Loki ya existía y estaba ocupando el nombre.

✅ Solución:

Eliminar el contenedor conflictivo:

docker rm -f 76515411f9b7_loki-practica


Luego volver a ejecutar:

docker compose up -d
