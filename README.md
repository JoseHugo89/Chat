Documentación: Sistema de Chat en Vivo
Estructura del Proyecto
Frontend (client/)
Copy
client/
├── src/
│   ├── assets/             # Recursos estáticos
│   │   ├── avarter.svg
│   │   └── example design.PNG
│   ├── components/         # Componentes React
│   │   ├── chat/          # Componentes específicos del chat
│   │   │   ├── AllUsers.jsx       # Lista de usuarios
│   │   │   ├── ChatBox.jsx        # Contenedor principal del chat
│   │   │   ├── Notifications.jsx   # Sistema de notificaciones
│   │   │   ├── UserCard.jsx       # Tarjeta de perfil de usuario
│   │   │   └── NavBar.jsx         # Barra de navegación
│   ├── context/           # Contextos de React
│   │   ├── AuthContext.jsx    # Manejo de autenticación
│   │   └── ChatContext.jsx    # Estado global del chat
│   ├── hooks/             # Hooks personalizados
│   │   ├── useFetchLatestMessage.js  # Obtener últimos mensajes
│   │   └── useFetchRecipient.js      # Obtener datos del destinatario
│   └── utils/             # Utilidades
Backend (server/)
Copy
server/
├── Controllers/          # Controladores
│   ├── chatController.js    # Lógica de chat
│   ├── messageController.js # Gestión de mensajes
│   └── userController.js    # Gestión de usuarios
├── Models/              # Modelos de MongoDB 
│   ├── chatModel.js       # Esquema de chats
│   ├── messageModel.js    # Esquema de mensajes
│   └── userModel.js       # Esquema de usuarios
├── Routes/              # Rutas de la API
│   ├── chatRoute.js      # Rutas de chat
│   ├── messageRoute.js   # Rutas de mensajes
│   └── userRoute.js      # Rutas de usuarios
└── socket/             # Configuración de Socket.IO
Componentes Principales
Frontend
1. ChatBox.jsx
Componente principal del chat
Maneja la interfaz de mensajes
Integra emojis y entrada de texto
Gestiona el historial de mensajes
2. AllUsers.jsx
Muestra lista de usuarios activos
Estado de conexión en tiempo real
Búsqueda y filtrado de usuarios
3. Notifications.jsx
Sistema de notificaciones
Alertas de nuevos mensajes
Indicadores de mensajes no leídos
4. UserCard.jsx
Muestra información del usuario
Avatar y estado de conexión
Información básica del perfil
Backend
1. Controllers
chatController.js: Gestión de conversaciones
messageController.js: CRUD de mensajes
userController.js: Gestión de usuarios y autenticación
2. Models
chatModel.js: Estructura de conversaciones
messageModel.js: Estructura de mensajes
userModel.js: Estructura de usuarios
Flujo de Datos
1. Autenticación
javascript
Copy
// AuthContext.jsx
- Manejo de registro/login
- Almacenamiento de tokens
- Control de sesiones
2. Mensajería
javascript
Copy
// ChatContext.jsx
- Estado global del chat
- Gestión de mensajes activos
- Control de conversaciones
3. Hooks Personalizados
javascript
Copy
// useFetchLatestMessage.js
- Obtención de últimos mensajes
- Actualización en tiempo real

// useFetchRecipient.js
- Datos del destinatario
- Gestión de usuarios en chat
Características Técnicas
Socket.IO Integration
Comunicación bidireccional
Eventos en tiempo real
Estado de conexión de usuarios
MongoDB Schema
javascript
Copy
// userModel.js
{
  username: String,
  email: String,
  password: String,
  // ...
}

// messageModel.js
{
  conversationId: ObjectId,
  sender: ObjectId,
  text: String,
  // ...
}
Rutas API
User Routes
javascript
Copy
POST /api/users/register
POST /api/users/login
GET /api/users/find
Message Routes
javascript
Copy
POST /api/messages
GET /api/messages/:conversationId
Chat Routes
javascript
Copy
POST /api/chats
GET /api/chats/:userId
Mejoras Sugeridas
Implementación
Sistema de archivos adjuntos
Mensajes de voz
Videollamadas integradas
Chat grupal
Características
Mensajes destacados
Búsqueda avanzada
Reacciones a mensajes
Estados personalizados
Seguridad
Cifrado end-to-end
Autenticación 2FA
Respaldo de mensajes
Control de spam

