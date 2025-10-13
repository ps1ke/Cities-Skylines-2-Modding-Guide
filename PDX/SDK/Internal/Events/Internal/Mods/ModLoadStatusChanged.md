# PDX.SDK.Internal.Events.Internal.Mods.ModLoadStatusChanged

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Internal.Mods`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class ModLoadStatusChanged : PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private System.Boolean <IsActivePlaysetUpdated>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.IMod <NewModToLoad>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.IMod <ModToUnload>k__BackingField;

    public System.Guid EventId { get; set; }
    public System.Boolean IsActivePlaysetUpdated { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get; set; }

    public ModLoadStatusChanged();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private System.Boolean <IsActivePlaysetUpdated>k__BackingField`  

```csharp
private System.Boolean <IsActivePlaysetUpdated>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.IMod <NewModToLoad>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.IMod <NewModToLoad>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.IMod <ModToUnload>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.IMod <ModToUnload>k__BackingField;
```


## Properties

- `public System.Guid EventId { get; set }`  

```csharp
public System.Guid EventId { get; set; }
```

- `public System.Boolean IsActivePlaysetUpdated { get; set }`  

```csharp
public System.Boolean IsActivePlaysetUpdated { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.IMod NewModToLoad { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.IMod ModToUnload { get; set; }
```


## Constructors

- `public ModLoadStatusChanged()`  

```csharp
public ModLoadStatusChanged();
```


