# Game.Prefabs.ZoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs;
    private System.Int32 m_ZoneFillColors;
    private System.Int32 m_ZoneEdgeColors;
    private System.Boolean m_IsEditorMode;
    private System.Boolean m_UpdateColors;
    private System.Boolean m_RemovedZones;
    private UnityEngine.Vector4[] m_FillColorArray;
    private UnityEngine.Vector4[] m_EdgeColorArray;
    private Unity.Jobs.JobHandle m_PrefabsReaders;
    private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle;

    public ZoneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
    private System.Int32 GetNextIndex();
    public Unity.Entities.Entity GetPrefab(Game.Zones.ZoneType zoneType);
    public Game.Prefabs.ZonePrefabs GetPrefabs();
    private System.Void GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected);
    private System.Void InitializeZonePrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Void UpdateZoneColors();
    private System.Void UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs;
```

- `private System.Int32 m_ZoneFillColors`  

```csharp
private System.Int32 m_ZoneFillColors;
```

- `private System.Int32 m_ZoneEdgeColors`  

```csharp
private System.Int32 m_ZoneEdgeColors;
```

- `private System.Boolean m_IsEditorMode`  

```csharp
private System.Boolean m_IsEditorMode;
```

- `private System.Boolean m_UpdateColors`  

```csharp
private System.Boolean m_UpdateColors;
```

- `private System.Boolean m_RemovedZones`  

```csharp
private System.Boolean m_RemovedZones;
```

- `private UnityEngine.Vector4[] m_FillColorArray`  

```csharp
private UnityEngine.Vector4[] m_FillColorArray;
```

- `private UnityEngine.Vector4[] m_EdgeColorArray`  

```csharp
private UnityEngine.Vector4[] m_EdgeColorArray;
```

- `private Unity.Jobs.JobHandle m_PrefabsReaders`  

```csharp
private Unity.Jobs.JobHandle m_PrefabsReaders;
```

- `private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneSystem()`  

```csharp
[Preserve]
	public ZoneSystem()
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

- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddPrefabsReader(JobHandle handle)
	{
		m_PrefabsReaders = JobHandle.CombineDependencies(m_PrefabsReaders, handle);
	}
```

- `private GetNextIndex() : System.Int32`  

```csharp
private int GetNextIndex()
	{
		if (m_RemovedZones)
		{
			for (int i = 1; i < m_ZonePrefabs.Length; i++)
			{
				if (m_ZonePrefabs[i] == Entity.Null)
				{
					return i;
				}
			}
			m_RemovedZones = false;
		}
		return math.max(1, m_ZonePrefabs.Length);
	}
```

- `public GetPrefab(Game.Zones.ZoneType zoneType) : Unity.Entities.Entity`  

```csharp
public Entity GetPrefab(ZoneType zoneType)
	{
		if (zoneType.m_Index >= m_ZonePrefabs.Length)
		{
			return Entity.Null;
		}
		return m_ZonePrefabs[zoneType.m_Index];
	}
```

- `public GetPrefabs() : Game.Prefabs.ZonePrefabs`  

```csharp
public ZonePrefabs GetPrefabs()
	{
		return new ZonePrefabs(m_ZonePrefabs.AsArray());
	}
```

- `private GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected) : System.Void`  

```csharp
private void GetZoneColors(Color color, out Color occupied, out Color selected)
	{
		Color.RGBToHSV(color, out var H, out var S, out var V);
		occupied = Color.HSVToRGB(H, S * 0.75f, V);
		occupied.a = color.a * 0.5f;
		selected = Color.HSVToRGB(H, math.min(1f, S * 1.25f), V);
		selected.a = math.min(color.a * 1.5f, math.lerp(color.a, 1f, 0.5f));
	}
```

- `private InitializeZonePrefabs() : System.Void`  

```csharp
private void InitializeZonePrefabs()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_CreatedQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ZoneData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ZoneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ArchetypeChunk archetypeChunk = nativeArray[i];
			NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
			NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
			NativeArray<ZoneData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle3);
			if (archetypeChunk.Has(ref typeHandle))
			{
				for (int j = 0; j < nativeArray4.Length; j++)
				{
					Entity entity = nativeArray2[j];
					ZoneData zoneData = nativeArray4[j];
					if (zoneData.m_ZoneType.m_Index < m_ZonePrefabs.Length && m_ZonePrefabs[zoneData.m_ZoneType.m_Index] == entity)
					{
						m_ZonePrefabs[zoneData.m_ZoneType.m_Index] = Entity.Null;
						m_RemovedZones = true;
					}
				}
				continue;
			}
			for (int k = 0; k < nativeArray4.Length; k++)
			{
				Entity value = nativeArray2[k];
				ZonePrefab prefab = m_PrefabSystem.GetPrefab<ZonePrefab>(nativeArray3[k]);
				ZoneData zoneData2 = nativeArray4[k];
				zoneData2.m_AreaType = prefab.m_AreaType;
				if (prefab.m_AreaType != AreaType.None)
				{
					zoneData2.m_ZoneType = new ZoneType
					{
						m_Index = (ushort)GetNextIndex()
					};
					zoneData2.m_MinOddHeight = ushort.MaxValue;
					zoneData2.m_MinEvenHeight = ushort.MaxValue;
					zoneData2.m_MaxHeight = 0;
				}
				else
				{
					zoneData2.m_ZoneFlags |= ZoneFlags.SupportNarrow;
					zoneData2.m_MinOddHeight = 1;
					zoneData2.m_MinEvenHeight = 1;
					zoneData2.m_MaxHeight = 1;
				}
				if (zoneData2.m_ZoneType.m_Index < m_ZonePrefabs.Length)
				{
					m_ZonePrefabs[zoneData2.m_ZoneType.m_Index] = value;
				}
				else
				{
					while (zoneData2.m_ZoneType.m_Index > m_ZonePrefabs.Length)
					{
						m_ZonePrefabs.Add(Entity.Null);
					}
					m_ZonePrefabs.Add(in value);
				}
				nativeArray4[k] = zoneData2;
				UpdateZoneColors(prefab, zoneData2);
			}
		}
		nativeArray.Dispose();
		Shader.SetGlobalVectorArray(m_ZoneFillColors, m_FillColorArray);
		Shader.SetGlobalVectorArray(m_ZoneEdgeColors, m_EdgeColorArray);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CreatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<ZoneData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Deleted>());
		m_ZonePrefabs = new NativeList<Entity>(Allocator.Persistent);
		m_FillColorArray = new Vector4[1023];
		m_EdgeColorArray = new Vector4[1023];
		m_ZoneFillColors = Shader.PropertyToID("colossal_ZoneFillColors");
		m_ZoneEdgeColors = Shader.PropertyToID("colossal_ZoneEdgeColors");
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_PrefabsReaders.Complete();
		m_ZonePrefabs.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		if (mode.IsEditor() != m_IsEditorMode)
		{
			m_PrefabsReaders.Complete();
			m_IsEditorMode = !m_IsEditorMode;
			m_UpdateColors = m_ZonePrefabs.Length != 0;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_PrefabsReaders.Complete();
		m_PrefabsReaders = default(JobHandle);
		if (!m_CreatedQuery.IsEmptyIgnoreFilter)
		{
			InitializeZonePrefabs();
		}
		if (m_UpdateColors)
		{
			UpdateZoneColors();
		}
	}
```

- `private UpdateZoneColors() : System.Void`  

```csharp
private void UpdateZoneColors(ZonePrefab zonePrefab, ZoneData zoneData)
	{
		Color color = zonePrefab.m_Color;
		Color edge = zonePrefab.m_Edge;
		GetZoneColors(color, out var occupied, out var selected);
		GetZoneColors(edge, out var occupied2, out var selected2);
		int colorIndex = ZoneUtils.GetColorIndex(CellFlags.Visible, zoneData.m_ZoneType);
		int colorIndex2 = ZoneUtils.GetColorIndex(CellFlags.Visible | CellFlags.Occupied, zoneData.m_ZoneType);
		int colorIndex3 = ZoneUtils.GetColorIndex(CellFlags.Visible | CellFlags.Selected, zoneData.m_ZoneType);
		if (m_IsEditorMode)
		{
			color.a = 0f;
			edge.a *= 0.5f;
			occupied.a = 0f;
			occupied2.a = 0f;
			selected.a = 0f;
		}
		m_FillColorArray[colorIndex] = color;
		m_EdgeColorArray[colorIndex] = edge;
		m_FillColorArray[colorIndex2] = occupied;
		m_EdgeColorArray[colorIndex2] = occupied2;
		m_FillColorArray[colorIndex3] = selected;
		m_EdgeColorArray[colorIndex3] = selected2;
	}
```

- `private UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData) : System.Void`  

```csharp
private void UpdateZoneColors(ZonePrefab zonePrefab, ZoneData zoneData)
	{
		Color color = zonePrefab.m_Color;
		Color edge = zonePrefab.m_Edge;
		GetZoneColors(color, out var occupied, out var selected);
		GetZoneColors(edge, out var occupied2, out var selected2);
		int colorIndex = ZoneUtils.GetColorIndex(CellFlags.Visible, zoneData.m_ZoneType);
		int colorIndex2 = ZoneUtils.GetColorIndex(CellFlags.Visible | CellFlags.Occupied, zoneData.m_ZoneType);
		int colorIndex3 = ZoneUtils.GetColorIndex(CellFlags.Visible | CellFlags.Selected, zoneData.m_ZoneType);
		if (m_IsEditorMode)
		{
			color.a = 0f;
			edge.a *= 0.5f;
			occupied.a = 0f;
			occupied2.a = 0f;
			selected.a = 0f;
		}
		m_FillColorArray[colorIndex] = color;
		m_EdgeColorArray[colorIndex] = edge;
		m_FillColorArray[colorIndex2] = occupied;
		m_EdgeColorArray[colorIndex2] = occupied2;
		m_FillColorArray[colorIndex3] = selected;
		m_EdgeColorArray[colorIndex3] = selected2;
	}
```


## Nested types

- `Game.Prefabs.ZoneSystem+TypeHandle`  

