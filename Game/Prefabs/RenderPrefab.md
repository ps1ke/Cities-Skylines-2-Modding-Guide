# Game.Prefabs.RenderPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RenderPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RenderPrefab : Game.Prefabs.RenderPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.GeometryAsset> m_GeometryAsset;
    private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.SurfaceAsset>[] m_SurfaceAssets;
    private Colossal.Mathematics.Bounds3 m_Bounds;
    private System.Single m_SurfaceArea;
    private System.Int32 m_IndexCount;
    private System.Int32 m_VertexCount;
    private System.Int32 m_MeshCount;
    private System.Boolean m_IsImpostor;
    private System.Boolean m_ManualVTRequired;
    private UnityEngine.Material[] m_MaterialsContainer;

    public System.Boolean hasGeometryAsset { get; }
    public Colossal.IO.AssetDatabase.GeometryAsset geometryAsset { get; set; }
    public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaceAssets { get; set; }
    public Colossal.Mathematics.Bounds3 bounds { get; set; }
    public System.Single surfaceArea { get; set; }
    public System.Int32 indexCount { get; set; }
    public System.Int32 vertexCount { get; set; }
    public System.Int32 meshCount { get; set; }
    public System.Boolean isImpostor { get; set; }
    public System.Boolean manualVTRequired { get; set; }
    public System.Int32 materialCount { get; }

    public RenderPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public Colossal.IO.AssetDatabase.SurfaceAsset GetSurfaceAsset(System.Int32 index);
    public UnityEngine.Material ObtainMaterial(System.Int32 i, System.Boolean useVT);
    public UnityEngine.Material[] ObtainMaterials(System.Boolean useVT);
    public UnityEngine.Mesh ObtainMesh(System.Int32 materialIndex, System.Int32& subMeshIndex);
    public UnityEngine.Mesh[] ObtainMeshes();
    public System.Void Release();
    public System.Void ReleaseMaterials();
    public System.Void ReleaseMeshes();
    public System.Void SetSurfaceAsset(System.Int32 index, Colossal.IO.AssetDatabase.SurfaceAsset value);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.GeometryAsset> m_GeometryAsset`  

```csharp
private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.GeometryAsset> m_GeometryAsset;
```

- `private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.SurfaceAsset>[] m_SurfaceAssets`  

```csharp
private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.SurfaceAsset>[] m_SurfaceAssets;
```

- `private Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
private Colossal.Mathematics.Bounds3 m_Bounds;
```

- `private System.Single m_SurfaceArea`  

```csharp
private System.Single m_SurfaceArea;
```

- `private System.Int32 m_IndexCount`  

```csharp
private System.Int32 m_IndexCount;
```

- `private System.Int32 m_VertexCount`  

```csharp
private System.Int32 m_VertexCount;
```

- `private System.Int32 m_MeshCount`  

```csharp
private System.Int32 m_MeshCount;
```

- `private System.Boolean m_IsImpostor`  

```csharp
private System.Boolean m_IsImpostor;
```

- `private System.Boolean m_ManualVTRequired`  

```csharp
private System.Boolean m_ManualVTRequired;
```

- `private UnityEngine.Material[] m_MaterialsContainer`  

```csharp
private UnityEngine.Material[] m_MaterialsContainer;
```


## Properties

- `public System.Boolean hasGeometryAsset { get }`  

```csharp
public System.Boolean hasGeometryAsset { get; }
```

- `public Colossal.IO.AssetDatabase.GeometryAsset geometryAsset { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset geometryAsset { get; set; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaceAssets { get; set }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaceAssets { get; set; }
```

- `public Colossal.Mathematics.Bounds3 bounds { get; set }`  

```csharp
public Colossal.Mathematics.Bounds3 bounds { get; set; }
```

- `public System.Single surfaceArea { get; set }`  

```csharp
public System.Single surfaceArea { get; set; }
```

- `public System.Int32 indexCount { get; set }`  

```csharp
public System.Int32 indexCount { get; set; }
```

- `public System.Int32 vertexCount { get; set }`  

```csharp
public System.Int32 vertexCount { get; set; }
```

- `public System.Int32 meshCount { get; set }`  

```csharp
public System.Int32 meshCount { get; set; }
```

- `public System.Boolean isImpostor { get; set }`  

```csharp
public System.Boolean isImpostor { get; set; }
```

- `public System.Boolean manualVTRequired { get; set }`  

```csharp
public System.Boolean manualVTRequired { get; set; }
```

- `public System.Int32 materialCount { get }`  

```csharp
public System.Int32 materialCount { get; }
```


## Constructors

- `public RenderPrefab()`  

```csharp
public RenderPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<MeshData>());
		components.Add(ComponentType.ReadWrite<SharedMeshData>());
		components.Add(ComponentType.ReadWrite<BatchGroup>());
		if (isImpostor)
		{
			components.Add(ComponentType.ReadWrite<ImpostorData>());
		}
	}
```

- `public GetSurfaceAsset(System.Int32 index) : Colossal.IO.AssetDatabase.SurfaceAsset`  

```csharp
public SurfaceAsset GetSurfaceAsset(int index)
	{
		return m_SurfaceAssets[index];
	}
```

- `public ObtainMaterial(System.Int32 i, System.Boolean useVT = True) : UnityEngine.Material`  

```csharp
public Material ObtainMaterial(int i, bool useVT = true)
	{
		Material[] array = ObtainMaterials(useVT);
		if (i < 0 || i >= array.Length)
		{
			throw new IndexOutOfRangeException($"i {i} is out of material range (length: {array.Length}) in {base.name}");
		}
		return array[i];
	}
```

- `public ObtainMaterials(System.Boolean useVT = True) : UnityEngine.Material[]`  

```csharp
public Material[] ObtainMaterials(bool useVT = true)
	{
		ComponentBase.baseLog.TraceFormat(this, "ObtainMaterials {0}", base.name);
		if (m_MaterialsContainer == null || m_MaterialsContainer.Length != materialCount)
		{
			m_MaterialsContainer = new Material[materialCount];
		}
		for (int i = 0; i < materialCount; i++)
		{
			SurfaceAsset surfaceAsset = m_SurfaceAssets[i];
			m_MaterialsContainer[i] = surfaceAsset.Load(-1, loadTextures: true, TextureAsset.KeepOnCPU.Dont, useVT);
		}
		return m_MaterialsContainer;
	}
```

- `public ObtainMesh(System.Int32 materialIndex, System.Int32& subMeshIndex) : UnityEngine.Mesh`  

```csharp
public Mesh ObtainMesh(int materialIndex, out int subMeshIndex)
	{
		ComponentBase.baseLog.TraceFormat(this, "ObtainMesh {0}", base.name);
		subMeshIndex = materialIndex;
		if (hasGeometryAsset)
		{
			Mesh[] array = geometryAsset?.ObtainMeshes();
			if (array != null)
			{
				Mesh[] array2 = array;
				foreach (Mesh mesh in array2)
				{
					if (materialIndex < mesh.subMeshCount)
					{
						subMeshIndex = materialIndex;
						return mesh;
					}
					materialIndex -= mesh.subMeshCount;
				}
			}
		}
		return null;
	}
```

- `public ObtainMeshes() : UnityEngine.Mesh[]`  

```csharp
public Mesh[] ObtainMeshes()
	{
		ComponentBase.baseLog.TraceFormat(this, "ObtainMeshes {0}", base.name);
		return geometryAsset?.ObtainMeshes();
	}
```

- `public Release() : System.Void`  

```csharp
public void Release()
	{
		ReleaseMeshes();
		ReleaseMaterials();
	}
```

- `public ReleaseMaterials() : System.Void`  

```csharp
public void ReleaseMaterials()
	{
		ComponentBase.baseLog.TraceFormat(this, "ReleaseMaterials {0}", base.name);
	}
```

- `public ReleaseMeshes() : System.Void`  

```csharp
public void ReleaseMeshes()
	{
		ComponentBase.baseLog.TraceFormat(this, "ReleaseMeshes {0}", base.name);
		geometryAsset?.ReleaseMeshes();
	}
```

- `public SetSurfaceAsset(System.Int32 index, Colossal.IO.AssetDatabase.SurfaceAsset value) : System.Void`  

```csharp
public void SetSurfaceAsset(int index, SurfaceAsset value)
	{
		m_SurfaceAssets[index] = value;
	}
```


## Nested types

- `Game.Prefabs.RenderPrefab+<>c`  

