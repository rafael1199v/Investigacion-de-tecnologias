# **Expo Router: Guía Completa**

Este repositorio contiene todo lo necesario para aprender a usar e implementar **Expo Router**, una herramienta poderosa para la navegación en aplicaciones React Native y web.

![This is an alt text.](./images/ExpoRouter.png)

---

## **¿Qué es Expo Router?**

Expo Router es una biblioteca de navegación basada en archivos que simplifica la organización de rutas en aplicaciones React Native y web. Cada archivo dentro del directorio `app/` representa automáticamente una ruta en tu aplicación, lo que reduce la configuración manual y mejora la productividad.

---
## **Cómo usar Expo Router**

### **1. Instalación**
Primero, asegúrate de tener Expo CLI instalado:

```bash
npm install --global eas-cli  
```



Luego, instala Expo Router junto con sus dependencias:
```
npx expo install expo-router react-native-safe-area-context react-native-screens expo-linking expo-constants expo-status-bar
```

---

### **2. Configuración inicial**
Modifica el archivo `package.json` para establecer el punto de entrada principal:
```"main": "expo-router/entry"```

Crea un directorio llamado `app/` dentro de tu proyecto. Este directorio será donde definirás las rutas de tu aplicación.

---

### **3. Crear rutas**
Cada archivo dentro del directorio `app/` representa una ruta automáticamente.

#### Ejemplo básico:
- Archivo: `app/index.jsx` (pantalla principal)

```js
import { View, Text } from 'react-native';

const Home = () => (
<View>
<Text>Bienvenido a la página principal</Text>
</View>
);

export default Home;
```

- Archivo: `app/about.jsx` (pantalla secundaria)
```
import { View, Text } from 'react-native';

const About = () => (
<View>
<Text>Acerca de nosotros</Text>
</View>
);

export default About;
```

#### Configuración del diseño general (`_layout.jsx`):
```
import { Stack } from "expo-router";

const Layout = () => (
<Stack>
<Stack.Screen name="index" options={{ title: "Inicio" }} />
<Stack.Screen name="about" options={{ title: "Acerca de" }} />
</Stack>
);

export default Layout;
```
---

### **4. Probar tu aplicación**
Inicia el servidor de desarrollo con:
```
npx expo start
```

Esto abrirá una interfaz interactiva donde puedes probar tu aplicación en dispositivos Android, iOS o navegadores web.

---

## **Cómo implementar Expo Router**

### Paso 1: Identificar necesidades del proyecto
Define qué tipo de navegación necesitas (rutas simples, pestañas, etc.).

### Paso 2: Crear rutas dinámicas
Expo Router también soporta rutas dinámicas. Por ejemplo:
- Archivo: `app/[id].jsx`
```
import { useRouter, useSearchParams } from "expo-router";
import { View, Text } from "react-native";

const DynamicPage = () => {
const { id } = useSearchParams();
return (
<View>
<Text>Ruta dinámica con ID: {id}</Text>
</View>
);
};

export default DynamicPage;
```
Accediendo a `/123`, se mostrará "Ruta dinámica con ID: 123".

### Paso 3: Desplegar la aplicación
Usa EAS Hosting para desplegar tu aplicación:
1. Inicia sesión en Expo CLI:
```
eas login
```

2. Construye tu aplicación:
```
eas build --platform all
```

3. Despliega tu aplicación:
```
eas update --branch main
```

---

## **Comparación práctica: Expo Router vs React Navigation**

### Ejemplo con Expo Router (Rutas basadas en archivos)
- Archivo `app/index.jsx`:
```
import { View, Text } from 'react-native';

const Home = () => (
<View>
<Text>Página principal</Text>
</View>
);

export default Home;
```

- Archivo `app/profile.jsx`:
```
import { View, Text } from 'react-native';

const Profile = () => (
<View>
<Text>Perfil del usuario</Text>
</View>
);

export default Profile;
```

### Ejemplo con React Navigation (Rutas manuales)
- Configuración inicial:
```
npm install @react-navigation/native react-native-screens react-native-safe-area-context react-navigation-stack react-native-gesture-handler react-native-reanimated react-native-linking
```

- Código para navegación:
```
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import { View, Text } from 'react-native';

const Stack = createStackNavigator();

const HomeScreen = () => (
<View>
<Text>Página principal</Text>
</View>
);

const ProfileScreen = () => (
<View>
<Text>Perfil del usuario</Text>
</View>
);

export default function App() {
return (
<NavigationContainer>
<Stack.Navigator initialRouteName="Home">
<Stack.Screen name="Home" component={HomeScreen} />
<Stack.Screen name="Profile" component={ProfileScreen} />
</Stack.Navigator>
</NavigationContainer>
);
}
```

---
## **Tabla Comparativa: Expo Router vs React Navigation**

| **Característica**         | **Expo Router**                                                                 | **React Navigation**                                                        |
|-----------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **Modelo de rutas**         | Basado en archivos. Cada archivo es una ruta automáticamente.                | Configuración manual de rutas mediante código.                              |
| **Compatibilidad multiplataforma** | Funciona en Android, iOS y web.                                              | Compatible con Android e iOS; requiere configuración adicional para la web. |
| **SEO (para web)**          | Compatible gracias a las rutas estáticas y dinámicas.                         | No optimizado para SEO sin configuraciones adicionales.                     |
| **Configuración inicial**   | Sencilla: solo instala y configura el directorio `app/`.                      | Más compleja: requiere definir navegadores y rutas explícitamente.          |
| **Enlaces profundos (Deep Linking)** | Automáticos y fáciles de configurar.                                        | Requiere configuraciones manuales adicionales.                              |

---

## **Conclusión**

Expo Router es una solución poderosa y eficiente para gestionar la navegación en aplicaciones React Native y web gracias a su enfoque basado en archivos. Comparado con herramientas como React Navigation, simplifica la configuración inicial y automatiza procesos como enlaces profundos y SEO. 

---

