# PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events.Mods`  

**Type:** interface abstract public  

**Implements:** `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public abstract interface IModLoadStatusChanged : PDX.SDK.Contracts.Events.IEventBase
{
    public System.Boolean IsActivePlaysetUpdated { get; }
    public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get; }
    public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get; }

}
```


## Properties

- `public System.Boolean IsActivePlaysetUpdated { get }`  

```csharp
public System.Boolean IsActivePlaysetUpdated { get; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get; }
```


