# Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey>`  

## Code

```csharp
public sealed struct NetKey : System.IEquatable<Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey>
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_StartLocation;
    public Unity.Mathematics.float3 m_EndLocation;

    public System.Boolean Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.float3 m_StartLocation`  

```csharp
public Unity.Mathematics.float3 m_StartLocation;
```

- `public Unity.Mathematics.float3 m_EndLocation`  

```csharp
public Unity.Mathematics.float3 m_EndLocation;
```


## Methods

- `public Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


