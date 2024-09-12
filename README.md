
# 3D Planet Model

## Overview
This project is a 3D visualization of a planet with an advanced particle system, utilizing the **Three.js** library for 3D graphics rendering and post-processing effects. The primary goal is to create a realistic model of a planet that rotates, accompanied by a dynamic particle system to simulate cosmic dust or star fields.

## Key Components

1. **Scene Setup**
   - The `THREE.Scene()` is initialized to create a container for all 3D objects, lights, and cameras.
   - A **Perspective Camera** is created using `THREE.PerspectiveCamera` with a 75-degree field of view, an aspect ratio matching the window's size, and near and far clipping planes set at 0.1 and 1000, respectively.
   - A **WebGL Renderer** is initialized (`THREE.WebGLRenderer`) to display the 3D scene on the webpage with antialiasing enabled for smoother edges.

2. **Loading Planet Texture**
   - A `THREE.TextureLoader` loads a texture (`/2k_earth_daymap.jpg`) to represent the surface of the planet.
   - The planet is represented using a **Sphere Geometry** (`THREE.SphereGeometry`) with a radius of 1 and 32 segments for width and height, and a **MeshStandardMaterial** is applied to map the loaded texture.

3. **Particle System**
   - An advanced particle system is created with 2000 particles.
   - **BufferGeometry** is used to store data for the particles, including positions, colors, and sizes. Random values are assigned to each particle's position within a spherical volume, color, and size to create a dynamic and varied effect.
   - A **Custom ShaderMaterial** is used to render particles with vertex and fragment shaders to control the appearance of each particle, including size and color, and to apply a texture (`https://threejs.org/examples/textures/sprites/spark1.png`) to each particle for a glowing effect.

4. **Lighting**
   - An **Ambient Light** (`THREE.AmbientLight`) with a color of white (`0xffffff`) and an intensity of 0.5 is added to provide basic, uniform lighting across the scene.
   - A **Point Light** (`THREE.PointLight`) is added with a color of white and full intensity (1), positioned at coordinates (5, 5, 5), simulating a light source that illuminates objects from a specific point.

5. **Camera Positioning**
   - The camera is positioned along the z-axis (`camera.position.z = 5`) to provide a suitable view of the planet and particle system.

6. **Post-Processing Effects**
   - **EffectComposer** is set up for post-processing. This allows applying multiple effects to the rendered scene.
   - **RenderPass** is added to render the scene normally before applying any other effects.
   - **UnrealBloomPass** is configured with reduced settings for a subtle bloom effect, giving a slight glow to bright parts of the scene.
   - **BokehPass** is configured for depth-of-field effects, with reduced aperture and max blur to ensure minimal blurring and keep the scene focused.

7. **Animation Loop**
   - An animation loop is created using `requestAnimationFrame` to continuously update the scene.
   - Within the loop, both the planet and the particle system are slightly rotated (`star.rotation.y` and `particleSystem.rotation.y`) to create a dynamic visual effect.
   - The scene is rendered with post-processing using the `composer.render()` method.

8. **Responsive Window Resizing**
   - An event listener for the `resize` event is added to dynamically adjust the camera's aspect ratio and the renderer size when the window is resized, ensuring the 3D model remains properly displayed.

## How to Use
1. Open the HTML file in any modern web browser with WebGL support.
2. The page will display a 3D rotating planet with a particle system that responds to the movement of the planet.
3. Resize the browser window to see the adaptive resizing in action.

## Dependencies
- **Three.js**: A popular 3D library for JavaScript, loaded via CDN (`https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js`).
- **Post-processing modules**:
  - `EffectComposer`, `RenderPass`, `UnrealBloomPass`, `ShaderPass`, `BokehPass` from Skypack CDN for enhanced visual effects.

## Potential Enhancements
1. **Interactivity**: Add mouse controls for rotating and zooming the camera around the planet.
2. **Additional Textures**: Introduce more textures (e.g., normal maps, specular maps) for a more realistic planetary surface.
3. **Particle System Improvements**: Vary particle movement over time for more dynamic effects.
4. **Dynamic Lighting**: Implement more complex lighting scenarios (e.g., moving light sources) to simulate day-night cycles or eclipses.

This documentation provides a detailed overview of the 3D Planet Model project's structure, functionality, and potential improvements. It serves as a guide for further development and optimization of the project.
# 3d-planet-model
