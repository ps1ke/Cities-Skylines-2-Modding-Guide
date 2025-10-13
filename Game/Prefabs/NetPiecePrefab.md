# Game.Prefabs.NetPiecePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RenderPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetPiecePrefab : Game.Prefabs.RenderPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NetPieceLayer m_Layer;
    public System.Single m_Width;
    public System.Single m_Length;
    public Colossal.Mathematics.Bounds1 m_HeightRange;
    public System.Single m_WidthOffset;
    public System.Single m_NodeOffset;
    public System.Single m_SideConnectionOffset;
    public Unity.Mathematics.float4 m_SurfaceHeights;

    public NetPiecePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NetPieceLayer m_Layer`  

```csharp
public Game.Prefabs.NetPieceLayer m_Layer;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_Length`  

```csharp
public System.Single m_Length;
```

- `public Colossal.Mathematics.Bounds1 m_HeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightRange;
```

- `public System.Single m_WidthOffset`  

```csharp
public System.Single m_WidthOffset;
```

- `public System.Single m_NodeOffset`  

```csharp
public System.Single m_NodeOffset;
```

- `public System.Single m_SideConnectionOffset`  

```csharp
public System.Single m_SideConnectionOffset;
```

- `public Unity.Mathematics.float4 m_SurfaceHeights`  

```csharp
public Unity.Mathematics.float4 m_SurfaceHeights;
```


## Constructors

- `public NetPiecePrefab()`  

```csharp
public NetPiecePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<NetPieceData>());
		components.Add(ComponentType.ReadWrite<MeshMaterial>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (!TryGet<LodProperties>(out var component) || component.m_LodMeshes == null)
		{
			return;
		}
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		for (int i = 0; i < component.m_LodMeshes.Length; i++)
		{
			Entity entity2 = orCreateSystemManaged.GetEntity(component.m_LodMeshes[i]);
			if (!entityManager.HasBuffer<MeshMaterial>(entity2))
			{
				entityManager.AddComponent<MeshMaterial>(entity2);
			}
		}
	}
```


