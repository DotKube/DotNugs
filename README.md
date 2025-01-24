# DotNugs

**DotNugs** is a simple .NET Core console application that allows you to search for NuGet packages from the command line. It uses the NuGet API to search for packages and display results in a table format.

This is a fork of [Nugs](https://github.com/loic-sharma/nugs) by Loic Sharma.  
The only change in this fork is updating the project to **.NET 8**.

---

## NuGet Package

This project has not been uploaded to NuGet yet but may be in the near future.

---

## Use of Bagetter

This project uses [Bagetter](https://www.bagetter.com/) as a local NuGet feed for testing.  
**Bagetter** is a simple local NuGet feed that allows you to:

- **Publish** packages locally for testing.
- **Pull** packages as a pull-through cache, reducing reliance on the NuGet API.

Think of it as a caching Docker repository for NuGet packages.

---

## Use of Taskfile

This project uses [Taskfile](https://taskfile.dev/) to manage tasks.  
To view the list of available tasks, run:

```bash
task --list
```

---

## Quick Start

### Run the Application

To run the application:

```bash
task run
```

<p align="center"><img src="https://user-images.githubusercontent.com/737941/82861979-43bd7800-9ed3-11ea-8be0-cd457e551132.gif" width="655" /></p>



### Publish the NuGet Package to Bagetter

Run the following tasks in order:

```bash
task create-nuget-feed
task pack
task publish-nuget-package

# Open your browser and navigate to http://localhost:5000
```

### Test the Pull-Through Cache

1. First, publish the package to Bagetter using the steps above.
2. Then, run the following tasks:

```bash
task add-nuget-source        # Add Bagetter as a NuGet source.
task pull-nugget-package     # Pull the package from Bagetter (e.g., Newtonsoft.Json).
task remove-nuget-package    # Remove the package from the .csproj file.
task remove-nuget-source     # Remove Bagetter as a NuGet source.
```
