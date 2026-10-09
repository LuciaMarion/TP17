# TP17: Detección de Secretos y Filtraciones en Git con Gitleaks
Este Trabajo Práctico guía en la instalación, ejecución local e integración automatizada de Gitleaks dentro de la fábrica de software (CI/CD) con GitHub Actions para la Notes App.
## Matriz de Control
| Job en Pipeline | Tipo de Evaluación | Exit Code | Acción ante Hallazgos | Evidencia Generada |
| :--- | :--- | :---: | :--- | :--- |
| `gitleaks-andon-cord` | Secret scanning en historial Git | 1 | **Andon Cord:** Bloquea el pipeline | Resumen en `$GITHUB_STEP_SUMMARY` |
| `gitleaks-audit-report` | Reporte de inspección JSON | 0 | **Informativo:** Genera evidencia | Artifact JSON descargable |

## Fases del workflow: 
Fase 1: Build y Package: construcción única de la imagen
Fase 2A: Gitleaks-Andon Cord: Bloqueante ante secretos expuestos
Fase 2B:Gitleaks- Reporte e inspección: Artifacts
Fase 3: Post-Aprobación de Ciberseguridad

### Todas las fases de verificación en GitHub Actions completaron exitosamente:
| Fase | Estado | Descripción |
| :--- | :---: | :--- |
| **Fase 1: Build & Package** | `Success` | Construcción correcta de la imagen Docker. |
| **Fase 2A: Gitleaks - Andon Cord** | `Success` | Sin presencia de secretos en el código analizado. |
| **Fase 2B: Gitleaks - Reporte** | `Success` | Reporte generado y subido a los artefactos. |
| **Fase 3: Release & Deploy** | `Success` | Post-Aprobación de Ciberseguridad. |
