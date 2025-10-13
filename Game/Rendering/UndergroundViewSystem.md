# Game.Rendering.UndergroundViewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UndergroundViewSystem : Game.GameSystemBase
{
    private System.Boolean <undergroundOn>k__BackingField;
    private System.Boolean <tunnelsOn>k__BackingField;
    private System.Boolean <pipelinesOn>k__BackingField;
    private System.Boolean <subPipelinesOn>k__BackingField;
    private System.Boolean <waterwaysOn>k__BackingField;
    private System.Boolean <contourLinesOn>k__BackingField;
    private System.Boolean <markersOn>k__BackingField;
    private Game.Net.UtilityTypes <utilityTypes>k__BackingField;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private System.Boolean m_LastWasWaterways;
    private System.Boolean m_LastWasMarkers;
    private System.Boolean m_Loaded;
    private Game.Net.UtilityTypes m_LastUtilityTypes;
    private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle;

    public System.Boolean undergroundOn { get; private set; }
    public System.Boolean tunnelsOn { get; private set; }
    public System.Boolean pipelinesOn { get; private set; }
    public System.Boolean subPipelinesOn { get; private set; }
    public System.Boolean waterwaysOn { get; private set; }
    public System.Boolean contourLinesOn { get; private set; }
    public System.Boolean markersOn { get; private set; }
    public Game.Net.UtilityTypes utilityTypes { get; private set; }

    public UndergroundViewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <undergroundOn>k__BackingField`  

```csharp
private System.Boolean <undergroundOn>k__BackingField;
```

- `private System.Boolean <tunnelsOn>k__BackingField`  

```csharp
private System.Boolean <tunnelsOn>k__BackingField;
```

- `private System.Boolean <pipelinesOn>k__BackingField`  

```csharp
private System.Boolean <pipelinesOn>k__BackingField;
```

- `private System.Boolean <subPipelinesOn>k__BackingField`  

```csharp
private System.Boolean <subPipelinesOn>k__BackingField;
```

- `private System.Boolean <waterwaysOn>k__BackingField`  

```csharp
private System.Boolean <waterwaysOn>k__BackingField;
```

- `private System.Boolean <contourLinesOn>k__BackingField`  

```csharp
private System.Boolean <contourLinesOn>k__BackingField;
```

- `private System.Boolean <markersOn>k__BackingField`  

```csharp
private System.Boolean <markersOn>k__BackingField;
```

- `private Game.Net.UtilityTypes <utilityTypes>k__BackingField`  

```csharp
private Game.Net.UtilityTypes <utilityTypes>k__BackingField;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem`  

```csharp
private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private System.Boolean m_LastWasWaterways`  

```csharp
private System.Boolean m_LastWasWaterways;
```

- `private System.Boolean m_LastWasMarkers`  

```csharp
private System.Boolean m_LastWasMarkers;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.UtilityTypes m_LastUtilityTypes`  

```csharp
private Game.Net.UtilityTypes m_LastUtilityTypes;
```

- `private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean undergroundOn { get; private set }`  

```csharp
public System.Boolean undergroundOn { get; private set; }
```

- `public System.Boolean tunnelsOn { get; private set }`  

```csharp
public System.Boolean tunnelsOn { get; private set; }
```

- `public System.Boolean pipelinesOn { get; private set }`  

```csharp
public System.Boolean pipelinesOn { get; private set; }
```

- `public System.Boolean subPipelinesOn { get; private set }`  

```csharp
public System.Boolean subPipelinesOn { get; private set; }
```

- `public System.Boolean waterwaysOn { get; private set }`  

```csharp
public System.Boolean waterwaysOn { get; private set; }
```

- `public System.Boolean contourLinesOn { get; private set }`  

```csharp
public System.Boolean contourLinesOn { get; private set; }
```

- `public System.Boolean markersOn { get; private set }`  

```csharp
public System.Boolean markersOn { get; private set; }
```

- `public Game.Net.UtilityTypes utilityTypes { get; private set }`  

```csharp
public Game.Net.UtilityTypes utilityTypes { get; private set; }
```


## Constructors

- `public UndergroundViewSystem()`  

```csharp
[Preserve]
	public UndergroundViewSystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_UtilityLodUpdateSystem = base.World.GetOrCreateSystemManaged<UtilityLodUpdateSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_InfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<InfomodeActive>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<InfoviewNetGeometryData>(),
				ComponentType.ReadOnly<InfoviewNetStatusData>(),
				ComponentType.ReadOnly<InfoviewCoverageData>()
			}
		});
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.GetAvailableSnapMask(out var onMask, out var offMask);
			undergroundOn = m_ToolSystem.activeTool.requireUnderground;
			tunnelsOn = m_ToolSystem.activeTool.requireUnderground || (m_ToolSystem.activeTool.requireNet & (Layer.Road | Layer.TrainTrack | Layer.Pathway | Layer.TramTrack | Layer.SubwayTrack | Layer.PublicTransportRoad)) != 0;
			subPipelinesOn = (m_ToolSystem.activeTool.requireNet & (Layer.PowerlineLow | Layer.PowerlineHigh | Layer.WaterPipe | Layer.SewagePipe)) != Layer.None || (undergroundOn && (m_ToolSystem.activeTool.requireNet & Layer.ResourceLine) != 0);
			pipelinesOn = m_ToolSystem.activeTool.requirePipelines || subPipelinesOn || (undergroundOn && tunnelsOn);
			waterwaysOn = (m_ToolSystem.activeTool.requireNet & Layer.Waterway) != 0;
			contourLinesOn = (ToolBaseSystem.GetActualSnap(m_ToolSystem.activeTool.selectedSnap, onMask, offMask) & Snap.ContourLines) != 0;
		}
		else
		{
			undergroundOn = false;
			tunnelsOn = false;
			pipelinesOn = false;
			subPipelinesOn = false;
			waterwaysOn = false;
			contourLinesOn = false;
		}
		markersOn = !m_RenderingSystem.hideOverlay;
		utilityTypes = UtilityTypes.None;
		if (!m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			ComponentTypeHandle<InfoviewNetGeometryData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewNetStatusData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewCoverageData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewCoverageData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			NativeArray<ArchetypeChunk> nativeArray = m_InfomodeQuery.ToArchetypeChunkArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<InfoviewNetGeometryData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<InfoviewNetStatusData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					switch (nativeArray2[j].m_Type)
					{
					case NetType.Road:
						tunnelsOn = true;
						break;
					case NetType.TrainTrack:
						tunnelsOn = true;
						break;
					case NetType.TramTrack:
						tunnelsOn = true;
						break;
					case NetType.Waterway:
						waterwaysOn = true;
						break;
					case NetType.SubwayTrack:
						tunnelsOn = true;
						break;
					}
				}
				for (int k = 0; k < nativeArray3.Length; k++)
				{
					switch (nativeArray3[k].m_Type)
					{
					case NetStatusType.Wear:
						tunnelsOn = true;
						break;
					case NetStatusType.TrafficFlow:
						tunnelsOn = true;
						break;
					case NetStatusType.TrafficVolume:
						tunnelsOn = true;
						break;
					case NetStatusType.LowVoltageFlow:
						pipelinesOn = true;
						subPipelinesOn = true;
						utilityTypes |= UtilityTypes.LowVoltageLine;
						break;
					case NetStatusType.HighVoltageFlow:
						pipelinesOn = true;
						subPipelinesOn = true;
						utilityTypes |= UtilityTypes.HighVoltageLine;
						break;
					case NetStatusType.PipeWaterFlow:
						pipelinesOn = true;
						subPipelinesOn = true;
						utilityTypes |= UtilityTypes.WaterPipe;
						break;
					case NetStatusType.PipeSewageFlow:
						pipelinesOn = true;
						subPipelinesOn = true;
						utilityTypes |= UtilityTypes.SewagePipe;
						break;
					case NetStatusType.OilFlow:
						pipelinesOn = true;
						subPipelinesOn = true;
						utilityTypes |= UtilityTypes.Resource;
						break;
					}
				}
				if (archetypeChunk.Has(ref typeHandle3))
				{
					tunnelsOn = true;
				}
			}
			nativeArray.Dispose();
		}
		if (utilityTypes != m_LastUtilityTypes)
		{
			m_LastUtilityTypes = utilityTypes;
			if (!loaded)
			{
				m_UtilityLodUpdateSystem.Update();
			}
		}
		if (waterwaysOn != m_LastWasWaterways)
		{
			m_LastWasWaterways = waterwaysOn;
			Camera main = Camera.main;
			if (main != null)
			{
				if (waterwaysOn)
				{
					main.cullingMask |= 1 << LayerMask.NameToLayer("Waterway");
				}
				else
				{
					main.cullingMask &= ~(1 << LayerMask.NameToLayer("Waterway"));
				}
			}
		}
		if (markersOn == m_LastWasMarkers)
		{
			return;
		}
		m_LastWasMarkers = markersOn;
		Camera main2 = Camera.main;
		if (main2 != null)
		{
			if (markersOn)
			{
				main2.cullingMask |= 1 << LayerMask.NameToLayer("Marker");
			}
			else
			{
				main2.cullingMask &= ~(1 << LayerMask.NameToLayer("Marker"));
			}
		}
	}
```


## Nested types

- `Game.Rendering.UndergroundViewSystem+TypeHandle`  

