# Game.Effects.SourceInfo

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Effects.SourceInfo>`  

## Code

```csharp
public sealed struct SourceInfo : System.IEquatable<Game.Effects.SourceInfo>
{
    public Unity.Entities.Entity m_Entity;
    public System.Int32 m_EffectIndex;

    public SourceInfo(Unity.Entities.Entity entity, System.Int32 effectIndex);

    public System.Boolean Equals(Game.Effects.SourceInfo other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.Int32 m_EffectIndex`  

```csharp
public System.Int32 m_EffectIndex;
```


## Constructors

- `public SourceInfo(Unity.Entities.Entity entity, System.Int32 effectIndex)`  

```csharp
public SourceInfo(Unity.Entities.Entity entity, System.Int32 effectIndex);
```


## Methods

- `public Equals(Game.Effects.SourceInfo other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Effects.SourceInfo other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


