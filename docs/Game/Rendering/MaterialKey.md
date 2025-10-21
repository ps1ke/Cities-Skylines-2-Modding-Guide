# Game.Rendering.ManagedBatchSystem+MaterialKey

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Game.Rendering.ManagedBatchSystem+MaterialKey>`  

## Code

```csharp
public class MaterialKey : System.IEquatable<Game.Rendering.ManagedBatchSystem+MaterialKey>
{
    private UnityEngine.Shader <shader>k__BackingField;
    private UnityEngine.Material <template>k__BackingField;
    private System.Int32 <decalLayerMask>k__BackingField;
    private System.Int32 <renderQueue>k__BackingField;
    private System.Collections.Generic.HashSet<System.String> <keywords>k__BackingField;
    private System.Collections.Generic.List<System.Int32> <vtStacks>k__BackingField;
    private System.Collections.Generic.Dictionary<System.Int32, System.Object> <textures>k__BackingField;

    public UnityEngine.Shader shader { get; set; }
    public UnityEngine.Material template { get; set; }
    public System.Int32 decalLayerMask { get; set; }
    public System.Int32 renderQueue { get; set; }
    public System.Collections.Generic.HashSet<System.String> keywords { get; private set; }
    public System.Collections.Generic.List<System.Int32> vtStacks { get; private set; }
    public System.Collections.Generic.Dictionary<System.Int32, System.Object> textures { get; private set; }

    public MaterialKey();
    public MaterialKey(Game.Rendering.ManagedBatchSystem+MaterialKey source);

    public System.Void Clear();
    public System.Boolean Equals(Game.Rendering.ManagedBatchSystem+MaterialKey other);
    public virtual System.Int32 GetHashCode();
    public System.Void Initialize(Colossal.IO.AssetDatabase.SurfaceAsset surface);
    public System.Void Initialize(UnityEngine.Material material);
}
```


## Fields

- `private UnityEngine.Shader <shader>k__BackingField`  

```csharp
private UnityEngine.Shader <shader>k__BackingField;
```

- `private UnityEngine.Material <template>k__BackingField`  

```csharp
private UnityEngine.Material <template>k__BackingField;
```

- `private System.Int32 <decalLayerMask>k__BackingField`  

```csharp
private System.Int32 <decalLayerMask>k__BackingField;
```

- `private System.Int32 <renderQueue>k__BackingField`  

```csharp
private System.Int32 <renderQueue>k__BackingField;
```

- `private System.Collections.Generic.HashSet<System.String> <keywords>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<System.String> <keywords>k__BackingField;
```

- `private System.Collections.Generic.List<System.Int32> <vtStacks>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.Int32> <vtStacks>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Object> <textures>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Object> <textures>k__BackingField;
```


## Properties

- `public UnityEngine.Shader shader { get; set }`  

```csharp
public UnityEngine.Shader shader { get; set; }
```

- `public UnityEngine.Material template { get; set }`  

```csharp
public UnityEngine.Material template { get; set; }
```

- `public System.Int32 decalLayerMask { get; set }`  

```csharp
public System.Int32 decalLayerMask { get; set; }
```

- `public System.Int32 renderQueue { get; set }`  

```csharp
public System.Int32 renderQueue { get; set; }
```

- `public System.Collections.Generic.HashSet<System.String> keywords { get; private set }`  

```csharp
public System.Collections.Generic.HashSet<System.String> keywords { get; private set; }
```

- `public System.Collections.Generic.List<System.Int32> vtStacks { get; private set }`  

```csharp
public System.Collections.Generic.List<System.Int32> vtStacks { get; private set; }
```

- `public System.Collections.Generic.Dictionary<System.Int32, System.Object> textures { get; private set }`  

```csharp
public System.Collections.Generic.Dictionary<System.Int32, System.Object> textures { get; private set; }
```


## Constructors

- `public MaterialKey()`  

```csharp
public MaterialKey();
```

- `public MaterialKey(Game.Rendering.ManagedBatchSystem+MaterialKey source)`  

```csharp
public MaterialKey(Game.Rendering.ManagedBatchSystem+MaterialKey source);
```


## Methods

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Equals(Game.Rendering.ManagedBatchSystem+MaterialKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Rendering.ManagedBatchSystem+MaterialKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Initialize(Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  

```csharp
public System.Void Initialize(Colossal.IO.AssetDatabase.SurfaceAsset surface);
```

- `public Initialize(UnityEngine.Material material) : System.Void`  

```csharp
public System.Void Initialize(UnityEngine.Material material);
```


