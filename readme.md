# **Guide to Adding a New Package to the JuliaPhylo Website**

This guide explains how to properly add a new package to the website while maintaining the layout and structure.

---

## **Step 1: Identify the Current State of the Packages Section**
Before adding a new package, check how many packages are currently inside the last `<div class="packages-container">`.

### **Condition 1: The Last `<div class="packages-container">` Already Has 3 Packages**
If there are **exactly 3 tiles** in the last container, **create a new `<div class="packages-container">`** for the new package.

#### **Example (Before Adding New Package)**
```html
<div class="packages-container">
    <a href="https://github.com/JuliaPhylo/ExistingPackage1.jl" target="_blank" class="package-link" id="ExistingPackage1-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage1</h1>
            </div>
            <p class="box-text">Description of ExistingPackage1.</p>
        </section>
    </a>

    <a href="https://github.com/JuliaPhylo/ExistingPackage2.jl" target="_blank" class="package-link" id="ExistingPackage2-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage2</h1>
            </div>
            <p class="box-text">Description of ExistingPackage2.</p>
        </section>
    </a>

    <a href="https://github.com/JuliaPhylo/ExistingPackage3.jl" target="_blank" class="package-link" id="ExistingPackage3-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage3</h1>
            </div>
            <p class="box-text">Description of ExistingPackage3.</p>
        </section>
    </a>
</div>
```
#### **Modification (After Adding New Package)**
Since the last container already has 3 tiles, **create a new `<div class="packages-container">`** for the new package:
```html
<div class="packages-container">
    <a href="https://github.com/JuliaPhylo/NewPackage.jl" target="_blank" class="package-link" id="NewPackage-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">NewPackage</h1>
            </div>
            <p class="box-text">NewPackage is a Julia package for [brief description].</p>
        </section>
    </a>
</div>
```

### **Condition 2: The Last `<div class="packages-container">` Has Less Than 3 Packages**
If the last container has **fewer than 3 packages**, simply **add the new package to the existing `<div class="packages-container">`.**

#### **Example (Before Adding New Package)**
```html
<div class="packages-container">
    <a href="https://github.com/JuliaPhylo/ExistingPackage1.jl" target="_blank" class="package-link" id="ExistingPackage1-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage1</h1>
            </div>
            <p class="box-text">Description of ExistingPackage1.</p>
        </section>
    </a>

    <a href="https://github.com/JuliaPhylo/ExistingPackage2.jl" target="_blank" class="package-link" id="ExistingPackage2-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage2</h1>
            </div>
            <p class="box-text">Description of ExistingPackage2.</p>
        </section>
    </a>
</div>
```

#### **Modification (After Adding New Package)**
Since the last container has only **two** packages, **add the new package to the same container**:
```html
<div class="packages-container">
    <a href="https://github.com/JuliaPhylo/ExistingPackage1.jl" target="_blank" class="package-link" id="ExistingPackage1-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage1</h1>
            </div>
            <p class="box-text">Description of ExistingPackage1.</p>
        </section>
    </a>

    <a href="https://github.com/JuliaPhylo/ExistingPackage2.jl" target="_blank" class="package-link" id="ExistingPackage2-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">ExistingPackage2</h1>
            </div>
            <p class="box-text">Description of ExistingPackage2.</p>
        </section>
    </a>

    <a href="https://github.com/JuliaPhylo/NewPackage.jl" target="_blank" class="package-link" id="NewPackage-section">
        <section class="box">
            <div class="pkg-header">
                <h1 class="pkg-text">NewPackage</h1>
            </div>
            <p class="box-text">NewPackage is a Julia package for [brief description].</p>
        </section>
    </a>
</div>
```

