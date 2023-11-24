# Pildora React
Desarrollado por Facebook, es una libreria de JavaScript utilizada para construir interfaces de usuario modernas y eficientes. Se enfoca en la creación de componentes reutilizables que gestionan su propio estado y se integran para construir aplicaciones complejas.

## Virtual DOM
React utiliza un DOM virtual para optimizar las actualizaciones, permitiendo una experiencia de usuario más rápida. 
![image](https://github.com/Mauro069/pildora-react/assets/81174890/a2ab10e1-f4c2-4957-9210-138a9fe1bbc1)

## JSX
JSX, que significa "JavaScript XML," es una extensión de la sintaxis de JavaScript que permite escribir código que se parece mucho a HTML o XML. JSX es comúnmente utilizado con React para describir la interfaz de usuario de una aplicación.

```jsx
const element = <h1>Hola Mundo</h1>

React.createElement('h1', null, 'Hola Mundo')
```

JSX parece HTML, lo que facilita la representación de la estructura del componente de manera similar a cómo lo harías con HTML.

## Angular vs React
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <div>
      <h1>{{ title }}</h1>
      <p>{{ message }}</p>
    </div>
  `,
  styles: [
    `
      div {
        text-align: center;
        margin: 20px;
        padding: 20px;
        border: 1px solid #ccc;
        border-radius: 5px;
      }
    `,
  ],
})
export class AppComponent {
  title = 'Hola desde Angular';
  message = '¡Este es un componente en Angular!';
}
```
```jsx
import React from 'react';

function App() {
  const title = 'Hola desde React';
  const message = '¡Este es un componente en React!';

  return (
    <div style={{ textAlign: 'center', margin: '20px', padding: '20px', border: '1px solid #ccc', borderRadius: '5px' }}>
      <h1>{title}</h1>
      <p>{message}</p>
    </div>
  );
}

export default App;
```

### Angular
- Utiliza TypeScript de manera predeterminada
- Es un framework completo que proporciona una solución integral para el desarrollo de aplicaciones, incluyendo herramientas para el enrutamiento, manejo de estado, y más.
- Incluye muchas características por defecto, lo que puede resultar en una aplicación más grande. Sin embargo, también proporciona un conjunto más completo de herramientas y características.
- Utiliza archivos de plantilla HTML para definir la interfaz de usuario y agrega lógica de presentación a través de atributos especiales.
- Utiliza servicios y el patrón de arquitectura Flux para gestionar el estado. También tiene su propio sistema de gestión de estado llamado NgRx.
- Utiliza su propio sistema de "Change Detection" para detectar y aplicar los cambios en el DOM.
- Puede tener una curva de aprendizaje más pronunciada, especialmente para aquellos nuevos en TypeScript y los conceptos específicos de Angular.
- Proporciona un sistema de enrutamiento integrado y potente.

### React
- Utiliza principalmente JavaScript.
- Es una biblioteca de vistas. No proporciona un conjunto de herramientas completo para el desarrollo de aplicaciones, pero puede integrarse fácilmente con otras bibliotecas o herramientas.
- Es más liviano y flexible. Puedes elegir las bibliotecas y herramientas que deseas utilizar en tu proyecto.
- Utiliza JSX, que es una extensión de JavaScript que permite escribir código HTML directamente en archivos JavaScript.
- Utiliza el concepto de "estado" y proporciona el hook useState para gestionarlo. También es común utilizar bibliotecas externas como Redux para aplicaciones más complejas.
- Utiliza una estrategia de "reconciliación" virtual DOM para optimizar las actualizaciones del DOM y mejorar el rendimiento.
- Tiene una curva de aprendizaje más suave, especialmente para aquellos familiarizados con JavaScript.
- Utiliza bibliotecas externas como React Router para el enrutamiento.

## Webs hechas con React
![Group 1](https://github.com/Mauro069/pildora-react/assets/81174890/b7140ecd-e502-42a2-9048-740d65709797)

## Crea tu primer proyecto en React
Create React App (CRA) ya esta deprecado y no lo recomiendan ni en la docu de React.

![Group 2](https://github.com/Mauro069/pildora-react/assets/81174890/0f31e531-453d-43ae-9196-e68efe3d564f)

Te recomiendan usar vite o crear un proyecto directamente en NextJs
```
// Iniciar proyecto
npm create vite@latest

// Instalar dependencias
npm install

// Correr proyecto
npm run dev
```

## Estilos
En React, hay varias formas de agregar estilos a tus componentes.

### Estilos en linea
```jsx
<div style={{
    backgroundColor: 'lightblue',
    padding: '10px',
    borderRadius: '5px',
  }}>
  <p>Este componente tiene estilos en línea.</p>
</div>
```

### Usando CSS
```css
/* styles.css */
.container {
  background-color: lightcoral;
  padding: 10px;
  border-radius: 5px;
}

.text {
  color: white;
  font-size: 16px;
}
```

```jsx
import React from 'react';
import './styles.css';  // Importar el archivo de estilos

const NormalCSSExample = () => {
  return (
    <div className="container">
      <p className="text">Este componente usa estilos CSS normales.</p>
    </div>
  );
};

export default NormalCSSExample;
```

### Usando CSS/SCSS Modules
```css
/* styles.module.css */
.container {
  background-color: lightblue;
  padding: 10px;
  border-radius: 5px;
}

.text {
  color: navy;
  font-size: 16px;
}
```

```jsx
import React from 'react';
import styles from './styles.module.css';  // Importar el archivo de módulos de estilo

const ModuleCSSExample = () => {
  return (
    <div className={styles.container}>
      <p className={styles.text}>Este componente usa módulos de estilos en React.</p>
    </div>
  );
};

export default ModuleCSSExample;
```
En el ejemplo con módulos de estilo, las clases definidas en el archivo styles.module.css se vuelven locales al componente. Esto evita problemas de colisión de nombres de clases en la aplicación y proporciona un alcance más específico para los estilos. Además, la importación de estilos se realiza de manera diferente, utilizando la asignación de estilos directamente desde el objeto styles.

## Hooks
Genial, los Hooks son una parte fundamental de React para trabajar con el estado y el ciclo de vida en componentes funcionales. A continuación, te proporciono explicaciones breves y ejemplos prácticos de algunos de los hooks más utilizados:
- useState
- useEffect
- useContext
- useReducer
- useCallback
- useMemo
- useRef

### useState
useState es un hook en React que permite a los componentes funcionales tener y gestionar estado local. Antes de la introducción de hooks en React, los componentes funcionales eran principalmente "sin estado" y no tenían la capacidad de retener información entre renderizaciones. useState resuelve este problema, permitiendo que los componentes funcionales gestionen su propio estado interno.

```jsx
import React, { useState } from 'react';

function ExampleComponent() {
  // Desestructuración del array devuelto por useState
  const [state, setState] = useState(initialState);

  // 'state' es el valor actual del estado
  // 'setState' es una función que se utiliza para actualizar el estado

  return (
   <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### useEffect
useEffect es otro hook fundamental en React que permite realizar operaciones secundarias en componentes funcionales. Estas operaciones secundarias pueden incluir efectos secundarios, como la suscripción a eventos, la obtención de datos desde una API, manipulación del DOM, entre otras cosas. useEffect se ejecuta después de que el componente se renderiza en el DOM y después de cada actualización.

```jsx
import React, { useState, useEffect } from 'react';

function DataFetcher() {
  const [data, setData] = useState(null);

  useEffect(() => {
    // Lógica para obtener datos (por ejemplo, una solicitud a una API)
    fetchData().then(result => setData(result));

    // Devolución de una función de limpieza (opcional)
    return () => {
      // Código para limpiar el efecto si es necesario
    };
  }, []); // El segundo argumento vacío indica que este efecto se ejecuta solo una vez al montar.

  return (
    <div>
      {data ? <p>Data: {data}</p> : <p>Loading...</p>}
    </div>
  );
}

export default DataFetcher;
```

### useContext
useContext es un hook en React que permite acceder al valor de un contexto directamente en un componente funcional. Los contextos en React proporcionan una forma de pasar datos a través del árbol de componentes sin tener que pasar explícitamente las propiedades a cada nivel.
```jsx
// ThemeContext.js
import React, { createContext, useContext, useState } from 'react';

const ThemeContext = createContext();

export const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState('light');

  const toggleTheme = () => {
    setTheme(prevTheme => (prevTheme === 'light' ? 'dark' : 'light'));
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => {
  return useContext(ThemeContext);
};
```
Y lo usarias asi:
```jsx
// ThemedComponent.js
import React from 'react';
import { useTheme } from './ThemeContext';

const ThemedComponent = () => {
  const { theme, toggleTheme } = useTheme();

  return (
    <div style={{ backgroundColor: theme === 'light' ? '#fff' : '#333', padding: '20px', color: theme === 'light' ? '#333' : '#fff' }}>
      <p>Este componente usa el tema: {theme}</p>
      <button onClick={toggleTheme}>Cambiar Tema</button>
    </div>
  );
};

export default ThemedComponent;

// App.js
import React from 'react';
import { ThemeProvider } from './ThemeContext';
import ThemedComponent from './ThemedComponent';

const App = () => {
  return (
    <ThemeProvider>
      <div>
        <h1>Aplicación con Temas</h1>
        <ThemedComponent />
      </div>
    </ThemeProvider>
  );
};

export default App;
```

### useReducer
useReducer es un hook en React que se utiliza para gestionar el estado de un componente de una manera más compleja, especialmente cuando el estado tiene una lógica más elaborada o cuando varios cambios en el estado dependen del estado anterior.

```jsx
import React, { useReducer } from 'react';

// Reducer function
const reducer = (state, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    case 'DECREMENT':
      return { count: state.count - 1 };
    case 'RESET':
      return { count: 0 };
    default:
      return state;
  }
};

function Counter() {
  // Inicializar el estado usando useReducer
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'INCREMENT' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'DECREMENT' })}>Decrement</button>
      <button onClick={() => dispatch({ type: 'RESET' })}>Reset</button>
    </div>
  );
}

export default Counter;
```

### useRef
useRef es un hook en React que se utiliza para acceder al objeto de referencia mutable en un componente funcional. Los objetos de referencia (ref) en React proporcionan una manera de interactuar con el DOM y otros elementos del componente de manera imperativa. A diferencia del estado, las actualizaciones de las referencias no provocan una nueva renderización del componente.

```jsx
import React, { useRef, useEffect } from 'react';

function AutoFocusInput() {
  // Crear una referencia mutable
  const inputRef = useRef();

  useEffect(() => {
    // Acceder al valor actual de la referencia
    inputRef.current.focus();
  }, []);

  return <input ref={inputRef} placeholder="Auto Focus" />;
}

export default AutoFocusInput;
```

### useCallback
useCallback es un hook en React que se utiliza para memoizar funciones, evitando así su recreación en cada renderización del componente. Esto es útil para optimizar el rendimiento, especialmente cuando se pasan funciones como props a componentes hijos, ya que evita que esos componentes se vuelvan a renderizar innecesariamente.

```jsx
import React, { useCallback, useState } from 'react';

function ClickCounter() {
  const [count, setCount] = useState(0);

  // Crear una función memoizada con useCallback
  const handleClick = useCallback(() => {
    setCount(prevCount => prevCount + 1);
  }, []); // No hay dependencias, la función se crea solo una vez

  return (
    <div>
      <p>Click Count: {count}</p>
      {/* Pasar la función memoizada como prop */}
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}

export default ClickCounter;
```

### useMemo
useMemo es un hook en React que se utiliza para memoizar valores computados. Similar a useCallback, useMemo ayuda a evitar la recalculación de valores en cada renderización del componente, mejorando así el rendimiento.

```jsx
import React, { useMemo, useState } from 'react';

function ExpensiveCalculation({ value }) {
  // Crear un valor memoizado con useMemo
  const result = useMemo(() => {
    // Realizar cálculos costosos basados en 'value'
    return value * 2;
  }, [value]); // El segundo argumento es un array de dependencias

  return <p>Result: {result}</p>;
}

function ExampleComponent() {
  const [inputValue, setInputValue] = useState(0);

  return (
    <div>
      <input
        type="number"
        value={inputValue}
        onChange={(e) => setInputValue(Number(e.target.value))}
      />
      {/* Utilizar el componente con el valor memoizado */}
      <ExpensiveCalculation value={inputValue} />
    </div>
  );
}

export default ExampleComponent;
```

## Custom Hooks
Además de los hooks incorporados, puedes crear tus propios hooks personalizados. Estos son útiles para encapsular la lógica compleja y fomentar la reutilización del código.
```jsx
import { useState, useEffect } from 'react';

function useFetchData(url) {
  const [data, setData] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch(url);
        const result = await response.json();
        setData(result);
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    };

    fetchData();
  }, [url]);

  return data;
}
```
Y lo usarias asi:
```jsx
// Uso del Hook Personalizado
function DataComponent() {
  const apiUrl = 'https://api.example.com/data';
  const data = useFetchData(apiUrl);

  return (
    <div>
      {data ? <p>Data: {data}</p> : <p>Loading...</p>}
    </div>
  );
}
```




