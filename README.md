# AWTRIX NG – Consumo eléctrico / Electricity consumption

Autor: **ML**  
Blueprint de Home Assistant para Ulanzi TC002 con AWTRIX NG, comunicado mediante MQTT.

## Archivos / Files

- `awtrix_ng_consumo_electrico_es.yaml` — Español
- `awtrix_ng_stromverbrauch_de.yaml` — Deutsch
- `awtrix_ng_electricity_consumption_en.yaml` — English
- `awtrix_ng_consommation_electrique_fr.yaml` — Français
- `awtrix_ng_consumo_eletrico_pt.yaml` — Português

Cada archivo conserva la misma funcionalidad; se traducen los nombres, descripciones y opciones de la interfaz del blueprint. El texto hablado de la alarma se mantiene en inglés porque es la voz que hemos probado en AWTRIX NG.

## Funciones principales

- Potencia y porcentaje con desplazamiento horizontal cuando no caben.
- Icono animado instalado localmente en el TC002: `lightningbolt`.
- Barra de progreso con borde gris; altura interior configurable de 1 a 6 px.
- Tres zonas de color, umbrales configurables y porcentaje visible por encima del 100 %.
- Parpadeo opcional y alarma seleccionable: sirena RTTTL o voz inglesa.
- Modo de prueba y publicación MQTT al arrancar, al cambiar los sensores y cada cinco segundos.

## Requisitos e instalación

1. Home Assistant con MQTT configurado.
2. AWTRIX NG y Ulanzi TC002 con pantalla de 52 × 16 píxeles.
3. Un sensor de potencia en vatios y un sensor de porcentaje de consumo.
4. Instala el icono `lightningbolt` en el TC002 desde AWTRIX Hub. El icono no está incluido en este repositorio: cada usuario debe descargarlo a su propio reloj y comprobar que el identificador sea exactamente `lightningbolt`.
5. En Home Assistant, abre **Settings → Automations & scenes → Blueprints → Import Blueprint** y pega la URL *raw* del archivo YAML correspondiente al idioma que quieras usar.
6. Crea una automatización desde el blueprint y selecciona el dispositivo AWTRIX y los sensores.
7. Prueba primero el modo de prueba y comprueba la alarma antes de activar el uso normal.

Documentación oficial:
- [Home Assistant — Using automation blueprints](https://www.home-assistant.io/docs/automation/using_blueprints/)
- [AWTRIX NG — documentación](https://blueforcer.github.io/awtrix-ng/)
- [AWTRIX NG — iconos para TC002](https://blueforcer.github.io/awtrix-ng/tc002/guides/icons/)

## Estado

Versión 10, funcional en el TC002 del autor. Se recomienda probar la configuración y la compatibilidad con el modelo/versión de firmware propios antes de usarla en producción.
