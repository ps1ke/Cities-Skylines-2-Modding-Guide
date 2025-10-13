# Game.Tools.OwnerDefinition

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Tools.OwnerDefinition>`  

## Code

```csharp
public sealed struct OwnerDefinition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Tools.OwnerDefinition>
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;

    public System.Boolean Equals(Game.Tools.OwnerDefinition other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```


## Methods

- `public Equals(Game.Tools.OwnerDefinition other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Tools.OwnerDefinition other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


