# Colossal.PSI.Common.Mod

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.PSI.Common.Mod>`  

## Code

```csharp
public sealed struct Mod : System.IEquatable<Colossal.PSI.Common.Mod>
{
    public System.Int32 id;
    public System.String displayName;
    public System.String author;
    public System.String thumbnailPath;
    public System.String path;
    public System.String version;
    public System.String[] tags;
    public System.Action onClick;
    public System.Action<System.Boolean> onEnable;

    public System.Boolean Equals(Colossal.PSI.Common.Mod other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Int32 id`  

```csharp
public System.Int32 id;
```

- `public System.String displayName`  

```csharp
public System.String displayName;
```

- `public System.String author`  

```csharp
public System.String author;
```

- `public System.String thumbnailPath`  

```csharp
public System.String thumbnailPath;
```

- `public System.String path`  

```csharp
public System.String path;
```

- `public System.String version`  

```csharp
public System.String version;
```

- `public System.String[] tags`  

```csharp
public System.String[] tags;
```

- `public System.Action onClick`  

```csharp
public System.Action onClick;
```

- `public System.Action<System.Boolean> onEnable`  

```csharp
public System.Action<System.Boolean> onEnable;
```


## Methods

- `public Equals(Colossal.PSI.Common.Mod other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.PSI.Common.Mod other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


