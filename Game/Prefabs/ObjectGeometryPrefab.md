# Game.Prefabs.ObjectGeometryPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class ObjectGeometryPrefab : Game.Prefabs.ObjectPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ObjectMeshInfo[] m_Meshes;
    public System.Boolean m_Circular;

    protected ObjectGeometryPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.ObjectMeshInfo[] m_Meshes`  

```csharp
public Game.Prefabs.ObjectMeshInfo[] m_Meshes;
```

- `public System.Boolean m_Circular`  

```csharp
public System.Boolean m_Circular;
```


## Constructors

- `protected ObjectGeometryPrefab()`  

```csharp
protected ObjectGeometryPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<ObjectGeometry>());
		components.Add(ComponentType.ReadWrite<CullingInfo>());
		components.Add(ComponentType.ReadWrite<MeshBatch>());
		components.Add(ComponentType.ReadWrite<PseudoRandomSeed>());
		bool flag = false;
		bool flag2 = false;
		bool flag3 = false;
		bool flag4 = false;
		bool flag5 = false;
		bool flag6 = false;
		bool flag7 = false;
		if (m_Meshes != null)
		{
			for (int i = 0; i < m_Meshes.Length; i++)
			{
				RenderPrefabBase mesh = m_Meshes[i].m_Mesh;
				if (mesh == null)
				{
					continue;
				}
				flag |= mesh.Has<ColorProperties>();
				flag2 |= mesh.Has<StackProperties>();
				flag3 |= mesh.Has<AnimationProperties>();
				flag7 = flag7 || mesh is CharacterGroup;
				ProceduralAnimationProperties component = mesh.GetComponent<ProceduralAnimationProperties>();
				if (component != null)
				{
					flag4 = true;
					if (component.m_Bones != null)
					{
						for (int j = 0; j < component.m_Bones.Length; j++)
						{
							switch (component.m_Bones[j].m_Type)
							{
							case BoneType.LookAtDirection:
							case BoneType.WindTurbineRotation:
							case BoneType.WindSpeedRotation:
							case BoneType.PoweredRotation:
							case BoneType.TrafficBarrierDirection:
							case BoneType.LookAtRotation:
							case BoneType.LookAtAim:
							case BoneType.LengthwiseLookAtRotation:
							case BoneType.WorkingRotation:
							case BoneType.OperatingRotation:
							case BoneType.LookAtMovementX:
							case BoneType.LookAtMovementY:
							case BoneType.LookAtMovementZ:
							case BoneType.LookAtRotationSide:
							case BoneType.LookAtAimForward:
								flag5 = true;
								break;
							}
						}
					}
				}
				if (mesh.GetComponent<EmissiveProperties>() != null)
				{
					flag6 = true;
				}
			}
		}
		if (flag || flag7)
		{
			components.Add(ComponentType.ReadWrite<MeshColor>());
		}
		if (flag2)
		{
			components.Add(ComponentType.ReadWrite<Stack>());
		}
		if (flag3)
		{
			components.Add(ComponentType.ReadWrite<Animated>());
		}
		if (flag4)
		{
			components.Add(ComponentType.ReadWrite<Skeleton>());
			components.Add(ComponentType.ReadWrite<Bone>());
			components.Add(ComponentType.ReadWrite<BoneHistory>());
			if (flag5)
			{
				components.Add(ComponentType.ReadWrite<Momentum>());
			}
		}
		if (flag6)
		{
			components.Add(ComponentType.ReadWrite<Emissive>());
			components.Add(ComponentType.ReadWrite<LightState>());
		}
		if (flag7)
		{
			components.Add(ComponentType.ReadWrite<MeshGroup>());
			components.Add(ComponentType.ReadWrite<Animated>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Meshes != null)
		{
			for (int i = 0; i < m_Meshes.Length; i++)
			{
				prefabs.Add(m_Meshes[i].m_Mesh);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ObjectGeometryData>());
		components.Add(ComponentType.ReadWrite<SubMesh>());
		bool flag = false;
		bool flag2 = false;
		if (m_Meshes != null)
		{
			for (int i = 0; i < m_Meshes.Length; i++)
			{
				RenderPrefabBase mesh = m_Meshes[i].m_Mesh;
				if (!(mesh == null))
				{
					flag |= mesh.Has<StackProperties>();
					flag2 = flag2 || mesh is CharacterGroup;
				}
			}
		}
		if (flag)
		{
			components.Add(ComponentType.ReadWrite<StackData>());
		}
		if (flag2)
		{
			components.Add(ComponentType.ReadWrite<SubMeshGroup>());
			components.Add(ComponentType.ReadWrite<CharacterElement>());
		}
	}
```


