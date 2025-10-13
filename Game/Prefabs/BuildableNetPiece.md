# Game.Prefabs.BuildableNetPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildableNetPiece : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float3 m_Position;
    public System.Single m_Width;
    public Unity.Mathematics.float3 m_SnapPosition;
    public System.Single m_SnapWidth;
    public System.Boolean m_AllowOnBridge;

    public BuildableNetPiece();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public Unity.Mathematics.float3 m_SnapPosition`  

```csharp
public Unity.Mathematics.float3 m_SnapPosition;
```

- `public System.Single m_SnapWidth`  

```csharp
public System.Single m_SnapWidth;
```

- `public System.Boolean m_AllowOnBridge`  

```csharp
public System.Boolean m_AllowOnBridge;
```


## Constructors

- `public BuildableNetPiece()`  

```csharp
public BuildableNetPiece();
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
		components.Add(ComponentType.ReadWrite<NetPieceArea>());
	}
```


