# PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Mods.Result.PublishResult`  

**Attributes:** `Preserve`  

## Code

```csharp
public class PublishUpdateResult : PDX.SDK.Contracts.Service.Mods.Result.PublishResult
{
    private System.Nullable<System.Int32> <ModVersion>k__BackingField;
    private System.String <UserModVersion>k__BackingField;

    public System.Nullable<System.Int32> ModVersion { get; set; }
    public System.String UserModVersion { get; set; }

    public PublishUpdateResult();

}
```


## Fields

- `private System.Nullable<System.Int32> <ModVersion>k__BackingField`  

```csharp
private System.Nullable<System.Int32> <ModVersion>k__BackingField;
```

- `private System.String <UserModVersion>k__BackingField`  

```csharp
private System.String <UserModVersion>k__BackingField;
```


## Properties

- `public System.Nullable<System.Int32> ModVersion { get; set }`  

```csharp
public System.Nullable<System.Int32> ModVersion { get; set; }
```

- `public System.String UserModVersion { get; set }`  

```csharp
public System.String UserModVersion { get; set; }
```


## Constructors

- `public PublishUpdateResult()`  

```csharp
public PublishUpdateResult();
```


