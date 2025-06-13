#### **1989–1993: The Conception Era**

- **1989** – Tim Berners-Lee proposes a hypertext system (WorldWideWeb).
    
- **1991** – First version of HTML: ~18 tags.
    
    - No standard; just a doc: _“HTML Tags”_.
        
    - Included `<p>`, `<a>`, `<img>`, `<br>`, `<ul>`, etc.
        
    - Styling was inline, semantic understanding was minimal.
        

---

#### **1995: HTML 2.0**

- First official **IETF standard** (RFC 1866).
    
- Codified the earlier tag soup.
    
- Features:
    
    - Forms: `<form>`, `<input>`, `<select>`, `<textarea>`.
        
    - Tables: `<table>`, `<tr>`, `<td>`.
        
- Still basic — CSS, scripting, multimedia all absent.
    

---

#### **1997: HTML 3.2**

- Controlled by W3C.
    
- Bizarre mixture of presentational and semantic markup.
    
- New:
    
    - `<font>`, `<center>`, `<div>`, `<script>`, `<style>`.
        
    - Scripting allowed (JS got in).
        
    - CSS officially supported (barely used).
        

---

#### **1999: HTML 4.01**

- A serious attempt at cleaning up.
    
- Split into:
    
    - **Strict** (no presentational tags),
        
    - **Transitional** (includes `<font>`, `<center>`, etc.),
        
    - **Frameset** (supports frames).
        
- Big deals:
    
    - Better support for **accessibility** and **internationalization**.
        
    - **DOM level 1** standardized.
        

---

#### **2000–2004: The Dark Ages**

- W3C pushes **XHTML 1.0**: XML syntax + HTML.
    
    - Not backwards compatible.
        
    - Websites mostly ignored it or used it incorrectly.
        
- W3C proposes **XHTML 2.0** (dead on arrival).
    
    - No `<img>`, no backward compatibility, no support.
        
    - Developers ignored it. Eventually killed.
        

---

#### **2008–2014: HTML5 (The Resurrection)**

- Spearheaded by **WHATWG**, not W3C.
    
- HTML5 = reboot.
    
- Goals: semantic clarity, native multimedia, web apps.
    
- Major features:
    
    - **New semantic tags**: `<section>`, `<article>`, `<header>`, `<footer>`, `<nav>`, `<main>`, `<aside>`.
        
    - **Multimedia**: `<video>`, `<audio>`, `<source>`, `<track>`.
        
    - **Form enhancements**: `type="email"`, `type="date"`, `placeholder`, `required`, etc.
        
    - **APIs**: Offline storage (localStorage), Geolocation, Canvas (`<canvas>`), Web Workers, WebSockets.
        
    - Deprecated presentational tags: `<font>`, `<center>`, `<big>`.
        

---

#### **2014–2020: HTML Living Standard**

- WHATWG and W3C finally reconcile.
    
- HTML becomes a **living standard** – no versioning.
    
- Incremental changes:
    
    - `<dialog>` (modal support).
        
    - `<template>` and `<slot>` (Web Components).
        
    - Push for accessibility via ARIA roles.
        
    - Input types and attributes expanded (`inputmode`, `autocapitalize`, etc).
        

---

#### **2021–Now (HTML Living Standard)**

- Still evolving.
    
- Notable additions (often ignored by devs):
    
    - `<picture>` + `srcset`: responsive images.
        
    - Native lazy-loading with `loading="lazy"`.
        
    - Declarative Shadow DOM (finally shipping).
        
    - Better form controls support (e.g. `autocomplete="on"` nuances).
        
    - `inert` attribute: useful for modals.
        
    - Push for privacy, performance, and interop via Interop projects.