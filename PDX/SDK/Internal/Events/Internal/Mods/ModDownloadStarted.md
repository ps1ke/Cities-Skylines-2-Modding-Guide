# PDX.SDK.Internal.Events.Internal.Mods.ModDownloadStarted

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Internal.Mods`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Mods.IModDownloadStarted`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class ModDownloadStarted : PDX.SDK.Contracts.Events.Mods.IModDownloadStarted, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private System.Int32 <ModId>k__BackingField;

    public System.Guid EventId { get; set; }
    public System.Int32 ModId { get; set; }

    public ModDownloadStarted();

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

- `public ModDownloadStarted()`  

```csharp
public ModDownloadStarted();
```


