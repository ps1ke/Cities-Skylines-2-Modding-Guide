# PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.UploadResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class UploadResult : PDX.SDK.Contracts.Result
{
    private System.String <Etag>k__BackingField;
    private System.String <Url>k__BackingField;

    public System.String Etag { get; set; }
    public System.String Url { get; set; }

    public UploadResult();

}
```


## Fields

- `private System.String <Etag>k__BackingField`  

```csharp
private System.String <Etag>k__BackingField;
```

- `private System.String <Url>k__BackingField`  

```csharp
private System.String <Url>k__BackingField;
```


## Properties

- `public System.String Etag { get; set }`  

```csharp
public System.String Etag { get; set; }
```

- `public System.String Url { get; set }`  

```csharp
public System.String Url { get; set; }
```


## Constructors

- `public UploadResult()`  

```csharp
public UploadResult();
```


