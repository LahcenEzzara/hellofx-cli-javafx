# HelloFX-CLI-JavaFX

A simple JavaFX application demonstrating how to compile and run a JavaFX project using the JavaFX SDK from the command line.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Java Development Kit (JDK)**: Version 17 or higher.
- **JavaFX SDK**: Download the appropriate JavaFX SDK for your operating system from [Gluon's website](https://gluonhq.com/products/javafx/).
- **PowerShell**: Version 7.5.0 or higher (or any terminal/command prompt).

## Setup

1. **Download and Extract JavaFX SDK**:
   - Download the JavaFX SDK from [Gluon's website](https://gluonhq.com/products/javafx/).
   - Extract the SDK to a desired location on your system. For example:

```powershell
C:\javafx-sdk-17.0.14
```

2. **Set Environment Variable**:
   - Set an environment variable `PATH_TO_FX` pointing to the `lib` directory of the JavaFX SDK. In PowerShell, run:

```powershell
$env:PATH_TO_FX = "C:\javafx-sdk-17.0.14\lib"
```
   - This variable will be used to specify the module path when compiling and running the JavaFX application.

## Compile and Run the Application

### Compile the Application

To compile the `HelloFX.java` file, use the following command:

```powershell
javac --module-path $env:PATH_TO_FX --add-modules javafx.controls HelloFX.java
```

- **`--module-path`**: Specifies the path to the JavaFX SDK's `lib` directory.
- **`--add-modules`**: Adds the required JavaFX modules. In this case, `javafx.controls` is sufficient for basic applications. If your application uses FXML, you will need to add `javafx.fxml` as well:

```powershell
javac --module-path $env:PATH_TO_FX --add-modules javafx.controls,javafx.fxml HelloFX.java
```

### Run the Application

After compiling, run the application using:

```powershell
java --module-path $env:PATH_TO_FX --add-modules javafx.controls HelloFX
```

- This command runs the compiled `HelloFX` class with the JavaFX runtime.


## Troubleshooting

### Common Issues

1. **Java Version Mismatch**:
   - Ensure that the JDK version matches the JavaFX SDK version. For example, if you are using JavaFX 17, make sure you have JDK 17 installed.

2. **Module Not Found**:
   - If you encounter errors like `module not found`, ensure that the `--add-modules` flag includes all necessary modules (e.g., `javafx.controls`, `javafx.fxml`).

3. **Environment Variable Not Set**:
   - If the `PATH_TO_FX` environment variable is not set correctly, the compilation or runtime will fail. Double-check the path and ensure it points to the `lib` directory of the JavaFX SDK.

4. **Class Not Found**:
   - Ensure that the `HelloFX.class` file is in the same directory as your command prompt or PowerShell session, or specify the correct path to the class file.

## Additional Resources

- [JavaFX Documentation](https://openjfx.io/)
- [Gluon JavaFX SDK Downloads](https://gluonhq.com/products/javafx/)
- [JavaFX GitHub Samples](https://github.com/openjfx/samples)

## License

This project is open-source and available under the [MIT License](LICENSE).
