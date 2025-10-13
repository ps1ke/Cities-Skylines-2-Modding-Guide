# Game.UI.InGame.DevTreeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DevTreeUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.City.DevTreeSystem m_DevTreeSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_DevTreePointsQuery;
    private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
    private Unity.Entities.EntityQuery m_UnlockedServiceQuery;
    private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery;
    private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding;
    private Colossal.UI.Binding.RawValueBinding m_ServicesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding;
    private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    public DevTreeUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node);
    private System.Void BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
    private System.Void BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
    private System.Void BindServices(Colossal.UI.Binding.IJsonWriter writer);
    private System.String GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab);
    private Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo> GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator);
    private System.Int32 GetDevTreePoints();
    private System.Int32 GetMaxDevTreePoints();
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedDevTreeServices(Unity.Collections.Allocator allocator);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void PurchaseNode(Unity.Entities.Entity node);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.City.DevTreeSystem m_DevTreeSystem`  

```csharp
private Game.City.DevTreeSystem m_DevTreeSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreePointsQuery;
```

- `private Unity.Entities.EntityQuery m_DevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedServiceQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery;
```

- `private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ServicesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ServicesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding;
```

- `private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public DevTreeUISystem()`  

```csharp
[Preserve]
	public DevTreeUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node) : System.Void`  

```csharp
private void BindNodeDetails(IJsonWriter binder, Entity node)
	{
		if (node != Entity.Null && base.EntityManager.TryGetComponent<DevTreeNodeData>(node, out var component) && base.EntityManager.TryGetComponent<PrefabData>(node, out var component2))
		{
			DevTreeNodePrefab prefab = m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(component2);
			bool value = base.EntityManager.HasEnabledComponent<Locked>(node);
			binder.TypeBegin("devTree.NodeDetails");
			binder.PropertyName("entity");
			binder.Write(node);
			binder.PropertyName("name");
			binder.Write(prefab.name);
			binder.PropertyName("icon");
			binder.Write(GetDevTreeIcon(prefab));
			binder.PropertyName("cost");
			binder.Write(component.m_Cost);
			binder.PropertyName("locked");
			binder.Write(value);
			int value2 = 0;
			bool value3 = false;
			if (base.EntityManager.TryGetBuffer(node, isReadOnly: true, out DynamicBuffer<DevTreeNodeRequirement> buffer))
			{
				value2 = buffer.Length;
				value3 = buffer.Length > 0;
				for (int i = 0; i < buffer.Length; i++)
				{
					if (base.EntityManager.HasEnabledComponent<Locked>(buffer[i].m_Node))
					{
						value3 = false;
					}
				}
			}
			binder.PropertyName("unlockable");
			binder.Write(value3);
			binder.PropertyName("requirementCount");
			binder.Write(value2);
			binder.PropertyName("milestoneRequirement");
			binder.Write(ProgressionUtils.GetRequiredMilestone(base.EntityManager, component.m_Service));
			binder.TypeEnd();
		}
		else
		{
			binder.WriteNull();
		}
	}
```

- `private BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  

```csharp
private void BindNodes(IJsonWriter binder, Entity service)
	{
		if (service != Entity.Null)
		{
			NativeList<DevTreeNodeInfo> devTreeNodes = GetDevTreeNodes(service, Allocator.TempJob);
			binder.ArrayBegin(devTreeNodes.Length);
			for (int i = 0; i < devTreeNodes.Length; i++)
			{
				DevTreeNodeInfo devTreeNodeInfo = devTreeNodes[i];
				DevTreeNodePrefab prefab = m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(devTreeNodeInfo.prefabData);
				binder.TypeBegin("devTree.Node");
				binder.PropertyName("entity");
				binder.Write(devTreeNodeInfo.entity);
				binder.PropertyName("name");
				binder.Write(prefab.name);
				binder.PropertyName("icon");
				binder.Write(GetDevTreeIcon(prefab));
				binder.PropertyName("cost");
				binder.Write(devTreeNodeInfo.devTreeNodeData.m_Cost);
				binder.PropertyName("locked");
				binder.Write(devTreeNodeInfo.locked);
				binder.PropertyName("position");
				binder.Write(new float2(prefab.m_HorizontalPosition, prefab.m_VerticalPosition));
				if (base.EntityManager.TryGetBuffer(devTreeNodeInfo.entity, isReadOnly: true, out DynamicBuffer<DevTreeNodeRequirement> buffer))
				{
					bool value = buffer.Length > 0;
					binder.PropertyName("requirements");
					binder.ArrayBegin(buffer.Length);
					for (int j = 0; j < buffer.Length; j++)
					{
						binder.Write(buffer[j].m_Node);
						if (base.EntityManager.HasEnabledComponent<Locked>(buffer[j].m_Node))
						{
							value = false;
						}
					}
					binder.ArrayEnd();
					binder.PropertyName("unlockable");
					binder.Write(value);
				}
				else
				{
					binder.PropertyName("requirements");
					binder.WriteEmptyArray();
					binder.PropertyName("unlockable");
					binder.Write(!devTreeNodeInfo.locked);
				}
				binder.TypeEnd();
			}
			binder.ArrayEnd();
			devTreeNodes.Dispose();
		}
		else
		{
			binder.WriteEmptyArray();
		}
	}
```

- `private BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  

```csharp
private void BindServiceDetails(IJsonWriter binder, Entity service)
	{
		if (service != Entity.Null && base.EntityManager.HasComponent<ServiceData>(service) && base.EntityManager.TryGetComponent<PrefabData>(service, out var component))
		{
			ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(component);
			binder.TypeBegin("devTree.ServiceDetails");
			binder.PropertyName("entity");
			binder.Write(service);
			binder.PropertyName("name");
			binder.Write(prefab.name);
			binder.PropertyName("icon");
			binder.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
			binder.PropertyName("locked");
			binder.Write(base.EntityManager.HasEnabledComponent<Locked>(service));
			binder.PropertyName("milestoneRequirement");
			binder.Write(ProgressionUtils.GetRequiredMilestone(base.EntityManager, service));
			binder.TypeEnd();
		}
		else
		{
			binder.WriteNull();
		}
	}
```

- `private BindServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindServices(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedDevTreeServices = GetSortedDevTreeServices(Allocator.TempJob);
		writer.ArrayBegin(sortedDevTreeServices.Length);
		for (int i = 0; i < sortedDevTreeServices.Length; i++)
		{
			UIObjectInfo uIObjectInfo = sortedDevTreeServices[i];
			ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(uIObjectInfo.prefabData);
			writer.TypeBegin("devTree.Service");
			writer.PropertyName("entity");
			writer.Write(uIObjectInfo.entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(uIObjectInfo.entity));
			writer.PropertyName("uiTag");
			writer.Write(prefab.uiTag);
			writer.PropertyName("requirements");
			m_PrefabUISystem.BindPrefabRequirements(writer, uIObjectInfo.entity);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		sortedDevTreeServices.Dispose();
	}
```

- `private GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab) : System.String`  

```csharp
private string GetDevTreeIcon(DevTreeNodePrefab prefab)
	{
		if (!string.IsNullOrEmpty(prefab.m_IconPath))
		{
			return prefab.m_IconPath;
		}
		if (prefab.m_IconPrefab != null)
		{
			return ImageSystem.GetThumbnail(prefab.m_IconPrefab) ?? m_ImageSystem.placeholderIcon;
		}
		return m_ImageSystem.placeholderIcon;
	}
```

- `private GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo>`  

```csharp
private NativeList<DevTreeNodeInfo> GetDevTreeNodes(Entity service, Allocator allocator)
	{
		NativeList<DevTreeNodeInfo> result = new NativeList<DevTreeNodeInfo>(16, allocator);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<DevTreeNodeData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DevTreeNodeData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Locked> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_DevTreeNodeQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<DevTreeNodeData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				EnabledMask enabledMask = archetypeChunk.GetEnabledMask(ref typeHandle3);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (nativeArray4[j].m_Service == service)
					{
						DevTreeNodeInfo value = new DevTreeNodeInfo
						{
							entity = nativeArray2[j],
							prefabData = nativeArray3[j],
							devTreeNodeData = nativeArray4[j],
							locked = (enabledMask.EnableBit.IsValid && enabledMask[j])
						};
						result.Add(in value);
					}
				}
			}
			return result;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private GetDevTreePoints() : System.Int32`  

```csharp
private int GetDevTreePoints()
	{
		return Mathf.Min((!m_DevTreePointsQuery.IsEmptyIgnoreFilter) ? m_DevTreePointsQuery.GetSingleton<DevTreePoints>().m_Points : 0, GetMaxDevTreePoints());
	}
```

- `private GetMaxDevTreePoints() : System.Int32`  

```csharp
private int GetMaxDevTreePoints()
	{
		NativeArray<DevTreeNodeData> nativeArray = m_LockedDevTreeNodeQuery.ToComponentDataArray<DevTreeNodeData>(Allocator.Temp);
		int num = 0;
		foreach (DevTreeNodeData item in nativeArray)
		{
			num += item.m_Cost;
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private GetSortedDevTreeServices(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private NativeList<UIObjectInfo> GetSortedDevTreeServices(Allocator allocator)
	{
		NativeArray<DevTreeNodeData> nativeArray = m_DevTreeNodeQuery.ToComponentDataArray<DevTreeNodeData>(Allocator.TempJob);
		NativeParallelHashSet<Entity> nativeParallelHashSet = new NativeParallelHashSet<Entity>(16, Allocator.TempJob);
		NativeList<UIObjectInfo> nativeList = new NativeList<UIObjectInfo>(16, allocator);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity service = nativeArray[i].m_Service;
			if (nativeParallelHashSet.Add(service) && base.EntityManager.TryGetComponent<UIObjectData>(service, out var component))
			{
				PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(service);
				nativeList.Add(new UIObjectInfo(service, componentData, component.m_Priority));
			}
		}
		nativeArray.Dispose();
		nativeParallelHashSet.Dispose();
		nativeList.Sort();
		return nativeList;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_DevTreeSystem = base.World.GetOrCreateSystemManaged<DevTreeSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_DevTreePointsQuery = GetEntityQuery(ComponentType.ReadOnly<DevTreePoints>());
		m_DevTreeNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<DevTreeNodeData>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_UnlockedServiceQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_ModifiedDevTreeNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<DevTreeNodeData>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_LockedDevTreeNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<DevTreeNodeData>(),
				ComponentType.ReadOnly<Locked>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		AddBinding(m_PointsBinding = new GetterValueBinding<int>("devTree", "points", GetDevTreePoints));
		AddBinding(m_ServicesBinding = new RawValueBinding("devTree", "services", BindServices));
		AddBinding(m_ServiceDetailsBinding = new RawMapBinding<Entity>("devTree", "serviceDetails", BindServiceDetails));
		AddBinding(m_NodesBinding = new RawMapBinding<Entity>("devTree", "nodes", BindNodes));
		AddBinding(m_NodeDetailsBinding = new RawMapBinding<Entity>("devTree", "nodeDetails", BindNodeDetails));
		AddBinding(new TriggerBinding<Entity>("devTree", "purchaseNode", PurchaseNode));
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_PointsBinding.Update();
		if (!m_ModifiedDevTreeNodeQuery.IsEmptyIgnoreFilter || PrefabUtils.HasUnlockedPrefab<DevTreeNodeData>(base.EntityManager, m_UnlockedServiceQuery))
		{
			m_NodesBinding.UpdateAll();
			m_NodeDetailsBinding.UpdateAll();
		}
		if (PrefabUtils.HasUnlockedPrefab<ServiceData>(base.EntityManager, m_UnlockedServiceQuery))
		{
			m_ServicesBinding.Update();
			m_ServiceDetailsBinding.UpdateAll();
		}
	}
```

- `private PurchaseNode(Unity.Entities.Entity node) : System.Void`  

```csharp
private void PurchaseNode(Entity node)
	{
		m_DevTreeSystem.Purchase(node);
	}
```


## Nested types

- `Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo`  
- `Game.UI.InGame.DevTreeUISystem+TypeHandle`  

