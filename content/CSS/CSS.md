### 📜 **1996 – CSS1**

- **Introduced by**: W3C
    
- **Key Features**:
    
    - Basic styling: `color`, `font`, `background`, `margin`, `padding`, `border`
        
    - Selectors: element, class, ID
        
    - Box model concept
        
- **Criticism**: Limited layout control, inconsistent browser support

---

### 📘 **1998 – CSS2**

- **Major Additions**:
    
    - Positioning: `absolute`, `relative`, `fixed`
        
    - Media types: `screen`, `print`
        
    - Z-index
        
    - Pseudo-elements like `:before`, `:after`
        
    - `min-width`, `max-width`, etc.
        
- **Flaw**: Poor implementation across browsers delayed its practical use

---

### ⚙️ **2005–2011 – CSS2.1**

- **Purpose**: A revision to fix ambiguities and errors in CSS2
    
- **Finalized in**: 2011
    
- **Impact**: Became the baseline for consistent styling across modern browsers

---

### 🚀 **2009 – CSS3 (Modularization Begins)**

- **Game-changer**: CSS3 was modularized into separate specifications (called modules)
    
- **Key Modules & Features**:
    
    - **Selectors Level 3**: `:nth-child()`, `:not()`
        
    - **Box Model Enhancements**: `box-sizing`
        
    - **Text Effects**: `text-shadow`
        
    - **Backgrounds**: `multiple backgrounds`, `background-size`
        
    - **Transitions & Animations**
        
    - **Transforms**: 2D/3D
        
    - **Flexbox (initial draft)**

---

### 📦 **2012–2016 – Flexbox, Gradients, Media Queries**

- **Flexbox**: Simplified 1D layout handling
    
    - Finalized in **2012**, widely adopted after **2014**
        
- **Media Queries**: Crucial for responsive design
    
- **Gradients**: Linear and radial
    
- **Web Fonts**: `@font-face` revolutionized typography

---

### 🧱 **2017 – CSS Grid**

- **Grid Layout**: First true 2D layout system
    
    - Features: `grid-template-rows`, `grid-template-areas`, `gap`
        
    - Made complex layouts easier without JS hacks

---

### 🎨 **2018–2020 – CSS Variables, Clipping, & Shapes**

- **Custom Properties** (`--my-var`): Scoped variables in CSS
    
- **`clip-path`**: Custom shapes for elements
    
- **Logical Properties**: `margin-inline`, `padding-block` (RTL-aware)

---

### 🌐 **2021 – Container Queries (Draft Spec)**

- Allow styling based on the **size of a parent container**, not the viewport
    
- Early support began showing up in Chrome behind flags

---

### 📏 **2022 – :has() Selector**

- **CSS Relational Selectors**: Like parent selectors
    
    - Example: `div:has(img)` – style a div if it contains an image
        
- Supported in **Chrome, Edge, Safari** (not Firefox initially)

---

### 🧠 **2023 – Wide Support for New Layout Models**

- **Subgrid**: Grid items inherit grid lines from the parent
    
- **Wide adoption** of:
    
    - **`aspect-ratio`**
        
    - **New color functions**: `color-mix()`, `color-contrast()`
        
    - **Layered styles**: `@layer` for managing CSS cascade

---

### 🔮 **2024+ – In Progress / Experimental**

- **CSS Nesting** (native, no preprocessor required)
    
    - Example:
        
        css
        
        CopyEdit
        
        `.card {   color: black;   &:hover {     color: red;   } }`
        
- **Scope-based Styling**: Scoped styles without relying on Shadow DOM
    
- **Enhanced color spaces**: `lab()`, `oklab()`, `lch()` for modern displays
    
- **CSS Toggles**: Like a built-in switch for stateful UI (`@toggle` proposal)

Trigonometric functions