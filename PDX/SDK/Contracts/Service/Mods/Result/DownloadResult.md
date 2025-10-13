# PDX.SDK.Contracts.Service.Mods.Result.DownloadResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class DownloadResult : PDX.SDK.Contracts.Result
{
    private System.String <ContentFileOrFolder>k__BackingField;
    private System.String <ThumbnailFilename>k__BackingField;
    private System.Collections.Generic.List<System.String> <ScreenshotsFilenames>k__BackingField;

    public System.String ContentFileOrFolder { get; set; }
    public System.String ThumbnailFilename { get; set; }
    public System.Collections.Generic.List<System.String> ScreenshotsFilenames { get; set; }

    public DownloadResult();

}
```


## Fields

- `private System.String <ContentFileOrFolder>k__BackingField`  

```csharp
private System.String <ContentFileOrFolder>k__BackingField;
```

- `private System.String <ThumbnailFilename>k__BackingField`  

```csharp
private System.String <ThumbnailFilename>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <ScreenshotsFilenames>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <ScreenshotsFilenames>k__BackingField;
```


## Properties

- `public System.String ContentFileOrFolder { get; set }`  

```csharp
public System.String ContentFileOrFolder { get; set; }
```

- `public System.String ThumbnailFilename { get; set }`  

```csharp
public System.String ThumbnailFilename { get; set; }
```

- `public System.Collections.Generic.List<System.String> ScreenshotsFilenames { get; set }`  

```csharp
public System.Collections.Generic.List<System.String> ScreenshotsFilenames { get; set; }
```


## Constructors

- `public DownloadResult()`  

```csharp
public DownloadResult();
```


