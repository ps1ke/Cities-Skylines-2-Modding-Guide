# Game.Prefabs.BuildingEfficiency

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingEfficiency : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public BuildingEfficiency();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Constructors

- `public BuildingEfficiency()`  

```csharp
public BuildingEfficiency();
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

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


