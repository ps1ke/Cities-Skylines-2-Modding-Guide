# PDX.SDK.Internal.Events.Internal.Mods.ModUnsubscribed

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Internal.Mods`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Mods.IModUnsubscribed`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class ModUnsubscribed : PDX.SDK.Contracts.Events.Mods.IModUnsubscribed, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private System.Int32 <ManagedModId>k__BackingField;
    private System.String <UnmanagedOrWipModName>k__BackingField;

    public System.Guid EventId { get; set; }
    public System.Int32 ManagedModId { get; set; }
    public System.String UnmanagedOrWipModName { get; set; }

    public ModUnsubscribed();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private System.Int32 <ManagedModId>k__BackingField`  

```csharp
private System.Int32 <ManagedModId>k__BackingField;
```

- `private System.String <UnmanagedOrWipModName>k__BackingField`  

```csharp
private System.String <UnmanagedOrWipModName>k__BackingField;
```


## Properties

- `public System.Guid EventId { get; set }`  

```csharp
public System.Guid EventId { get; set; }
```

- `public System.Int32 ManagedModId { get; set }`  

```csharp
public System.Int32 ManagedModId { get; set; }
```

- `public System.String UnmanagedOrWipModName { get; set }`  

```csharp
public System.String UnmanagedOrWipModName { get; set; }
```


## Constructors

- `public ModUnsubscribed()`  

```csharp
public ModUnsubscribed();
```


