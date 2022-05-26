## 1. Installing WSL

1. Open PowerShell as Administrator and run:
    ```powershell
    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
    ```

2. If you are prompted to restart your computer, do so.

3. Next, you'll need to download and install Ubuntu 20.04 LTS via the Windows Store linked [here](https://www.microsoft.com/en-au/p/ubuntu-2004-lts/9n6svws3rx71?activetab=pivot:overviewtab).  

## 2. Installing and Activating WSL2
1. Open PowerShell as Administrator and run:
    ```powershell
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

    Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart
    # alternative command to above:
    # dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```

2. Restart your PC.

3. Download and install the WSL2 Kernel Update linked [here](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) as administrator.

4. Launch your Ubuntu terminal by either typing in `wsl` into powershell or directly using the Ubuntu app.

5. You will be prompted to create a new user account. If it helps, use your UniMelb username and password for easy remembering.

6. Now, you need to set WSL2 as default. Open up powershell as administrator and run:
    ```powershell
    wsl --set-default-version 2
    ```

7. Verify your Ubuntu 20.04 LTS has `VERSION 2` by using the command:
    ```powershell
    # -l is short for --list and -v is short for --verbose
    wsl -l -v
    ```
    - If Ubuntu 20.04 LTS is `VERSION 1`, you need to update it by running `wsl --set-version Ubuntu-20.04 2`

8. Congratulations, you have now installed WSL2!

## 3. Installing Packages
1. ```powershell
   sudo apt update && sudo apt -y upgrade
   ```    
2. ```powershell
   sudo apt install python3-pip jupyter-core -y && pip3 install pandas numpy scipy scikit-learn matplotlib seaborn folium notebook pyarrow
   ```
Try to starting a jupyter notebook `jupyter notebook`.  If you encounter "ImportError: cannot import name 'soft_unicode' from 'markupsafe'" then install marksafe `pip install MarkupSafe`. try it again.  If the issue is unresolved downgrade to the stable version `pip install markupsafe==2.0.1`. If there is an issue with the connection run this `echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null` to connect to google's DNS then you should be able to.

3. ```powershell
   pip3 install seaborn folium jupyterlab pyarrow
   ```
4. ```powershell
   cd /mnt/d/'Program Files'/GitHub/
   jupyter-lab
   ```
5. Install spark
   ```powershell
   # install java
   sudo apt install openjdk-8-jdk -y
   # add to path
   echo 'JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"' | sudo tee -a /etc/environment
   # apply to environment
   source /etc/environment
   # install spark
   pip3 install pyspark
   ```
   
## 4. Connecting WSL to VS Code
1. Intall Remote - WSL in VS Code linked [here](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl).
2. Follow "Getting started" instructions.

* Backup guide linked [here](https://code.visualstudio.com/docs/remote/wsl-tutorial).

## 5. Installing R
1. Install R if not already installed linked [here](https://cran.r-project.org/bin/windows/base/).
2. Install [RStudio](https://www.rstudio.com/products/rstudio/download/#download).
3. Install tinytex _**in R**_
   ```r
   install.packages('tinytex')
   tinytex::install_tinytex()
   # to uninstall TinyTeX, run tinytex::uninstall_tinytex()
   ```
4. Updating R: 
   ```r
   install.packages("installr")
   library(installr)
   updateR()
   ```
