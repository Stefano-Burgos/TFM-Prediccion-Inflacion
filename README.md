# Predicción de Inflación mediante Temporal Fusion Transformers (TFT)
#Predicción de Inflación mediante Temporal Fusion Transformers 
**Autor. **
Estefano Tasiguano Burgos
**Proyecto**
Trabajo de Fin de Máster
## Descripción del Proyecto
Este trabajo evalúa la capacidad del modelo de aprendizaje profundo **Temporal Fusion Transformer** para pronosticar la inflación del IPC a partir de un panel macroeconómico heterogéneo y variables textuales extraídas de comunicaciones de bancos centrales 
## Hipótesis Contrastadas
|Hipótesis |Enunciado |Método de contraste |
| **H1** | El TFT reduce el error de predicción respecto a modelos de referencia. |MAE relativo, contraste Diebold-Mariano de panel y Model Confidence Set (MCS) frente a RW, AR(p), BVAR, Random Forest y Gradient Boosting. |
|**H2** |La inclusión de variables textuales mejora el desempeño, en especial a horizontes largos. |Comparación TFT numérico vs TFT + texto(h=1,2,3) y validación cruzada con Gradient Boosting. |
|**H3** | Los pesos de selección de variables del TFT son estables y económicamente interpretables. | Correlación de Spearman y solape top-20 entre ventanas de reestimación y semillas. |

## Estructura del Cuaderno
El cuaderno principal contiene todo el flujo reproducible:
1. **Fase 0:** Configuración de dependencias (Pytorch Forecasting, LightGBM, Transformens) y extracción de datos.
2. **Fase 1:** Prueba rápida de verificación de punta a punta.
3. **Fase 2:** Corrida completa por etapas (‘prep’, ‘base’, ‘tft’, ‘eval’).
4. **Resultados y figuras:** Tablas resumen de veredictos, gráficos de error por horizonte y análisis de interpretabilidad económica.
