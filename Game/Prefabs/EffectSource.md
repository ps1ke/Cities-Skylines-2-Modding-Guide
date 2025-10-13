# Game.Prefabs.EffectSource

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EffectSource : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects;
    public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves;

    public EffectSource();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects;
```

- `public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves;
```


## Constructors

- `public EffectSource()`  

```csharp
public EffectSource();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


## Nested types

- `Game.Prefabs.EffectSource+EffectSettings`  
- `Game.Prefabs.EffectSource+AnimationProperties`  

