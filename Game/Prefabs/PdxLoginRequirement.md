# Game.Prefabs.PdxLoginRequirement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ContentRequirementBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PdxLoginRequirement : Game.Prefabs.ContentRequirementBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public PdxLoginRequirement();

    public virtual System.Boolean CheckRequirement();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.String GetDebugString();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Constructors

- `public PdxLoginRequirement()`  

```csharp
public PdxLoginRequirement();
```


## Methods

- `public virtual CheckRequirement() : System.Boolean`  

```csharp
public virtual System.Boolean CheckRequirement();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDebugString() : System.String`  

```csharp
public virtual System.String GetDebugString();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


