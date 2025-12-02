# Liquid Ether

A mesmerizing WebGL fluid simulation effect built with Three.js. Create beautiful, interactive liquid-like animations that respond to mouse and touch interactions.

![Liquid Ether Demo](https://liquidetherdemo.vercel.app/)

## ✨ Features

- **Real-time Fluid Simulation** - Physics-based fluid dynamics using advection, divergence, and pressure calculations
- **Interactive** - Responds to mouse movements and touch gestures
- **Auto Demo Mode** - Beautiful autonomous animation when idle
- **Customizable Colors** - Easy to configure color palette
- **Smooth Transitions** - Seamless takeover from auto-mode to user interaction
- **Performance Optimized** - Automatic pause when tab is hidden or element is out of viewport
- **Responsive** - Adapts to any container size
- **Mobile Friendly** - Full touch support

## 🎮 Demo

### Live Preview

Simply open `index.html` in your browser to see the effect in action!

### How it works

1. **Idle State**: The animation runs automatically with smooth, organic movements
2. **Interactive**: Move your mouse or touch the screen to create fluid disturbances
3. **Auto Resume**: After 1 second of inactivity, the auto-animation smoothly takes over

## 🚀 Quick Start

### Basic Usage

1. Clone or download this repository
2. Open `index.html` in a modern browser
3. Enjoy the mesmerizing fluid effect!

### Integration into Your Project

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
  <title>Liquid Ether Effect</title>
</head>
<body>
  <div id="liquid-ether-container" class="liquid-ether-container"></div>
  <script src="script.js"></script>
</body>
</html>
```

## ⚙️ Configuration

Customize the effect by modifying the `config` object at the top of `script.js`:

```javascript
const config = {
  // Interaction
  mouseForce: 20,          // Strength of mouse/touch interaction
  cursorSize: 100,         // Size of the interaction area
  
  // Physics
  isViscous: false,        // Enable viscosity simulation
  viscous: 30,             // Viscosity strength
  iterationsViscous: 32,   // Viscosity calculation iterations
  iterationsPoisson: 32,   // Pressure calculation iterations
  dt: 0.014,               // Time step for simulation
  BFECC: true,             // Back and Forth Error Compensation (smoother results)
  resolution: 0.5,         // Simulation resolution (0.1 - 1.0)
  isBounce: false,         // Bounce off boundaries
  
  // Appearance
  colors: ['#5227FF', '#FF9FFC', '#B19EEF'],  // Color gradient
  
  // Auto Demo
  autoDemo: true,          // Enable auto-animation
  autoSpeed: 0.5,          // Auto-animation movement speed
  autoIntensity: 2.2,      // Auto-animation force multiplier
  takeoverDuration: 0.25,  // Smooth transition duration (seconds)
  autoResumeDelay: 1000,   // Delay before auto-animation resumes (ms)
  autoRampDuration: 0.6    // Fade-in duration for auto-animation
};
```

### Color Customization

Change the `colors` array to create different color schemes:

```javascript
// Sunset
colors: ['#FF6B35', '#F7931E', '#FFD23F']

// Ocean
colors: ['#0077B6', '#00B4D8', '#90E0EF']

// Aurora
colors: ['#00FF87', '#60EFFF', '#FF00E5']

// Fire
colors: ['#FF0000', '#FF7700', '#FFDD00']
```

## 🛠️ Technical Details

### How the Simulation Works

The fluid simulation uses a GPU-accelerated approach with WebGL shaders:

1. **Advection** - Moves the velocity field based on itself (BFECC method for stability)
2. **External Force** - Applies forces from mouse/touch input
3. **Viscosity** (optional) - Simulates fluid thickness
4. **Divergence** - Calculates velocity divergence
5. **Pressure** - Solves pressure using Jacobi iteration
6. **Projection** - Makes the velocity field divergence-free

### Performance Features

- **IntersectionObserver** - Pauses rendering when element is not visible
- **Page Visibility API** - Pauses when browser tab is hidden
- **ResizeObserver** - Efficiently handles container resize
- **Automatic cleanup** - Proper disposal of WebGL resources

## 📁 Project Structure

```
liquid-Ether/
├── index.html      # Main HTML file
├── style.css       # Styling
├── script.js       # Fluid simulation engine
└── README.md       # Documentation
```

## 🌐 Browser Support

- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+
- Mobile browsers (iOS Safari, Chrome for Android)

## 📄 Dependencies

- [Three.js r128](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js) - WebGL library

## 🎨 Use Cases

- **Hero Backgrounds** - Eye-catching landing page backgrounds
- **Loading Screens** - Beautiful loading animations
- **Interactive Art** - Digital art installations
- **Music Visualizers** - Combine with audio for reactive visuals
- **Portfolio Sites** - Stand out with unique effects

## 📝 License

MIT License - Feel free to use in personal and commercial projects.

## 🙏 Credits

Built with ❤️ using Three.js

---

**Enjoy creating beautiful fluid effects!** ✨

