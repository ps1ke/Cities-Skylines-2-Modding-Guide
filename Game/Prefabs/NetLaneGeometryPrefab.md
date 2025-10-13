# Game.Prefabs.NetLaneGeometryPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.NetLanePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetLaneGeometryPrefab : Game.Prefabs.NetLanePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NetLaneMeshInfo[] m_Meshes;

    public NetLaneGeometryPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.NetLaneMeshInfo[] m_Meshes`  

```csharp
public Game.Prefabs.NetLaneMeshInfo[] m_Meshes;
```


## Constructors

- `public NetLaneGeometryPrefab()`  

```csharp
public NetLaneGeometryPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		if (components.Contains(ComponentType.ReadWrite<MasterLane>()))
		{
			return;
		}
		components.Add(ComponentType.ReadWrite<LaneGeometry>());
		components.Add(ComponentType.ReadWrite<CullingInfo>());
		components.Add(ComponentType.ReadWrite<MeshBatch>());
		bool flag = false;
		if (m_Meshes != null)
		{
			for (int i = 0; i < m_Meshes.Length; i++)
			{
				RenderPrefab mesh = m_Meshes[i].m_Mesh;
				flag |= mesh.Has<ColorProperties>();
			}
		}
		if (flag)
		{
			components.Add(ComponentType.ReadWrite<PseudoRandomSeed>());
			components.Add(ComponentType.ReadWrite<MeshColor>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_Meshes.Length; i++)
		{
			prefabs.Add(m_Meshes[i].m_Mesh);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<NetLaneGeometryData>());
		components.Add(ComponentType.ReadWrite<SubMesh>());
	}
```


