# Game.Prefabs.TerrainArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TerrainArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_HeightOffset;
    public System.Single m_SlopeWidth;
    public System.Single m_NoiseScale;
    public System.Single m_NoiseFactor;
    public System.Boolean m_AbsoluteHeight;

    public TerrainArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_HeightOffset`  

```csharp
public System.Single m_HeightOffset;
```

- `public System.Single m_SlopeWidth`  

```csharp
public System.Single m_SlopeWidth;
```

- `public System.Single m_NoiseScale`  

```csharp
public System.Single m_NoiseScale;
```

- `public System.Single m_NoiseFactor`  

```csharp
public System.Single m_NoiseFactor;
```

- `public System.Boolean m_AbsoluteHeight`  

```csharp
public System.Boolean m_AbsoluteHeight;
```


## Constructors

- `public TerrainArea()`  

```csharp
public TerrainArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


