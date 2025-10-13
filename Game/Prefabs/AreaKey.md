# Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey>`  

## Code

```csharp
public sealed struct AreaKey : System.IEquatable<Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey>
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_StartLocation;
    public System.Int32 m_NodeCount;

    public System.Boolean Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey other);
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

- `public System.Int32 m_NodeCount`  

```csharp
public System.Int32 m_NodeCount;
```


## Methods

- `public Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


