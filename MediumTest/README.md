# MediumTest - Building R from a Specific Subversion Revision in the R Dev Container  

## 🚀 Creating a Bash Script for Building R from Subversion  

### Open the R Dev Container  

1. **Start the Dev Container in GitHub Codespaces.**  
2. **Open a Bash terminal inside VS Code.**  

### Write the Bash Script  

- Create a script that takes the R Subversion revision number as input and downloads the required version.  
- Make the script executable using:  
  ```bash
  chmod +x build_r.sh
  ```
- Build R from revision **86123** with:  
  ```bash
  ./build_r.sh 86123
  ```  

## 🛠️ Bash Script for Building R from a Specific Subversion Revision  

```bash
if [ -z "$1" ]; then
  echo "Error: Missing revision number."
  echo "Usage: $0 <revision-number>"
  exit 1
fi

REVISION=$1
echo "Fetching and building R from Subversion revision: $REVISION"


echo "Checking for Subversion..."
if ! command -v svn &> /dev/null; then
  echo "Subversion not found. Installing..."
  sudo apt-get update && sudo apt-get install -y subversion
else
  echo "Subversion is already installed."
fi


echo "Downloading R source code from revision $REVISION..."
svn checkout -r "$REVISION" https://svn.r-project.org/R/trunk R-devel || { echo "Failed to checkout code"; exit 1; }


cd R-devel || { echo "Error: Could not enter R-devel directory"; exit 1; }
echo "Configuring build..."
./configure --enable-R-shlib

echo "Compiling R... This might take some time."
make

echo "Build complete! R is now compiled from revision $REVISION."

```

## ✅ Test Output  

Here is the screenshot of the R session required for the Medium Test:  

**Script**

![image](https://github.com/user-attachments/assets/e71110da-8707-4435-ba98-91881fdd3b69)

**Shell Running**

![03 medium](https://github.com/user-attachments/assets/bed9634c-7b81-4713-b4a6-b05c813fbaa0)

![04 medium](https://github.com/user-attachments/assets/f86383a3-f00a-4756-b7cf-f218cf2053c1)

![05 medium](https://github.com/user-attachments/assets/1454b5b7-06ba-42d8-901c-fd897e21b974)

![WhatsApp Image 2025-03-24 at 15 40 44_40a1bdd9](https://github.com/user-attachments/assets/f03beca2-2abe-4f61-acf9-e3734d342631)





