# **Complete Guide to Updating the JuliaPhylo Website**  

---

# **Part 1: Adding a New Package**  

## **Step 1: Identify the Current State of the Packages Section**  
Before adding a new package, check how many packages are currently inside the last `<div class="packages-container">`.

### **Condition 1: The Last `<div class="packages-container">` Already Has 3 Packages**  
If the last container already has **exactly 3 tiles**, **create a new `<div class="packages-container">`** for the new package.

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

---

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

---

# **Part 2: Adding Links to the Community or Resources Section**  

## **Adding a Community Link**  
1. Open `index.html`.  
2. Locate the **Community Section** (`id="community"`).  
3. Inside the `<ul>`, add a new `<li>` entry:

#### **Modification**
```html
<ul>
    <li>Abide by <a href="https://julialang.org/community/standards/">Community Guidelines</a></li>
    <li>Join our **Telegram Group** for discussions: <a href="https://t.me/juliaphylo">JuliaPhylo Telegram</a></li>
</ul>
```

---

## **Adding a Resources Link**  
1. Open `index.html`.  
2. Locate the **Resources Section** (`id="resources"`).  
3. Inside the `<ul>`, add a new `<li>` entry:

#### **Modification**
```html
<ul>
    <li><a href="https://example.com/new-tutorial">New Phylogenetics Tutorial</a> - Learn advanced phylogenetic analysis techniques.</li>
</ul>
```

---

# **Part 3: Running the HTML File Locally**  

## **Method 1: Running HTML Without Extensions (Using a Browser)**  
1. Locate `index.html` in your file explorer. Make suure the `main.css` file is in the same directory as this file.  
2. **Double-click** the file, or:  
   - Right-click → **Open with** → Select your browser (Chrome, Firefox, Edge, etc.).  
3. Refresh the page (`Ctrl + R` or `Cmd + R` on Mac) after making changes.  

---

## **Method 2: Running HTML with the Live Server Extension in VS Code**  
This method provides **auto-reloading** when you save changes. This is helpful when you want to make and test multiple changes to the website.

1. Open **VS Code**.  
2. **Install Live Server Extension on VSCode** (if not installed)
3. **Open the directory with `index.html` and `main.css` in VS Code.**  
4. **Start Live Server:**  
   - Right-click in `index.html` → **"Open with Live Server"**.  
   - OR click the **Go Live** button in the bottom-right of VS Code.  
5. The website opens at `http://127.0.0.1:5500/index.html`.  
6. **Edit and Save (`Ctrl + S`)** → The browser updates automatically.  

