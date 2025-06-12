**Guía Básica y Visual de Opciones sobre Acciones en el Mercado Americano**

---

### 📈 Qué es una Opcion sobre Acciones

Una **opción** es un contrato que te da el **derecho, pero no la obligación**, de comprar o vender 100 acciones de una empresa a un precio fijo (**strike**) antes de una fecha (**vencimiento**).

- **Call (Compra)**: Derecho a comprar acciones
- **Put (Venta)**: Derecho a vender acciones

Cada contrato equivale a **100 acciones**. Si el precio de una acción es \$50, el contrato representa \$5,000 (50 x 100).

---

### 🔢 Tipos de Estrategias

| Tipo           | Dirección del precio | Riesgo                      | Obligación                |
| -------------- | -------------------- | --------------------------- | ------------------------- |
| **Long Call**  | Subida (alcista)     | Limitado a la prima         | No                        |
| **Long Put**   | Bajada (bajista)     | Limitado a la prima         | No                        |
| **Short Call** | Lateral/Bajada       | Riesgo ilimitado            | Sí (vender si se ejerce)  |
| **Short Put**  | Lateral/Subida       | Riesgo alto (si baja mucho) | Sí (comprar si se ejerce) |

---

### 🔹 Niveles de Permisos (Brokers)

| Nivel | Permite                                               |
| ----- | ----------------------------------------------------- |
| 1     | Venta de puts cubiertos (cash-secured)                |
| 2     | Compra de calls y puts (long options)                 |
| 3     | Spreads (verticales, calendar)                        |
| 4     | Estrategias desnudas con margen (short sin cobertura) |

*Si estás en nivel 2, puedes comprar opciones (call/put) pero ****no vender sin cobertura****.*

---

### 🌐 Exchanges y OCC

- Los contratos se negocian en exchanges como: **CBOE, NASDAQ, MIAX, BOX, NYSE**.
- Todos los contratos están garantizados por la **OCC (Options Clearing Corporation)**:
  - Garantiza que el comprador/ejerciente reciba lo pactado.
  - Protege contra impagos.

---

### 🔄 Flujo de una Orden

```
[Usuario] ➔ [Broker] ➔ [Exchange] ➔ [Market Maker] ➔ [OCC]
```

*La OCC garantiza que la operación se liquide correctamente.*

---

### 🏛️ Griegas - Tu Panel de Control de Riesgo

| Griega    | Qué mide                                                | Impacto                |
| --------- | ------------------------------------------------------- | ---------------------- |
| **Delta** | Cambio del precio de la opción por \$1 en el subyacente | Direccionalidad        |
| **Theta** | Pérdida diaria por paso del tiempo                      | Valor temporal         |
| **Vega**  | Cambio por 1% de volatilidad implícita                  | Apuesta a eventos/IV   |
| **Gamma** | Cambio de Delta si el precio sube \$1                   | Aceleración del riesgo |

**Ejemplo:**

- Call con delta 0.60 = ganas \$60 si la acción sube \$1.
- Theta -0.05 = pierdes \$5 por día.
- Vega 0.10 = ganas \$10 si sube la IV un 1%.

---

### 📊 Herramientas y Simuladores

Puedes usar herramientas como:

- **Thinkorswim** (TD Ameritrade)
- **OptionsStrat**
- **Tastyworks**
- **TradingView con cadenas de opciones**

Allí puedes ver:

- Cadena de opciones (option chain)
- Griegas en tiempo real
- Simulación de P/L según el precio y el tiempo

---

### 🚀 Automatización con Python

Con Python puedes:

- Calcular griegas automáticamente (Black-Scholes)
- Obtener datos reales (yfinance, alpaca, TDA-API)
- Simular escenarios con matplotlib
- Backtestear estrategias propias

```python
import mibian
c = mibian.BS([100, 95, 1, 5], volatility=25)
print(c.callDelta, c.callTheta)
```

---

### 🔗 Consejos para Principiantes

- Empieza con acciones debajo de \$30 para menos riesgo
- Prioriza baja volatilidad para estudiar más que especular
- No mantengas opciones hasta expiración: vende antes
- Si compras, el tiempo va en tu contra (Theta)
- Si vendes, cuida el riesgo de movimientos fuertes (Gamma/Vega)

---

### ✅ Conclusión

Entender opciones requiere práctica y disciplina, pero te da herramientas poderosas para especular o cubrir tu portafolio. Usa las griegas como tu GPS y la OCC como tu seguro.

Siguiente paso: elige un activo (como SPY), analiza su option chain, y simula una estrategia con Python o OptionsStrat.

---

© Guía producida con apoyo de herramientas reales y simuladores de mercado.

