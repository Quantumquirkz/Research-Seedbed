# Semillero de Investigadores - Plataforma Web

## Facultad de Ingeniería de Sistemas Computacionales
### Vicedecanato de Investigación, Postgrado y Extensión

---

## Descripción General

El **Semillero de Investigadores** es una iniciativa académica de la Facultad de Ingeniería de Sistemas Computacionales de la Universidad Tecnológica de Panamá, diseñada para crear un espacio de encuentro entre estudiantes y docentes investigadores. Esta plataforma web complementa el proceso de formación académica mediante el desarrollo de proyectos de investigación con impacto nacional e internacional.

La plataforma digital implementa un sistema de matching inteligente que facilita la conexión entre mentores, estudiantes y proyectos de investigación, optimizando la colaboración y maximizando el potencial de desarrollo en el ámbito investigativo.

## Objetivos del Proyecto

### Objetivo General
Crear un espacio digital para el encuentro entre estudiantes y docentes investigadores que complemente el proceso de formación académica con el desarrollo de proyectos de investigación con impacto nacional e internacional.

### Objetivos Específicos
- **Fomentar la colaboración** entre estudiantes e investigadores para todas las carreras y niveles dentro de la Facultad
- **Proporcionar espacios digitales** para que estudiantes e investigadores colaboren y compartan ideas y proyectos
- **Desarrollar habilidades de investigación** y pensamiento crítico en los estudiantes a través de actividades motivadoras
- **Brindar experiencias prácticas** de investigación a estudiantes para realizar proyectos de alta calidad
- **Difundir resultados de investigación** en congresos y revistas nacionales e internacionales
- **Promover la transferencia de conocimiento** bidireccional entre el sector privado y la academia
- **Elevar la calidad de trabajos de investigación** científico dentro de la Facultad

## Características de la Plataforma

### 🔗 Sistema de Matching Inteligente
- **Algoritmo de emparejamiento** que conecta automáticamente estudiantes con mentores basado en:
  - Áreas de interés y especialización
  - Nivel académico y experiencia
  - Disponibilidad temporal
  - Compatibilidad de objetivos de investigación

### 👥 Gestión de Usuarios y Roles
- **Sistema multi-rol** que permite diferentes tipos de usuarios:
  - Coordinadores del Semillero
  - Docentes Investigadores
  - Investigadores (SNI)
  - Mentores (Comunidad UTP y Sector Privado)
  - Estudiantes Participantes
  - Egresados

### 📊 Dashboard de Seguimiento
- **Panel de control** para monitorear el progreso de proyectos
- **Métricas de participación** y asistencia
- **Indicadores de rendimiento** académico e investigativo
- **Reportes automáticos** de avances y logros

### 🎯 Gestión de Proyectos
- **Creación y administración** de proyectos de investigación
- **Asignación automática** de recursos y participantes
- **Seguimiento de hitos** y entregables
- **Integración con sistemas** de evaluación académica

## Arquitectura del Sistema

### Componentes Principales

#### 1. Módulo de Matching
- **Motor de recomendaciones** basado en algoritmos de machine learning
- **Sistema de scoring** para evaluar compatibilidad entre usuarios
- **Optimización de recursos** para maximizar el impacto de las colaboraciones

#### 2. Módulo de Gestión de Usuarios
- **Autenticación y autorización** segura
- **Perfiles dinámicos** con información académica y profesional
- **Sistema de notificaciones** en tiempo real

#### 3. Módulo de Proyectos
- **CRUD completo** para gestión de proyectos
- **Workflow de aprobación** para nuevos proyectos
- **Integración con calendarios** académicos

#### 4. Módulo de Comunicación
- **Sistema de mensajería** integrado
- **Foros de discusión** por proyecto
- **Herramientas de colaboración** en tiempo real

## Algoritmo de Matching

### Metodología

El algoritmo de matching implementa un sistema de recomendación multicriterio que evalúa la compatibilidad entre mentores y estudiantes basándose en:

#### Criterios de Evaluación
1. **Compatibilidad Académica**
   - Áreas de especialización
   - Nivel de experiencia requerido vs. disponible
   - Historial académico del estudiante

2. **Factores Temporales**
   - Disponibilidad de horarios
   - Duración del proyecto
   - Compromisos académicos existentes

3. **Preferencias Personales**
   - Estilo de trabajo
   - Metodologías de investigación
   - Objetivos de desarrollo profesional

4. **Historial de Colaboración**
   - Proyectos anteriores exitosos
   - Retroalimentación de colaboraciones pasadas
   - Tasa de finalización de proyectos

#### Proceso de Matching
1. **Recolección de datos** de perfiles de usuarios
2. **Análisis de compatibilidad** mediante algoritmos de similitud
3. **Generación de recomendaciones** con scores de compatibilidad
4. **Optimización global** para maximizar el número de matches exitosos
5. **Presentación de resultados** con opciones de personalización

## Roles y Permisos

### Coordinador del Semillero
- **Supervisión general** de todos los proyectos y actividades
- **Gestión de usuarios** y asignación de roles
- **Generación de reportes** institucionales
- **Configuración del sistema** de matching

### Docente Investigador
- **Liderazgo de proyectos** de investigación
- **Selección de estudiantes** participantes
- **Gestión de recursos** y presupuestos
- **Evaluación de avances** académicos

### Investigador (SNI)
- **Participación en proyectos** de alto impacto
- **Mentoría especializada** en áreas específicas
- **Colaboración internacional** y networking
- **Publicación de resultados** científicos

### Mentores
- **Asesoría técnica** en desarrollo de proyectos
- **Transferencia de conocimiento** desde la industria
- **Apoyo en metodologías** de investigación
- **Networking profesional** con estudiantes

### Estudiante Participante
- **Participación activa** en proyectos asignados
- **Acceso a recursos** académicos y bibliográficos
- **Comunicación directa** con mentores y coordinadores
- **Seguimiento de progreso** académico

## Instalación y Configuración

### Prerrequisitos
- Node.js (versión 16 o superior)
- PostgreSQL (versión 13 o superior)
- Redis (para cache y sesiones)
- Git

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/utp-fisc/semillero-investigadores.git
cd semillero-investigadores
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Configurar variables de entorno**
```bash
cp .env.example .env
# Editar el archivo .env con las configuraciones necesarias
```

4. **Configurar la base de datos**
```bash
npm run db:migrate
npm run db:seed
```

5. **Iniciar el servidor**
```bash
npm run dev
```

### Configuración del Algoritmo de Matching

El algoritmo de matching puede ser configurado mediante el archivo `config/matching.js`:

```javascript
module.exports = {
  weights: {
    academic: 0.4,      // Peso para compatibilidad académica
    temporal: 0.2,      // Peso para factores temporales
    preferences: 0.3,   // Peso para preferencias personales
    history: 0.1        // Peso para historial de colaboración
  },
  thresholds: {
    minimumScore: 0.6,  // Score mínimo para considerar un match
    maxMatches: 5       // Máximo número de recomendaciones por usuario
  }
};
```

## Uso de la Plataforma

### Para Estudiantes
1. **Registro** en la plataforma con información académica
2. **Completar perfil** con intereses y disponibilidad
3. **Explorar proyectos** disponibles
4. **Solicitar participación** en proyectos de interés
5. **Recibir notificaciones** sobre matches con mentores

### Para Mentores
1. **Registro** con credenciales profesionales
2. **Definir áreas** de especialización
3. **Crear o unirse** a proyectos existentes
4. **Recibir recomendaciones** de estudiantes compatibles
5. **Gestionar colaboraciones** activas

### Para Coordinadores
1. **Acceso al dashboard** administrativo
2. **Monitoreo de métricas** del sistema
3. **Gestión de proyectos** y usuarios
4. **Generación de reportes** institucionales
5. **Configuración** del algoritmo de matching

## API y Documentación

### Endpoints Principales

#### Autenticación
- `POST /api/auth/login` - Iniciar sesión
- `POST /api/auth/register` - Registro de usuario
- `POST /api/auth/logout` - Cerrar sesión

#### Usuarios
- `GET /api/users/profile` - Obtener perfil del usuario
- `PUT /api/users/profile` - Actualizar perfil
- `GET /api/users/matches` - Obtener recomendaciones de matching

#### Proyectos
- `GET /api/projects` - Listar proyectos disponibles
- `POST /api/projects` - Crear nuevo proyecto
- `GET /api/projects/:id` - Obtener detalles de proyecto
- `PUT /api/projects/:id` - Actualizar proyecto

#### Matching
- `POST /api/matching/calculate` - Calcular matches
- `GET /api/matching/recommendations/:userId` - Obtener recomendaciones
- `POST /api/matching/feedback` - Enviar retroalimentación

### Documentación Completa
La documentación completa de la API está disponible en `/docs` cuando el servidor está ejecutándose.

## Contribución

### Guías para Desarrolladores

1. **Fork** del repositorio
2. **Crear branch** para nueva funcionalidad (`git checkout -b feature/nueva-funcionalidad`)
3. **Commit** de cambios (`git commit -m 'Agregar nueva funcionalidad'`)
4. **Push** al branch (`git push origin feature/nueva-funcionalidad`)
5. **Crear Pull Request**

### Estándares de Código
- Seguir las convenciones de ESLint configuradas
- Escribir tests para nuevas funcionalidades
- Documentar funciones y componentes
- Mantener cobertura de tests > 80%

## Testing

### Ejecutar Tests
```bash
# Tests unitarios
npm run test

# Tests de integración
npm run test:integration

# Tests end-to-end
npm run test:e2e

# Cobertura de tests
npm run test:coverage
```

## Despliegue

### Producción
```bash
npm run build
npm start
```

### Docker
```bash
docker build -t semillero-investigadores .
docker run -p 3000:3000 semillero-investigadores
```

## Monitoreo y Métricas

### Indicadores Clave
- **Tasa de matching exitoso**: > 85%
- **Satisfacción de usuarios**: > 4.5/5
- **Tiempo de respuesta**: < 200ms
- **Disponibilidad del sistema**: > 99.5%

### Herramientas de Monitoreo
- **Logs**: Winston con rotación automática
- **Métricas**: Prometheus + Grafana
- **Alertas**: Slack integration
- **Performance**: New Relic APM

## Seguridad

### Medidas Implementadas
- **Autenticación JWT** con refresh tokens
- **Encriptación** de datos sensibles
- **Rate limiting** para prevenir abuso
- **Validación** de entrada en todos los endpoints
- **HTTPS** obligatorio en producción
- **Auditoría** de acciones críticas

## Roadmap

### Versión 2.0 (Q2 2024)
- [ ] Integración con sistemas académicos externos
- [ ] Dashboard de analytics avanzado
- [ ] Mobile app nativa
- [ ] Sistema de gamificación

### Versión 2.1 (Q3 2024)
- [ ] Integración con bases de datos científicas
- [ ] Sistema de recomendaciones de publicaciones
- [ ] Herramientas de colaboración en tiempo real
- [ ] API pública para integraciones

## Contacto y Soporte

### Equipo de Desarrollo
- **Coordinador Técnico**: [Nombre del coordinador]
- **Lead Developer**: [Nombre del desarrollador]
- **Email**: semillero-investigadores@utp.ac.pa

### Recursos Adicionales
- **Documentación**: [Enlace a documentación completa]
- **Wiki del proyecto**: [Enlace al wiki]
- **Issues y reportes**: [Enlace al sistema de issues]

---

## Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## Agradecimientos

Agradecemos a la Facultad de Ingeniería de Sistemas Computacionales de la Universidad Tecnológica de Panamá por el apoyo y financiamiento de este proyecto, así como a todos los docentes, investigadores y estudiantes que participan activamente en el Semillero de Investigadores.

---

*Última actualización: Diciembre 2023*
*Versión de la plataforma: 1.0.0*