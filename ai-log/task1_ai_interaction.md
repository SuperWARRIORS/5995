# Task 1 – AI Interaction Log: Choosing and Setting Up APK Decompilation Tooling

## Objective
Use AI assistance to choose and set up a decompilation tool for auditing an Android APK on macOS.

---

## Step-by-step AI Interaction

### Step 1 – Ask AI which decompilation tools to use

**User:**  
The following file is an apk file, for auditing an Android APK on macOS, what decompilation tools should I use and why?

**AI:**  
For macOS APK auditing, it is recommended to use a toolchain rather than a single tool:

- **JADX (GUI + CLI)**  
  Best first pass for APKs. It decompiles `classes.dex` into readable Java/Kotlin-like code quickly and allows easy navigation, searching, and code analysis.

- **apktool**  
  Useful for decoding `AndroidManifest.xml`, resources, layouts, and smali bytecode. It helps when JADX output is incomplete or when inspecting application resources.

- **baksmali / smali**  
  Provides low-level DEX instruction inspection, which is useful for verifying program logic when Java decompilation may be inaccurate.

- **Ghidra (or IDA Free)**  
  Needed when APKs contain native libraries (`.so` files). Java decompilers cannot analyze native code.

- **dex2jar + CFR / JD-GUI (optional)**  
  A secondary Java decompilation approach that can be used to cross-check results when JADX struggles with heavily obfuscated code.

**Recommendation:**  
Start with **JADX** for fast initial analysis, then use **apktool** or other tools if deeper inspection is required.

---

### Step 2 – Ask AI which jadx file to download for macOS

**User:**  
On the jadx GitHub Releases page, which asset should I download for macOS?

**AI:**  
Download **`jadx-<version>.zip`** (for example `jadx-1.5.5.zip`).

**Reason:**
- Files ending with `-win` are Windows-only.
- `jadx-<version>.zip` is the cross-platform bundle that works on macOS and Linux.

Alternatively, jadx can be installed using Homebrew:

```
brew install jadx
```

---

### Step 3 – Ask AI how to start jadx-gui

**User:**  
After extracting the zip, how do I start jadx-gui on Mac?

**AI:**  
Open Terminal and run:

```
cd jadx-1.5.5
./bin/jadx-gui
```

If macOS blocks execution the first time, run:

```
chmod +x ./bin/jadx ./bin/jadx-gui
./bin/jadx-gui
```

If Java is not installed, install it first:

```
brew install openjdk
```

---

### Step 4 – Confirm that the tool works

**User:**  
I launched jadx-gui and opened `a1_case1.apk`. The project tree shows `Resources/AndroidManifest.xml` and `Source code` packages.

**AI:**  
This indicates that the APK was successfully loaded and decompiled. The source code and application resources are now accessible for further security auditing.

---

## Result

With the assistance of AI, the **jadx** decompilation tool was selected and successfully set up on macOS.  
The APK file `a1_case1.apk` was opened in **jadx-gui**, and the project structure including `AndroidManifest.xml` and source code packages was successfully displayed, confirming that the decompilation environment is ready for further analysis.
