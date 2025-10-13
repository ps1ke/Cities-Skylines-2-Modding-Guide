# PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Service.Mods.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Internal.Service.Mods.Models.IPlaysetModMetaData`  

## Code

```csharp
public class PlaysetSubscribedModMetaData : PDX.SDK.Internal.Service.Mods.Models.IPlaysetModMetaData
{
    private System.Int32 <Id>k__BackingField;
    private System.String <Version>k__BackingField;
    private System.Int32 <LoadOrder>k__BackingField;
    private System.Boolean <IsEnabled>k__BackingField;

    public System.Int32 Id { get; set; }
    public System.String Version { get; set; }
    public System.Int32 LoadOrder { get; set; }
    public System.Boolean IsEnabled { get; set; }

    public PlaysetSubscribedModMetaData();

    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private System.Int32 <Id>k__BackingField`  

```csharp
private System.Int32 <Id>k__BackingField;
```

- `private System.String <Version>k__BackingField`  

```csharp
private System.String <Version>k__BackingField;
```

- `private System.Int32 <LoadOrder>k__BackingField`  

```csharp
private System.Int32 <LoadOrder>k__BackingField;
```

- `private System.Boolean <IsEnabled>k__BackingField`  

```csharp
private System.Boolean <IsEnabled>k__BackingField;
```


## Properties

- `public System.Int32 Id { get; set }`  

```csharp
public System.Int32 Id { get; set; }
```

- `public System.String Version { get; set }`  

```csharp
public System.String Version { get; set; }
```

- `public System.Int32 LoadOrder { get; set }`  

```csharp
public System.Int32 LoadOrder { get; set; }
```

- `public System.Boolean IsEnabled { get; set }`  

```csharp
public System.Boolean IsEnabled { get; set; }
```


## Constructors

- `public PlaysetSubscribedModMetaData()`  

```csharp
public PlaysetSubscribedModMetaData();
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


