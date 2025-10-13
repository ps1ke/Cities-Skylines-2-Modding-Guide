# Game.Prefabs.Effects.EffectColor

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EffectColor : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EffectColorSource m_Source;
    public System.Single m_HueRandomness;
    public System.Single m_SaturationRandomness;
    public System.Single m_BrightnessRandomness;

    public EffectColor();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EffectColorSource m_Source`  

```csharp
public Game.Prefabs.EffectColorSource m_Source;
```

- `public System.Single m_HueRandomness`  

```csharp
public System.Single m_HueRandomness;
```

- `public System.Single m_SaturationRandomness`  

```csharp
public System.Single m_SaturationRandomness;
```

- `public System.Single m_BrightnessRandomness`  

```csharp
public System.Single m_BrightnessRandomness;
```


## Constructors

- `public EffectColor()`  

```csharp
public EffectColor();
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


