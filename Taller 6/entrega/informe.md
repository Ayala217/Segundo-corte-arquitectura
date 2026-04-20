# Taller 6 – Informe

## Cliente
**Ataraxia Parkour Gym (Bogotá)**

## Integrantes
- Arciniegas Guerrero Camilo  
- Ayala Silva Juan Sebastián  
- Campo Conde Juan Diego  

## Nota: En el archivo de Excel adjunto, los numerales del checklist que no se incluyeron son porque no se tiene información certera y se prefiere no poner falsa información con eso. 

## 1. Alcance del sistema evaluado
Para Ataraxia Parkour Gym, el “sistema” no es una plataforma propia, sino el conjunto de prácticas y herramientas que soportan la operación diaria:

- **Registro:** archivo Excel alojado en una nube privada (no se especifica pero se cree que es Google Drive).
- **Canal de atención:** WhatsApp Business (reciben comprobantes de transferencias y atienden clientes e interesados).
- **Pagos:** transferencia a Bancolombia (QR/llave), datáfono y efectivo.
- **Consentimiento informado:** formato físico (tratamiento de datos e imagen).

## 2. Resultado del checklist
Conteo de cumplimiento (11 criterios):
- Cumple: 0
- Parcial / evidencia incompleta: 4
- Brecha: 7

**Riesgos más relevantes:**
1) **Cumplimiento Ley 1581 incompleto**: hay consentimiento físico, pero no hay responsable designado ni retención clara (los chats se conservan indefinidamente en WhatsApp).  
2) **Datos de menores y sensibles**: se recolectan datos de menores y potencialmente de salud sin controles especiales demostrables.  
3) **Seguridad de cuentas**: no se conoce el uso de MFA/2FA para nube y WhatsApp; y hay permisos similares para todos los profesores.  
4) **Backups / continuidad**: no hay evidencia de copias, versionado ni pruebas de recuperación; nube no especificada.

## 3. Hallazgos por normativa / dominio

### 3.1 Decreto 1377 de 2013
**Estado:**  
- Si se recolectan datos de niños y adolescentes, se requieren controles y criterios especiales (interés superior, autorización del acudiente, minimización, custodia).

**Recomendaciones:**
- Minimizar datos (no pedir datos de más).
- Limitar acceso a información de menores y salud sólo al staff que necesita dicha información.
- Mantener los formatos físicos en un lugar seguro y controlar quién consulta.

### 3.2 ISO/IEC 27001
**Estado:**
Brechas típicas encontradas:
- Sin gestión formal de riesgos.
- Sin plan de incidentes.
- Sin auditoría/logs.
- Sin backups/versionado probado.
- Sin MFA confirmado.
- Riesgo de fuga por uso de WhatsApp y archivo de Excel sin política.

## 4. Plan de acción recomendado

### 0–15 días
1) Activar verificación en dos pasos en WhatsApp Business y MFA en Google Drive.

### 1–2 meses
2) Migrar el Excel a una nube con versionado y permisos y restringir accesos por rol.  
3) Crear matriz simple de riesgos (probabilidad/impacto) y plan a seguir.  

### 3 meses en adelante
4) Definir plan de respuesta a incidentes (pérdida de celular, filtración, robo de cuenta).  
5) Considerar una herramienta de gestión para disminuir trabajo manual.

## 5. Referencias
- Ley 1581 de 2012 (Colombia) – Protección de datos personales: https://www.funcionpublica.gov.co/eva/gestornormativo/norma.php?i=49981
- Decreto 1377 de 2013 – Reglamenta parcialmente la Ley 1581 (incluye requisitos especiales para datos de NNA): https://www.funcionpublica.gov.co/eva/gestornormativo/norma.php?i=53646
- Habeas Data financiero (Ley 1266 de 2008) – alcance sectorial (contexto): https://www.superfinanciera.gov.co/publicaciones/16083/normativanormativa-generalboletin-juridico-superintendencia-financieraboletin-juridico-no-habeas-data-ley-de-campo-de-aplicacion-16083/
