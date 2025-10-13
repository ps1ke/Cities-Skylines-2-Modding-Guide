# Game.Prefabs.NetTerrainPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetTerrainPiece : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float2 m_WidthOffset;
    public Unity.Mathematics.float2 m_ClipHeightOffset;
    public Unity.Mathematics.float3 m_MinHeightOffset;
    public Unity.Mathematics.float3 m_MaxHeightOffset;

    public NetTerrainPiece();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Unity.Mathematics.float2 m_WidthOffset`  

```csharp
public Unity.Mathematics.float2 m_WidthOffset;
```

- `public Unity.Mathematics.float2 m_ClipHeightOffset`  

```csharp
public Unity.Mathematics.float2 m_ClipHeightOffset;
```

- `public Unity.Mathematics.float3 m_MinHeightOffset`  

```csharp
public Unity.Mathematics.float3 m_MinHeightOffset;
```

- `public Unity.Mathematics.float3 m_MaxHeightOffset`  

```csharp
public Unity.Mathematics.float3 m_MaxHeightOffset;
```


## Constructors

- `public NetTerrainPiece()`  

```csharp
public NetTerrainPiece();
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
		components.Add(ComponentType.ReadWrite<NetTerrainData>());
	}
```


