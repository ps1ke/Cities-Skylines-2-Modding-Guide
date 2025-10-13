# Colossal.IO.AssetDatabase.AssetChangedEventArgs

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IEventArguments`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct AssetChangedEventArgs : Colossal.IEventArguments
{
    private readonly Colossal.IO.AssetDatabase.IAssetDatabase <database>k__BackingField;
    private readonly Colossal.IO.AssetDatabase.ChangeType <change>k__BackingField;
    private readonly Colossal.IO.AssetDatabase.IAssetData <asset>k__BackingField;

    public static Colossal.IO.AssetDatabase.AssetChangedEventArgs Default { get; }
    public Colossal.IO.AssetDatabase.IAssetDatabase database { get; }
    public Colossal.IO.AssetDatabase.ChangeType change { get; }
    public Colossal.IO.AssetDatabase.IAssetData asset { get; }

    public AssetChangedEventArgs(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ChangeType change);

    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private readonly Colossal.IO.AssetDatabase.IAssetDatabase <database>k__BackingField`  

```csharp
private readonly Colossal.IO.AssetDatabase.IAssetDatabase <database>k__BackingField;
```

- `private readonly Colossal.IO.AssetDatabase.ChangeType <change>k__BackingField`  

```csharp
private readonly Colossal.IO.AssetDatabase.ChangeType <change>k__BackingField;
```

- `private readonly Colossal.IO.AssetDatabase.IAssetData <asset>k__BackingField`  

```csharp
private readonly Colossal.IO.AssetDatabase.IAssetData <asset>k__BackingField;
```


## Properties

- `public static Colossal.IO.AssetDatabase.AssetChangedEventArgs Default { get }`  

```csharp
public static Colossal.IO.AssetDatabase.AssetChangedEventArgs Default { get; }
```

- `public Colossal.IO.AssetDatabase.IAssetDatabase database { get }`  

```csharp
public Colossal.IO.AssetDatabase.IAssetDatabase database { get; }
```

- `public Colossal.IO.AssetDatabase.ChangeType change { get }`  

```csharp
public Colossal.IO.AssetDatabase.ChangeType change { get; }
```

- `public Colossal.IO.AssetDatabase.IAssetData asset { get }`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData asset { get; }
```


## Constructors

- `public AssetChangedEventArgs(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ChangeType change)`  

```csharp
public AssetChangedEventArgs(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ChangeType change);
```


## Methods

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


