# Game.UI.InGame.LocalServicesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalServicesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set; }

    public LocalServicesSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set; }
```


## Constructors

- `public LocalServicesSection()`  

```csharp
[Preserve]
	public LocalServicesSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_ServiceDistrictBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<ServiceDistrict>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		localServiceBuildings = new NativeList<Entity>(Allocator.Persistent);
		prefabs = new NativeList<Entity>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		localServiceBuildings.Dispose();
		prefabs.Dispose();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		NativeArray<Entity> nativeArray = m_ServiceDistrictBuildingQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<PrefabRef> nativeArray2 = m_ServiceDistrictBuildingQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				DynamicBuffer<ServiceDistrict> buffer = base.EntityManager.GetBuffer<ServiceDistrict>(nativeArray[i], isReadOnly: true);
				for (int j = 0; j < buffer.Length; j++)
				{
					if (buffer[j].m_District == selectedEntity)
					{
						localServiceBuildings.Add(nativeArray[i]);
						NativeList<Entity> nativeList = prefabs;
						PrefabRef prefabRef = nativeArray2[i];
						nativeList.Add(in prefabRef.m_Prefab);
						break;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity);
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("localServiceBuildings");
		writer.ArrayBegin(localServiceBuildings.Length);
		for (int i = 0; i < localServiceBuildings.Length; i++)
		{
			writer.TypeBegin("selectedInfo.LocalServiceBuilding");
			writer.PropertyName("name");
			m_NameSystem.BindName(writer, localServiceBuildings[i]);
			writer.PropertyName("serviceIcon");
			writer.Write(m_ImageSystem.GetGroupIcon(prefabs[i]));
			writer.PropertyName("entity");
			writer.Write(localServiceBuildings[i]);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		localServiceBuildings.Clear();
		prefabs.Clear();
	}
```


