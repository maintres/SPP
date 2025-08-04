# Sistema de Gestión Penitenciaria Provincial (SPP)

## 📋 Descripción General

El **Sistema de Gestión Penitenciaria Provincial (SPP)** es una aplicación web desarrollada para el Servicio Penitenciario Provincial de San Juan, diseñada específicamente para gestionar el informe de ingreso de PPL (Personas Privadas de la Libertad). El sistema permite un control integral de la información personal, legal, médica, psicológica y socio-familiar de los internos.

## 🎯 Objetivos del Sistema

- **Gestión Integral**: Administración completa de la información de PPL desde su ingreso
- **Informes Detallados**: Generación de informes completos de ingreso
- **Control de Acceso**: Sistema de autenticación y autorización por roles
- **Auditoría**: Registro de todas las actividades del sistema
- **Geolocalización**: Integración con datos geográficos para ubicaciones

## 🏗️ Arquitectura del Sistema

### Tecnologías Utilizadas

- **Backend**: PHP 7.4+
- **Base de Datos**: MySQL
- **Frontend**: HTML5, CSS3, JavaScript
- **Framework CSS**: Bootstrap 5.3.2
- **Iconos**: Font Awesome 5.15.4
- **Fuentes**: Google Fonts (Poppins, Roboto)

### Estructura del Proyecto

```
SPP/
├── index.php                 # Punto de entrada principal
├── README.md                 # Documentación del sistema
├── conn/                     # Configuración de base de datos
│   └── connection.php       # Conexión PDO y MySQLi
├── Views/                    # Vistas del sistema
│   ├── home.php            # Página de login
│   ├── logout.php          # Cierre de sesión
│   └── admin/              # Panel administrativo
│       ├── index.php       # Dashboard principal
│       ├── navbar.php      # Navegación
│       ├── footer.php      # Pie de página
│       ├── ppl_index.php   # Gestión de PPL
│       ├── persona_*.php   # Gestión de personas
│       ├── sanitario_*.php # Información médica
│       ├── psiquia_*.php   # Información psicológica
│       └── ...             # Otros módulos
├── css/                     # Estilos del sistema
│   ├── style.css
│   └── styles.css
├── js/                      # Scripts JavaScript
│   ├── alertas.js
│   ├── ppl.js
│   └── tabla.js
├── img/                     # Imágenes del sistema
├── img_ppl/                 # Imágenes de PPL
├── herramientas/            # Utilidades adicionales
└── Base de datos/          # Scripts de base de datos
    ├── spp.sql             # Estructura principal
    └── datos-geolocalizacion.sql
```

## 🗄️ Base de Datos

### Tablas Principales

#### Gestión de Usuarios
- `usuarios` - Usuarios del sistema
- `rol` - Roles de usuario
- `persona` - Información personal de usuarios
- `registro_acceso` - Auditoría de accesos

#### Gestión de PPL
- `ppl` - Información principal de PPL
- `persona` - Datos personales
- `domicilio` - Información de residencia
- `situacionlegal` - Estado legal
- `ppl_causas` - Causas penales
- `delitos` - Tipos de delitos
- `tiposdelito` - Clasificación de delitos

#### Información Médica y Psicológica
- `datos_medicos` - Información médica
- `sanitario_*` - Datos sanitarios
- `psiquiatrico_psicologico` - Evaluación psicológica
- `marcas_cuerpo` - Marcas corporales

#### Información Socio-Familiar
- `ppl_padres` - Información de padres
- `ppl_pareja` - Información de pareja
- `ppl_hijos` - Información de hijos
- `ppl_hermanos` - Información de hermanos
- `ppl_familiar_info` - Información familiar general
- `ppl_situacion_sociofamiliar` - Situación socio-familiar

#### Educación y Laboral
- `educacion` - Información educativa
- `laboral` - Información laboral
- `informe_laboral` - Informes laborales
- `asistencia_espiritual` - Asistencia espiritual

#### Geografía y Ubicación
- `paises` - Países
- `provincias` - Provincias
- `ciudades` - Ciudades
- `juzgado` - Información de juzgados

#### Sistema
- `auditoria` - Registro de auditoría
- `clasificacion` - Clasificaciones del sistema
- `observaciones` - Observaciones generales
- `firma` - Firmas digitales
- `fechappl` - Fechas importantes

## 🔐 Sistema de Autenticación

### Características de Seguridad
- **Encriptación de Contraseñas**: Uso de `password_hash()` y `password_verify()`
- **Sesiones Seguras**: Control de sesiones con PHP
- **Validación de Entrada**: Sanitización de datos de entrada
- **Prevención de SQL Injection**: Uso de consultas preparadas con PDO

### Roles de Usuario
- **Administrador**: Acceso completo al sistema
- **Usuario Estándar**: Acceso limitado según permisos

## 📊 Módulos Principales

### 1. Gestión de PPL
- **Registro de Ingreso**: Captura de datos personales básicos
- **Información Legal**: Estado legal, causas, sentencias
- **Datos Biométricos**: Huellas dactilares, fotografía
- **Información Médica**: Historial médico, condiciones especiales

### 2. Información Personal
- **Datos Personales**: Nombre, documento, fecha de nacimiento
- **Domicilio**: Dirección, ciudad, provincia
- **Contacto**: Información de contacto de emergencia

### 3. Información Socio-Familiar
- **Familia Directa**: Padres, hermanos, hijos
- **Pareja**: Información de la pareja actual
- **Situación Familiar**: Análisis socio-familiar

### 4. Información Médica y Psicológica
- **Historial Médico**: Enfermedades, tratamientos
- **Evaluación Psicológica**: Estado mental, evaluaciones
- **Marcas Corporales**: Identificación de marcas distintivas

### 5. Información Educativa y Laboral
- **Educación**: Nivel educativo, estudios
- **Experiencia Laboral**: Trabajos previos, habilidades
- **Asistencia Espiritual**: Prácticas religiosas

### 6. Sistema de Informes
- **Generación de Informes**: Informes completos de ingreso
- **Exportación**: Múltiples formatos de salida
- **Auditoría**: Registro de todas las operaciones

## 🚀 Instalación y Configuración

### Requisitos del Sistema
- **Servidor Web**: Apache/Nginx
- **PHP**: 7.4 o superior
- **MySQL**: 5.7 o superior
- **Extensiones PHP**: PDO, MySQLi, GD

### Pasos de Instalación

1. **Clonar el Repositorio**
   ```bash
   git clone [URL_DEL_REPOSITORIO]
   cd SPP
   ```

2. **Configurar Base de Datos**
   - Crear base de datos MySQL: `spp`
   - Importar archivo: `Base de datos/spp.sql`
   - Importar datos geográficos: `Base de datos/datos-geolocalizacion.sql`

3. **Configurar Conexión**
   - Editar `conn/connection.php`
   - Actualizar credenciales de base de datos:
     ```php
     $db_host = 'localhost';
     $db_name = 'spp';
     $db_user = 'tu_usuario';
     $db_password = 'tu_contraseña';
     ```

4. **Configurar Servidor Web**
   - Apuntar el document root al directorio del proyecto
   - Asegurar permisos de escritura en directorios necesarios

5. **Acceso al Sistema**
   - URL: `http://localhost/SPP`
   - Usuario por defecto: Consultar administrador del sistema

## 🔧 Configuración del Entorno

### Variables de Entorno
```php
// Configuración de base de datos
$db_host = 'localhost';
$db_name = 'spp';
$db_user = 'root';
$db_password = '';

// Configuración de sesión
session_start();
```

### Estructura de Directorios
- **Permisos de Escritura**: `img_ppl/`, `img/`
- **Permisos de Lectura**: Todo el resto del sistema
- **Backup**: Directorio `Base de datos/`

## 📱 Características del Sistema

### Interfaz de Usuario
- **Diseño Responsivo**: Compatible con dispositivos móviles
- **Interfaz Intuitiva**: Navegación clara y fácil de usar
- **Validación en Tiempo Real**: Feedback inmediato al usuario
- **Alertas y Notificaciones**: Sistema de mensajes informativos

## 🖼️ Capturas de Pantalla del Sistema

### Pantalla de Login
![Captura de pantalla 2024-12-13 105907](https://github.com/user-attachments/assets/40b12392-7f0d-40b9-afa0-e480bec85a9a)

### Panel Principal
![Captura de pantalla 2024-12-13 105844](https://github.com/user-attachments/assets/046a4606-8608-49c9-86c9-bf80f84336e7)

### Gestión de PPL
![Captura de pantalla 2024-12-13 105838](https://github.com/user-attachments/assets/bccedd44-3c09-4bb5-af3a-f7f87f209e6d)

### Formulario de Registro
![Captura de pantalla 2024-12-13 105601](https://github.com/user-attachments/assets/a14c8390-6c58-4282-b159-946ad574ba17)

### Información Personal
![Captura de pantalla 2024-12-13 105554](https://github.com/user-attachments/assets/de9ed9a7-794f-428b-9edc-b3eef53a3f49)

### Datos Médicos
![Captura de pantalla 2024-12-13 105547](https://github.com/user-attachments/assets/90afab4d-b25c-4745-9d8e-01505d865e4d)

### Información Socio-Familiar
![Captura de pantalla 2024-12-13 105541](https://github.com/user-attachments/assets/ac5252a1-df11-4f6b-85e5-25e63d730b99)

### Gestión de Usuarios
![Captura de pantalla 2024-12-13 105521](https://github.com/user-attachments/assets/8830ba4e-9602-4243-9545-5ac39c5c5a4d)

### Reportes y Estadísticas
![Captura de pantalla 2024-12-13 105504](https://github.com/user-attachments/assets/834289de-7674-450a-befb-92a953f83249)

### Configuración del Sistema
![Captura de pantalla 2024-12-13 105452](https://github.com/user-attachments/assets/14e9e1e4-f60e-4fe3-bfb6-f4f1e83b644d)

### Auditoría y Logs
![Captura de pantalla 2024-12-13 105419](https://github.com/user-attachments/assets/0bffa0df-cf0e-4a6c-8443-c76981b47bb0)

### Búsqueda Avanzada
![Captura de pantalla 2024-12-13 105411](https://github.com/user-attachments/assets/2894f6f4-1ade-421a-9ba6-72b1b0837a0d)

### Exportación de Datos
![Captura de pantalla 2024-12-13 105350](https://github.com/user-attachments/assets/05aaaabe-4b0c-4e0e-8cd4-8ea3e2562004)

### Panel de Control
![Captura de pantalla 2024-12-13 105329](https://github.com/user-attachments/assets/a8b7557f-24f5-45d6-a053-eb06e1294f2f)

### Funcionalidades Avanzadas
- **Búsqueda Avanzada**: Filtros múltiples para encontrar PPL
- **Exportación de Datos**: Múltiples formatos de salida
- **Geolocalización**: Integración con datos geográficos
- **Auditoría Completa**: Registro de todas las operaciones

## 🔒 Seguridad

### Medidas Implementadas
- **Autenticación Segura**: Contraseñas encriptadas
- **Control de Sesiones**: Timeout automático
- **Validación de Entrada**: Sanitización de datos
- **Prevención de Ataques**: Protección contra SQL Injection
- **Logs de Auditoría**: Registro de actividades

### Recomendaciones de Seguridad
- Cambiar credenciales por defecto
- Configurar HTTPS en producción
- Realizar backups regulares
- Mantener actualizado el sistema

## 📈 Mantenimiento

### Backups
- **Base de Datos**: Backup diario automático
- **Archivos**: Backup semanal del sistema
- **Logs**: Rotación automática de logs

### Actualizaciones
- **Versiones**: Control de versiones con Git
- **Parches**: Aplicación de actualizaciones de seguridad
- **Testing**: Pruebas antes de implementar cambios

## 🤝 Soporte y Contacto

### Equipo de Desarrollo
- **Desarrollador Principal**: [Nombre del Desarrollador]
- **Institución**: Servicio Penitenciario Provincial de San Juan
- **Contacto**: [Información de contacto]

### Documentación Adicional
- **Manual de Usuario**: Disponible en el sistema
- **Manual Técnico**: Documentación para desarrolladores
- **API Documentation**: Para integraciones futuras

## 📄 Licencia

Este sistema fue desarrollado específicamente para el Servicio Penitenciario Provincial de San Juan. Todos los derechos reservados.

---

**Versión**: 1.0  
**Última Actualización**: Diciembre 2024  
**Estado**: En Producción
