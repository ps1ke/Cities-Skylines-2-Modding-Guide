# Game.Rendering.ManagedBatchSystem+GroupKey+Batch

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Rendering.ManagedBatchSystem+GroupKey+Batch>`  

## Code

```csharp
public sealed struct Batch : System.IEquatable<Game.Rendering.ManagedBatchSystem+GroupKey+Batch>
{
    private UnityEngine.Material <loadedMaterial>k__BackingField;
    private Game.Rendering.BatchFlags <flags>k__BackingField;

    public UnityEngine.Material loadedMaterial { get; set; }
    public Game.Rendering.BatchFlags flags { get; set; }

    public Batch(Game.Rendering.CustomBatch batch);

    public System.Boolean Equals(Game.Rendering.ManagedBatchSystem+GroupKey+Batch other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private UnityEngine.Material <loadedMaterial>k__BackingField`  

```csharp
private UnityEngine.Material <loadedMaterial>k__BackingField;
```

- `private Game.Rendering.BatchFlags <flags>k__BackingField`  

```csharp
private Game.Rendering.BatchFlags <flags>k__BackingField;
```


## Properties

- `public UnityEngine.Material loadedMaterial { get; set }`  

```csharp
public UnityEngine.Material loadedMaterial { get; set; }
```

- `public Game.Rendering.BatchFlags flags { get; set }`  

```csharp
public Game.Rendering.BatchFlags flags { get; set; }
```


## Constructors

- `public Batch(Game.Rendering.CustomBatch batch)`  

```csharp
public Batch(Game.Rendering.CustomBatch batch);
```


## Methods

- `public Equals(Game.Rendering.ManagedBatchSystem+GroupKey+Batch other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Rendering.ManagedBatchSystem+GroupKey+Batch other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


