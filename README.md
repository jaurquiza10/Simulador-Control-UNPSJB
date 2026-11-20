# Simulador de Control Clásico y Discreto

Simulador interactivo de Sistemas de Control en dominio continuo (**Plano $s$**) y discreto (**Plano $z$**), diseñado para el análisis gráfico y diseño de lazos de control en tiempo real.

## 🌐 Versión Web (Online)

Podés usar el simulador directamente desde el navegador sin instalar nada en:

👉 **[https://simulador-control-jaur-unpsjb.netlify.app](https://simulador-control-jaur-unpsjb.netlify.app)**

---

## 💻 Descarga para Windows (`.exe` Portable)

Si preferís ejecutarlo de forma local y offline en Windows:

1. Ingresá a la pestaña **Releases** de este repositorio en GitHub.
2. Descargá el archivo ejecutable portable `.exe` de la última versión publicada.
3. Ejecutalo directamente (no requiere instalación).

---

## ✨ Funcionalidades Principales

- **Modo Continuo (Plano $s$) y Discreto (Plano $z$)**:
  - Discretización de la planta continua $G(s)$ a $G(z)$ mediante **ZOH (Retenedor de Orden Cero)** o **Tustin (Bilineal)**, con período de muestreo $T_s$ configurable.
- **Definición de Planta y Compensadores**:
  - Ingreso de $G(s)$ como polinomio o forma factorizada en $s$ (por ejemplo `s*(s+1)*(s+2)`) o mediante coeficientes.
  - Agregado de múltiples compensadores $H_n(s)$ en el lazo abierto (**Adelanto**, **Atraso**, **PI**, **PD**, **PID** y **Personalizado**), con activación/desactivación instantánea.
  - Visualización de la función de transferencia a lazo abierto $L(s) = K \cdot G(s) \cdot \prod H_n(s)$ y del polinomio característico $1 + L(s) = 0$.
- **Control de Ganancia $K$ en Tiempo Real**:
  - Ajuste manual y por deslizador (lineal o no lineal), ajuste automático de rango, barrido animado de $K$ e indicadores de estabilidad en lazo cerrado, margen de ganancia (MG) y margen de fase (MF).
- **Herramientas de Análisis**:
  1. **Lugar de las Raíces**: evolución de los polos en lazo cerrado en el plano $s$ o $z$.
  2. **Diagrama de Bode**: respuesta en frecuencia (magnitud y fase) con márgenes de estabilidad.
  3. **Análisis por Nyquist**: diagrama polar y criterio de estabilidad.
  4. **Respuesta Temporal (`y(t)`)**: simulación de la respuesta al escalón en lazo cerrado.
  5. **Diagrama de Bloques**: representación visual del lazo de control.
- **Interfaz**:
  - Ejemplos rápidos preconfigurados y selector de **Modo Claro / Modo Oscuro**.

---

## 🛠️ Desarrollo de la Versión Desktop (Electron)

El código fuente de la versión de escritorio se encuentra aislado en la carpeta `desktop_exe/`:

```bash
cd desktop_exe
npm install
npm start
```

Para generar el ejecutable portable de Windows en `desktop_exe/dist/`:

```powershell
cd desktop_exe
$env:CSC_IDENTITY_AUTO_DISCOVERY="false"
npm run build
```
