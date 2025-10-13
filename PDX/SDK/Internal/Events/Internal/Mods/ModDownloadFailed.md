# PDX.SDK.Internal.Events.Internal.Mods.ModDownloadFailed

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Internal.Mods`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Mods.IModDownloadFailed`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class ModDownloadFailed : PDX.SDK.Contracts.Events.Mods.IModDownloadFailed, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private System.Int32 <ModId>k__BackingField;

    public System.Guid EventId { get; set; }
    public System.Int32 ModId { get; set; }

    public ModDownloadFailed();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private System.Int32 <ModId>k__BackingField`  

```csharp
private System.Int32 <ModId>k__BackingField;
```


## Properties

- `public System.Guid EventId { get; set }`  

```csharp
public System.Guid EventId { get; set; }
```

- `public System.Int32 ModId { get; set }`  

```csharp
public System.Int32 ModId { get; set; }
```


## Constructors

- `public ModDownloadFailed()`  

```csharp
public ModDownloadFailed();
```


