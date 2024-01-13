# React Three Fiber Starter
This is a simple starter project to help you get started with React Three Fiber, a React renderer for Three.js.

## Getting Started
Follow these steps to set up and run the project:

### 1. Create a new React App
Use Create React App to quickly scaffold a new React project.

```bash
npx create-react-app my-three-fiber-app
cd my-three-fiber-app

_____

> [!NOTE] Install React Three Fiber
> npm install react-three-fiber three @react-three/fiber
> yarn add react-three-fiber three @react-three/fiber

_____

> [!TIP]

// src/ThreeScene.js

import React, { useRef } from 'react';
import { Canvas, useFrame } from '@react-three/fiber';

const Box = (props) => {
  const mesh = useRef();

  useFrame(() => {
    mesh.current.rotation.x += 0.01;
    mesh.current.rotation.y += 0.01;
  });

  return (
    <mesh {...props} ref={mesh}>
      <boxBufferGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color="orange" />
    </mesh>
  );
};

const ThreeScene = () => {
  return (
    <Canvas>
      <ambientLight />
      <pointLight position={[10, 10, 10]} />
      <Box position={[-1.2, 0, 0]} />
    </Canvas>
  );
};

export default ThreeScene;

------
> [!TIP] Use the 3D Component
// src/App.js

import React from 'react';
import ThreeScene from './ThreeScene';

function App() {
  return (
    <div style={{ height: '100vh', display: 'flex', justifyContent: 'center', alignItems: 'center' }}>
      <ThreeScene />
    </div>
  );
}

export default App;


