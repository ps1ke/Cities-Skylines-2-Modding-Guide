# PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.DownloadResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class DownloadResult : PDX.SDK.Contracts.Result
{
    private System.Int32 <Size>k__BackingField;
    private System.String <Etag>k__BackingField;
    private System.String <RelativePath>k__BackingField;

    public System.Int32 Size { get; set; }
    public System.String Etag { get; set; }
    public System.String RelativePath { get; set; }

    public DownloadResult();

}
```


## Fields

- `private System.Int32 <Size>k__BackingField`  

```csharp
private System.Int32 <Size>k__BackingField;
```

- `private System.String <Etag>k__BackingField`  

```csharp
private System.String <Etag>k__BackingField;
```

- `private System.String <RelativePath>k__BackingField`  

```csharp
private System.String <RelativePath>k__BackingField;
```


## Properties

- `public System.Int32 Size { get; set }`  

```csharp
public System.Int32 Size { get; set; }
```

- `public System.String Etag { get; set }`  

```csharp
public System.String Etag { get; set; }
```

- `public System.String RelativePath { get; set }`  

```csharp
public System.String RelativePath { get; set; }
```


## Constructors

- `public DownloadResult()`  

```csharp
public DownloadResult();
```


