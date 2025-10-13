# Game.Prefabs.MovePieceVertices

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MovePieceVertices : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_LowerBottomToTerrain;
    public System.Boolean m_RaiseTopToTerrain;
    public System.Boolean m_SmoothTopNormal;

    public MovePieceVertices();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Boolean m_LowerBottomToTerrain`  

```csharp
public System.Boolean m_LowerBottomToTerrain;
```

- `public System.Boolean m_RaiseTopToTerrain`  

```csharp
public System.Boolean m_RaiseTopToTerrain;
```

- `public System.Boolean m_SmoothTopNormal`  

```csharp
public System.Boolean m_SmoothTopNormal;
```


## Constructors

- `public MovePieceVertices()`  

```csharp
public MovePieceVertices();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
	}
```


