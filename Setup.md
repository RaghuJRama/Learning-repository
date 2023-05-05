# JAVA development Setup for Cloud Foundry

### Install JDK for SapMachine 11

- Browse [https://sap.github.io/SapMachine/](https://sap.github.io/SapMachine/).
- In first dropdown, Select **Sap Machine 11 (Long Term Support)**.
- Click on **Download** button.
- Run sapmachine-jdk-11.*.**_windows-x64_bin.msi file to install JDK for SapMachine.
    - In **Custom Setup** prompt, select **Add to PATH** and **Set JAVA_HOME**.
- Verify
    - System variable JAVA_HOME is set it to the root directory of the extracted archive (e.g. C:\<...>\sapmachine-jdk-11.0.3)
    - System variable PATH is added %JAVA_HOME%\bin to the PATH variable separated from the previous path by a semicolon.