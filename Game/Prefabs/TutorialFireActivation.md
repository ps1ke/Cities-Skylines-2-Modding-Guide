# Game.Prefabs.TutorialFireActivation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialActivation`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialFireActivation : Game.Prefabs.TutorialActivation, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TutorialFireActivation+FireActivationTarget m_Target;

    public TutorialFireActivation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.TutorialFireActivation+FireActivationTarget m_Target`  

```csharp
public Game.Prefabs.TutorialFireActivation+FireActivationTarget m_Target;
```


## Constructors

- `public TutorialFireActivation()`  

```csharp
public TutorialFireActivation();
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


## Nested types

- `Game.Prefabs.TutorialFireActivation+FireActivationTarget`  

