# PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IPlaysetMod
{
    public System.Boolean IsEnabled { get; set; }
    public System.String DisplayName { get; set; }
    public System.Int32 LoadOrder { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }

}
```


## Properties

- `public System.Boolean IsEnabled { get; set }`  

```csharp
public System.Boolean IsEnabled { get; set; }
```

- `public System.String DisplayName { get; set }`  

```csharp
public System.String DisplayName { get; set; }
```

- `public System.Int32 LoadOrder { get; set }`  

```csharp
public System.Int32 LoadOrder { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
```


