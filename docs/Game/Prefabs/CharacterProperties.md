# Game.Prefabs.CharacterProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CharacterProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts;
    public System.String m_CorrectiveAnimationName;
    public System.String m_AnimatedPropName;
    public Game.Prefabs.CharacterOverlay[] m_Overlays;

    public CharacterProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts`  

```csharp
public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts;
```

- `public System.String m_CorrectiveAnimationName`  

```csharp
public System.String m_CorrectiveAnimationName;
```

- `public System.String m_AnimatedPropName`  

```csharp
public System.String m_AnimatedPropName;
```

- `public Game.Prefabs.CharacterOverlay[] m_Overlays`  

```csharp
public Game.Prefabs.CharacterOverlay[] m_Overlays;
```


## Constructors

- `public CharacterProperties()`  

```csharp
public CharacterProperties();
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

- `Game.Prefabs.CharacterProperties+BodyPart`  

