# 📊Desfase entre Tendencia y Momentum

Latencia entre RSI y SMA 50

Este proyecto implementa una consulta SQL que mide el desfase temporal (lag) entre dos tipos de señales técnicas clave:
- Debilidad de momentum (RSI 14 < 50)
- Debilidad de tendencia (Precio < SMA 50)

El objetivo es cuantificar cuántos días pasan entre ambas señales y entender cuál actúa como indicador líder.

## 🧠Idea central

En análisis técnico avanzado, no todas las señales aparecen al mismo tiempo.

Una pregunta fundamental es:
- ¿El momentum se deteriora antes que la tendencia, o al revés?

Este proyecto responde eso con datos, midiendo la latencia real entre:
- el primer signo de debilidad interna (RSI)
- la confirmación estructural de tendencia (ruptura de SMA 50)

## 📊Valor de negocio

Permite identificar indicadores líderes vs rezagados

Útil para:
- mejorar timing de salidas
- reducir drawdowns
- diseñar sistemas multi-señal más eficientes
- Convierte conceptos cualitativos en métricas cuantificables

## 🗄️Estructura de datos esperada

- indicadores_tecnicos
- campo	descripción
- ticker_id	Identificador del activo
- fecha	Fecha
- rsi_14	RSI de 14 períodos
- sma_50	Media móvil simple de 50 períodos
- precios_diarios
- campo	descripción
- ticker_id	Identificador
- fecha	Fecha
- close	Precio de cierre

## ⚙️Lógica de la consulta

Genera dos señales binarias:
- RSI < 50 → debilidad de momentum
- Close < SMA 50 → debilidad de tendencia
- Detecta el día exacto de activación de cada señal (cruce 0 → 1)
- Empareja ambos eventos por ticker

Calcula la latencia en días entre:
- cruce de RSI
- cruce posterior de SMA 50

## 🔎Interpretación de resultados

- Latencia positiva alta: el RSI avisa mucho antes → buen indicador líder
- Latencia corta: mercado eficiente o movimientos violentos
- Latencia negativa (si se analiza): ruptura de tendencia sin aviso previo
- Esto permite clasificar activos por comportamiento técnico estructural.

## 🚀Posibles extensiones

- Analizar latencias promedio por activo
- Comparar por régimen de volatilidad
- Usar otros umbrales (RSI 45 / SMA 100)
- Visualizar distribuciones de latencia

## 📝Notas finales

- No es una señal de trading directa
- Es una herramienta de diagnóstico de mercado
- Ideal para mejorar sistemas existentes

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.
***
📊 El mercado no cambia de golpe… cambia en etapas.

Y entender el *timing* entre esas etapas puede darte ventaja.

---

Hay un desfase muy interesante entre dos señales clave:

👉 Momentum (RSI)
👉 Tendencia (SMA 50)

---

🔍 Lo que analicé:

* 📉 Cuándo el RSI cae por debajo de 50 → primera señal de debilidad
* 📉 Cuándo el precio cae por debajo de la SMA 50 → confirmación de tendencia

Y medí algo clave:

👉 ¿Cuántos días pasan entre una señal y la otra?

---

💡 ¿Por qué importa?

Porque estas señales no ocurren al mismo tiempo.

En muchos casos:

* El **momentum se debilita primero**
* La **tendencia tarda en confirmarlo**

---

🧠 Insight clave:

El RSI no solo mide fuerza…

👉 puede actuar como *early warning signal*

---

📈 ¿Qué significa en la práctica?

* Si el RSI cae primero → tenés tiempo de anticiparte
* Si la SMA cae después → el mercado ya confirmó la debilidad

---

🚀 Aplicaciones:

* Mejor timing de salida
* Señales anticipadas de reversión
* Evitar entrar tarde a tendencias débiles
* Features temporales para modelos cuantitativos

---

🧠 Takeaway:

No todas las señales valen lo mismo en el tiempo.

👉 Algunas te avisan…
👉 otras confirman

Y la diferencia entre ambas es donde está la ventaja.

---

Estoy explorando insights combinando SQL + análisis cuantitativo para entender mejor estos patrones temporales.

Si te interesa este enfoque, conversemos 👇

#DataScience #Quant #Finance #Trading #MachineLearning #SQL #Investing
