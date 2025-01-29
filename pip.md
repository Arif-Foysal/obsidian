#### **How to Create a Virtual Environment for pip**

1. Create the virtual environment:
    
    bash
    
    CopyEdit
    
    `python3 -m venv myenv`
    
2. Activate the virtual environment:
    - macOS/Linux:
        
        bash
        
        CopyEdit
        
        `source myenv/bin/activate`
        
    - Windows:
        
        cmd
        
        CopyEdit
        
        `myenv\Scripts\activate`
        

---

#### **Step 2: Install Selenium and WebDriver-Manager**

Once the virtual environment is active:

bash

CopyEdit

`pip install selenium webdriver-manager`

---

#### **Step 3: Verify Installation**

Check if the packages are installed:

bash

CopyEdit

`pip list`

You should see both `selenium` and `webdriver-manager` in the list.


