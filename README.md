# .NET SDK


## Installation

### NuGet

You can easily install the Zara 4 SDK for .NET applications using the [NuGet](https://www.nuget.org/) package manager. NuGet is maintained with the latest Zara 4 SDK and is the best we to stay up to date.

Run `Install-Package Zara4` from the NuGet package manager console to install the latest SDK. Alternatively install via the VS 
[Package Management](https://docs.nuget.org/consume/package-manager-dialog) window.


### Manual Install

Download and install `Zara4.dll` into your application. You must add a reference to the dll to import the Zara 4 SDK.


---


## VB

You must import the Zara 4 SDK into your application by copying the following lines into the top of your VB file.

```vb
Imports Zara4.API
Imports Zara4.API.ImageProcessing
```

### Example usage

```vb
Dim apiClient = new Client("API_CLIENT_ID", "API_CLIENT_SECRET")
Dim originalImage = New LocalImageRequest("/path/to/original-image.jpg")

'Change request options
originalImage.optimisationMode = OptimisationMode.HIGHEST

Dim processedImage = apiClient.processImage(originalImage)
apiClient.downloadProcessedImage(processedImage, "/where/to/save/compressed-image.jpg")
```


---


## C Sharp

You must import the Zara 4 SDK into your application by copying the following lines into the top of your C# file.

```cs
using Zara4.API;
using Zara4.API.ImageProcessing;
```

### Example usage

```cs
Client apiClient = new Client("API_CLIENT_ID", "API_CLIENT_SECRET");
LocalImageRequest originalImage = new LocalImageRequest("/path/to/original-image.jpg");

// Change request options
originalImage.optimisationMode = OptimisationMode.HIGHEST;
originalImage.outputFormat = OutputFormat.MATCH;
originalImage.colourEnhancement = ColourEnhancement.IMPROVE_COLOUR;
originalImage.resizeMode = ResizeMode.NONE;

ProcessedImage processedImage = apiClient.processImage(originalImage);
apiClient.downloadProcessedImage(processedImage, "/where/to/save/compressed-image.jpg");
```
