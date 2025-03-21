# Installing Adobe Experience Manager (AEM)

This document outlines the basic folder structure and steps for installing Adobe Experience Manager (AEM) in a development environment.

## Folder Structure

The following folder structure is recommended for organizing your AEM installation:

## Project Structure
```
aem/
├── Author/
│   └── aem-author-p4502.jar
├── Publish/
│   └── aem-publish-p4503.jar
└── codebase/
|   └── mytraining
```

# AEM Project Build and Deployment Instructions

This document outlines the steps to build and deploy an Adobe Experience Manager (AEM) project.

## Prerequisites

* Maven (mvn) installed
* Java Development Kit (JDK) installed
* AEM author and publish JAR files (e.g., `aem-author-p4502.jar`, `aem-publish-p4503.jar`)

## Project Setup

1.  **Download the project:**
    * Download the `mytraining.zip` file from [https://drive.google.com/file/d/1wF4lB945kYnnDrWOisoTI_OrIxOeOBAs/view?usp=sharing](https://drive.google.com/file/d/1wF4lB945kYnnDrWOisoTI_OrIxOeOBAs/view?usp=sharing).
    * Extract the contents of the zip file to your desired directory.
  
## AEM JAR Download

* Download the AEM JAR file from [https://drive.google.com/file/d/1PCOw2aH8XMUO9swRLywKJ3K2HVxNuQY-/view?usp=sharing](https://drive.google.com/file/d/1PCOw2aH8XMUO9swRLywKJ3K2HVxNuQY-/view?usp=sharing).
* Rename the file to **`aem-author-p4502.jar`** and place it in the **`Author/`** folder.
* Copy the same file to the **`Publish/`** folder and rename it to **`aem-publish-p4503.jar`**.


## Build and Deploy Commands

1.  **Build and Deploy to AEM Author (Port 4502):**

    ```bash
    mvn clean install -PautoInstallSinglePackage -Daem.port=4502 -DskipTests
    ```

    * `mvn clean install`: Cleans the project and builds the package.
    * `-PautoInstallSinglePackage`: Activates the profile to automatically install the package to AEM.
    * `-Daem.port=4502`: Specifies the AEM port for the author instance.
    * `-DskipTests`: Skips the unit tests during the build.

2.  **Build and Deploy to AEM Publish (Port 4503):**

    ```bash
    mvn clean install -PautoInstallSinglePackage -Daem.port=4503 -DskipTests
    ```

    * `mvn clean install`: Cleans the project and builds the package.
    * `-PautoInstallSinglePackage`: Activates the profile to automatically install the package to AEM.
    * `-Daem.port=4503`: Specifies the AEM port for the publish instance.
    * `-DskipTests`: Skips the unit tests during the build.

3.  **Standard Project Build (Without AEM Deployment):**

    ```bash
    mvn clean install -DskipTests
    ```

    * `mvn clean install`: Cleans the project and builds the package.
    * `-DskipTests`: Skips the unit tests during the build.
    * This command is for creating the package without deploying it directly to an AEM instance.

4.  **Start AEM Author Instance (Port 4502):**

    ```bash
    java -jar aem-author-p4502.jar
    ```

    * Starts the AEM author instance using the provided JAR file.

5.  **Start AEM Publish Instance (Port 4503):**

    ```bash
    java -jar aem-publish-p4503.jar
    ```

    * Starts the AEM publish instance using the provided JAR file.

