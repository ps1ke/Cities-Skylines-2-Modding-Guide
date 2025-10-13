# PDX.SDK.Contracts.Service.Profile.Result.GetProfileResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Profile.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class GetProfileResult : PDX.SDK.Contracts.Result
{
    private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Social>k__BackingField;
    private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Game>k__BackingField;

    public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Social { get; set; }
    public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Game { get; set; }

    public GetProfileResult();

}
```


## Fields

- `private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Social>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Social>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Game>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Profile.Models.UserProfile <Game>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Social { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Social { get; set; }
```

- `public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Game { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Profile.Models.UserProfile Game { get; set; }
```


## Constructors

- `public GetProfileResult()`  

```csharp
public GetProfileResult();
```


