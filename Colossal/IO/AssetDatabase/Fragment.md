# Colossal.IO.AssetDatabase.SettingAsset+Fragment

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Colossal.IO.AssetDatabase.SettingAsset+Fragment>`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class Fragment : System.IEquatable<Colossal.IO.AssetDatabase.SettingAsset+Fragment>
{
    public Colossal.IO.AssetDatabase.SettingAsset asset;
    public Colossal.Hash128 guid;
    public Colossal.Json.Variant variant;
    public System.Object source;
    public System.Object default;

    public System.String name { get; }
    public Colossal.IO.AssetDatabase.SourceMeta meta { get; }

    public Fragment();

    public System.Boolean Equals(Colossal.IO.AssetDatabase.SettingAsset+Fragment other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Colossal.IO.AssetDatabase.SettingAsset asset`  

```csharp
public Colossal.IO.AssetDatabase.SettingAsset asset;
```

- `public Colossal.Hash128 guid`  

```csharp
public Colossal.Hash128 guid;
```

- `public Colossal.Json.Variant variant`  

```csharp
public Colossal.Json.Variant variant;
```

- `public System.Object source`  

```csharp
public System.Object source;
```

- `public System.Object default`  

```csharp
public System.Object default;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Colossal.IO.AssetDatabase.SourceMeta meta { get }`  

```csharp
public Colossal.IO.AssetDatabase.SourceMeta meta { get; }
```


## Constructors

- `public Fragment()`  

```csharp
public Fragment();
```


## Methods

- `public Equals(Colossal.IO.AssetDatabase.SettingAsset+Fragment other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.SettingAsset+Fragment other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


