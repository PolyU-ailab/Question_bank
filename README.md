# Question_bank
This repository provides a centralized framework for architecting and hosting a dynamic question bank, leveraging symbolic computation and automated formatting to streamline content delivery in educational environments.

### **Step 1: Download the Anaconda Installer**

First, open your **Terminal**. You need to download the Anaconda installation script. The command depends on whether your Mac has an Apple Silicon chip (M1/M2/M3) or an older Intel chip.

**For Apple Silicon (M1/M2/M3) Macs:**

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-MacOSX-arm64.sh
```

**For Intel Macs:**

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-MacOSX-x86_64.sh
```

*(Note: If you are reading this far in the future, you may want to grab the most up-to-date installer link directly from the [Anaconda website](https://www.google.com/search?q=https://repo.anaconda.com/archive/).)*

-----

### **Step 2: Run the Installer**

Once the download is complete, run the bash script to start the installation. You can use the wildcard `*` to catch the file regardless of which version you downloaded:

```bash
bash Anaconda3-*.sh
```

**During the installation process:**

1.  Press **Enter** to view the license agreement. Keep pressing **Space** to scroll to the bottom.
2.  Type `yes` to accept the license terms.
3.  Press **Enter** to accept the default installation location (usually `~/anaconda3`).
4.  **Crucial Step:** When the installer asks if you wish to run `conda init` to initialize Anaconda3, type `yes`. This sets up your terminal to recognize the `conda` command.

-----

### **Step 3: Activate Anaconda**

To apply the changes made by the installer to your current terminal session, you need to reload your shell profile. Since modern Macs use `zsh` by default:

```bash
source ~/.zshrc
```

*(If you are on an older Mac still using bash, run `source ~/.bash_profile` instead).*

You should now see `(base)` next to your terminal prompt, indicating that the base Anaconda environment is active.

-----

### **Step 4: Install Jupyter Notebook**

Anaconda comes bundled with a lot of tools by default, but to ensure Jupyter Notebook is explicitly installed and updated in your environment, run:

```bash
conda install -y jupyter
```

-----

### **Step 5: Install Your Required Packages**

Looking at your provided Python script, here is a breakdown of what needs to be installed:

  * **Needs Installation:** `numpy`, `pandas`, `ipython` (handles `IPython.display`), and `sympy`.
  * **Built-in standard libraries:** `io` and `random`. (These come pre-packaged with Python automatically, so you do not need to install them\!).

To install the required packages using conda, run this single command:

```bash
conda install -y numpy pandas ipython sympy
```

*(The `-y` flag just automatically says "yes" to the confirmation prompt so it installs without pausing).*

-----

### **Step 6: Launch Jupyter Notebook and Test**

Your environment is now fully set up. To start writing your code:

1.  In your terminal, type:
    ```bash
    jupyter notebook
    ```
2.  This will automatically open a new tab in your default web browser displaying the Jupyter file browser.
3.  Click **New -\> Python 3 (ipykernel)** in the top right to create a new notebook.
4.  Copy and paste your imports into the first cell to verify everything works:

<!-- end list -->

```python
import numpy as np
import pandas as pd
import io
import random
from IPython.display import display, Math
import sympy as sp
from sympy.parsing.latex import parse_latex

print("All packages loaded successfully!")
```

Press **Shift + Enter** to run the cell. If you see your print statement and no error messages, your terminal installation was a complete success.
