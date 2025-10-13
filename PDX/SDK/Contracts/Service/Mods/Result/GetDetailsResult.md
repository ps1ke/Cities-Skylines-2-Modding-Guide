# PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class GetDetailsResult : PDX.SDK.Contracts.Result
{
    private PDX.SDK.Contracts.Service.Mods.Models.ModDetails <Mod>k__BackingField;

    public PDX.SDK.Contracts.Service.Mods.Models.ModDetails Mod { get; set; }

    public GetDetailsResult();

}
```


## Fields

- `private PDX.SDK.Contracts.Service.Mods.Models.ModDetails <Mod>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.ModDetails <Mod>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Service.Mods.Models.ModDetails Mod { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.ModDetails Mod { get; set; }
```


## Constructors

- `public GetDetailsResult()`  

```csharp
public GetDetailsResult();
```


