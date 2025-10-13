# PDX.SDK.Internal.Events.Mods.ModSyncStatusChanged

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Mods`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Mods.IModSyncStatusChanged`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class ModSyncStatusChanged : PDX.SDK.Contracts.Events.Mods.IModSyncStatusChanged, PDX.SDK.Contracts.Events.IEventBase
{
    private readonly System.Guid <EventId>k__BackingField;
    private System.Boolean <IsSyncOngoing>k__BackingField;

    public System.Guid EventId { get; }
    public System.Boolean IsSyncOngoing { get; set; }

    public ModSyncStatusChanged();

}
```


## Fields

- `private readonly System.Guid <EventId>k__BackingField`  

```csharp
private readonly System.Guid <EventId>k__BackingField;
```

- `private System.Boolean <IsSyncOngoing>k__BackingField`  

```csharp
private System.Boolean <IsSyncOngoing>k__BackingField;
```


## Properties

- `public System.Guid EventId { get }`  

```csharp
public System.Guid EventId { get; }
```

- `public System.Boolean IsSyncOngoing { get; set }`  

```csharp
public System.Boolean IsSyncOngoing { get; set; }
```


## Constructors

- `public ModSyncStatusChanged()`  

```csharp
public ModSyncStatusChanged();
```


