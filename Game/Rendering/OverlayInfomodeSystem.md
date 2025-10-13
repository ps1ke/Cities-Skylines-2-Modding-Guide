# Game.Rendering.OverlayInfomodeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverlayInfomodeSystem : Game.GameSystemBase
{
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private UnityEngine.Texture2D m_TerrainTexture;
    private UnityEngine.Texture2D m_WaterTexture;
    private UnityEngine.Texture2D m_WindTexture;
    private Unity.Jobs.JobHandle m_Dependency;
    private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle;

    public OverlayInfomodeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void ApplyOverlay();
    private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
    private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData(Unity.Mathematics.int2 size);
    private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
    private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData(Unity.Mathematics.int2 size);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem`  

```csharp
private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem`  

```csharp
private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private UnityEngine.Texture2D m_TerrainTexture`  

```csharp
private UnityEngine.Texture2D m_TerrainTexture;
```

- `private UnityEngine.Texture2D m_WaterTexture`  

```csharp
private UnityEngine.Texture2D m_WaterTexture;
```

- `private UnityEngine.Texture2D m_WindTexture`  

```csharp
private UnityEngine.Texture2D m_WindTexture;
```

- `private Unity.Jobs.JobHandle m_Dependency`  

```csharp
private Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OverlayInfomodeSystem()`  

```csharp
[Preserve]
	public OverlayInfomodeSystem()
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

- `public ApplyOverlay() : System.Void`  

```csharp
public void ApplyOverlay()
	{
		if (m_TerrainRenderSystem.overrideOverlaymap == m_TerrainTexture)
		{
			m_Dependency.Complete();
			m_TerrainTexture.Apply();
		}
		if (m_TerrainRenderSystem.overlayExtramap == m_WindTexture)
		{
			m_Dependency.Complete();
			m_WindTexture.Apply();
		}
		if (m_WaterRenderSystem.overrideOverlaymap == m_WaterTexture)
		{
			m_Dependency.Complete();
			m_WaterTexture.Apply();
		}
	}
```

- `private GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
```

- `private GetTerrainTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private NativeArray<byte> GetTerrainTextureData(int2 size)
	{
		if (m_TerrainTexture.width != size.x || m_TerrainTexture.height != size.y)
		{
			m_TerrainTexture.Reinitialize(size.x, size.y);
			m_TerrainRenderSystem.overrideOverlaymap = null;
		}
		if (m_TerrainRenderSystem.overrideOverlaymap != m_TerrainTexture)
		{
			m_TerrainRenderSystem.overrideOverlaymap = m_TerrainTexture;
			ClearJob jobData = new ClearJob
			{
				m_TextureData = m_TerrainTexture.GetRawTextureData<byte>()
			};
			m_Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
			base.Dependency = m_Dependency;
		}
		return m_TerrainTexture.GetRawTextureData<byte>();
	}
```

- `private GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
```

- `private GetWaterTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private NativeArray<byte> GetWaterTextureData(int2 size)
	{
		if (m_WaterTexture.width != size.x || m_WaterTexture.height != size.y)
		{
			m_WaterTexture.Reinitialize(size.x, size.y);
			m_WaterRenderSystem.overrideOverlaymap = null;
		}
		if (m_WaterRenderSystem.overrideOverlaymap != m_WaterTexture)
		{
			m_WaterRenderSystem.overrideOverlaymap = m_WaterTexture;
			ClearJob jobData = new ClearJob
			{
				m_TextureData = m_WaterTexture.GetRawTextureData<byte>()
			};
			m_Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
			base.Dependency = m_Dependency;
		}
		return m_WaterTexture.GetRawTextureData<byte>();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainRenderSystem = base.World.GetOrCreateSystemManaged<TerrainRenderSystem>();
		m_WaterRenderSystem = base.World.GetOrCreateSystemManaged<WaterRenderSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomPreviewSystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_LandValueSystem = base.World.GetOrCreateSystemManaged<LandValueSystem>();
		m_PopulationToGridSystem = base.World.GetOrCreateSystemManaged<PopulationToGridSystem>();
		m_AvailabilityInfoToGridSystem = base.World.GetOrCreateSystemManaged<AvailabilityInfoToGridSystem>();
		m_TerrainTexture = new Texture2D(1, 1, TextureFormat.RGBA32, mipChain: false, linear: true)
		{
			name = "TerrainInfoTexture",
			hideFlags = HideFlags.HideAndDontSave,
			wrapMode = TextureWrapMode.Clamp
		};
		m_WaterTexture = new Texture2D(1, 1, TextureFormat.RGBA32, mipChain: false, linear: true)
		{
			name = "WaterInfoTexture",
			hideFlags = HideFlags.HideAndDontSave,
			wrapMode = TextureWrapMode.Clamp
		};
		m_WindTexture = new Texture2D(m_WindSystem.TextureSize.x, m_WindSystem.TextureSize.y, GraphicsFormat.R16G16B16A16_SFloat, 1, TextureCreationFlags.None)
		{
			name = "WindInfoTexture",
			hideFlags = HideFlags.HideAndDontSave,
			wrapMode = TextureWrapMode.Clamp
		};
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewHeatmapData>());
		m_HappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
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
		CoreUtils.Destroy(m_TerrainTexture);
		CoreUtils.Destroy(m_WaterTexture);
		CoreUtils.Destroy(m_WindTexture);
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_TerrainRenderSystem.overrideOverlaymap = null;
		m_TerrainRenderSystem.overlayExtramap = null;
		m_TerrainRenderSystem.overlayArrowMask = default(float4);
		m_WaterRenderSystem.overrideOverlaymap = null;
		m_WaterRenderSystem.overlayExtramap = null;
		m_WaterRenderSystem.overlayPollutionMask = default(float4);
		m_WaterRenderSystem.overlayArrowMask = default(float4);
		if (!m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_InfomodeQuery.ToArchetypeChunkArray(Allocator.TempJob);
			ComponentTypeHandle<InfoviewHeatmapData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewHeatmapData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfomodeActive> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<InfoviewHeatmapData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<InfomodeActive> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					InfoviewHeatmapData infoviewHeatmapData = nativeArray2[j];
					InfomodeActive activeData = nativeArray3[j];
					switch (infoviewHeatmapData.m_Type)
					{
					case HeatmapData.GroundWater:
					{
						JobHandle dependencies17;
						GroundWaterJob jobData16 = new GroundWaterJob
						{
							m_ActiveData = activeData,
							m_MapData = m_GroundWaterSystem.GetData(readOnly: true, out dependencies17)
						};
						jobData16.m_TextureData = GetTerrainTextureData(jobData16.m_MapData);
						JobHandle jobHandle13 = IJobExtensions.Schedule(jobData16, JobHandle.CombineDependencies(base.Dependency, dependencies17));
						m_GroundWaterSystem.AddReader(jobHandle13);
						m_Dependency = jobHandle13;
						base.Dependency = jobHandle13;
						break;
					}
					case HeatmapData.GroundPollution:
					{
						CitizenHappinessParameterData singleton3 = m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>();
						JobHandle dependencies16;
						GroundPollutionJob jobData15 = new GroundPollutionJob
						{
							m_ActiveData = activeData,
							m_MapData = m_GroundPollutionSystem.GetData(readOnly: true, out dependencies16),
							m_Multiplier = 256f / ((float)singleton3.m_MaxAirAndGroundPollutionBonus * (float)singleton3.m_PollutionBonusDivisor)
						};
						jobData15.m_TextureData = GetTerrainTextureData(jobData15.m_MapData);
						JobHandle jobHandle12 = IJobExtensions.Schedule(jobData15, JobHandle.CombineDependencies(base.Dependency, dependencies16));
						m_GroundPollutionSystem.AddReader(jobHandle12);
						m_Dependency = jobHandle12;
						base.Dependency = jobHandle12;
						break;
					}
					case HeatmapData.AirPollution:
					{
						CitizenHappinessParameterData singleton2 = m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>();
						JobHandle dependencies15;
						AirPollutionJob jobData14 = new AirPollutionJob
						{
							m_ActiveData = activeData,
							m_MapData = m_AirPollutionSystem.GetData(readOnly: true, out dependencies15),
							m_Multiplier = 256f / ((float)singleton2.m_MaxAirAndGroundPollutionBonus * (float)singleton2.m_PollutionBonusDivisor)
						};
						jobData14.m_TextureData = GetTerrainTextureData(jobData14.m_MapData);
						JobHandle job4 = IJobExtensions.Schedule(jobData14, JobHandle.CombineDependencies(base.Dependency, dependencies15));
						jobData14.m_TextureData = GetWaterTextureData(jobData14.m_MapData);
						jobData14.m_Water = true;
						job4 = JobHandle.CombineDependencies(job4, IJobExtensions.Schedule(jobData14, JobHandle.CombineDependencies(base.Dependency, dependencies15)));
						m_AirPollutionSystem.AddReader(job4);
						m_Dependency = job4;
						base.Dependency = job4;
						break;
					}
					case HeatmapData.Noise:
					{
						CitizenHappinessParameterData singleton = m_HappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>();
						JobHandle dependencies14;
						NoisePollutionJob jobData13 = new NoisePollutionJob
						{
							m_ActiveData = activeData,
							m_MapData = m_NoisePollutionSystem.GetData(readOnly: true, out dependencies14),
							m_Multiplier = 256f / ((float)singleton.m_MaxNoisePollutionBonus * (float)singleton.m_PollutionBonusDivisor)
						};
						jobData13.m_TextureData = GetTerrainTextureData(jobData13.m_MapData);
						JobHandle job3 = IJobExtensions.Schedule(jobData13, JobHandle.CombineDependencies(base.Dependency, dependencies14));
						jobData13.m_TextureData = GetWaterTextureData(jobData13.m_MapData);
						jobData13.m_Water = true;
						job3 = JobHandle.CombineDependencies(job3, IJobExtensions.Schedule(jobData13, JobHandle.CombineDependencies(base.Dependency, dependencies14)));
						m_NoisePollutionSystem.AddReader(job3);
						m_Dependency = job3;
						base.Dependency = job3;
						break;
					}
					case HeatmapData.Wind:
					{
						m_TerrainRenderSystem.overlayExtramap = m_WindTexture;
						m_WaterRenderSystem.overlayExtramap = m_WindTexture;
						float4 overlayArrowMask2 = default(float4);
						float4 overlayArrowMask3 = default(float4);
						overlayArrowMask2[activeData.m_Index - 1] = 1f;
						overlayArrowMask3[activeData.m_SecondaryIndex - 5] = 1f;
						m_TerrainRenderSystem.overlayArrowMask = overlayArrowMask2;
						m_WaterRenderSystem.overlayArrowMask = overlayArrowMask3;
						JobHandle dependencies13;
						JobHandle jobHandle11 = IJobExtensions.Schedule(new WindJob
						{
							m_MapData = m_WindSystem.GetData(readOnly: true, out dependencies13),
							m_TextureData = m_WindTexture.GetRawTextureData<half4>()
						}, JobHandle.CombineDependencies(base.Dependency, dependencies13));
						m_WindSystem.AddReader(jobHandle11);
						m_Dependency = jobHandle11;
						base.Dependency = jobHandle11;
						break;
					}
					case HeatmapData.WaterFlow:
					{
						m_WaterRenderSystem.overlayExtramap = m_WaterRenderSystem.flowTexture;
						float4 overlayArrowMask = new float4 { [activeData.m_Index - 5] = 1f };
						m_WaterRenderSystem.overlayArrowMask = overlayArrowMask;
						break;
					}
					case HeatmapData.TelecomCoverage:
					{
						JobHandle dependencies12;
						TelecomCoverageJob jobData12 = new TelecomCoverageJob
						{
							m_ActiveData = activeData,
							m_MapData = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies12)
						};
						jobData12.m_TextureData = GetTerrainTextureData(jobData12.m_MapData);
						JobHandle job2 = IJobExtensions.Schedule(jobData12, JobHandle.CombineDependencies(base.Dependency, dependencies12));
						jobData12.m_TextureData = GetWaterTextureData(jobData12.m_MapData);
						jobData12.m_Water = true;
						job2 = JobHandle.CombineDependencies(job2, IJobExtensions.Schedule(jobData12, JobHandle.CombineDependencies(base.Dependency, dependencies12)));
						m_TelecomCoverageSystem.AddReader(job2);
						m_Dependency = job2;
						base.Dependency = job2;
						break;
					}
					case HeatmapData.Fertility:
					{
						JobHandle dependencies11;
						FertilityJob jobData11 = new FertilityJob
						{
							m_ActiveData = activeData,
							m_MapData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies11)
						};
						jobData11.m_TextureData = GetTerrainTextureData(jobData11.m_MapData);
						JobHandle jobHandle10 = IJobExtensions.Schedule(jobData11, JobHandle.CombineDependencies(base.Dependency, dependencies11));
						m_NaturalResourceSystem.AddReader(jobHandle10);
						m_Dependency = jobHandle10;
						base.Dependency = jobHandle10;
						break;
					}
					case HeatmapData.Ore:
					{
						JobHandle dependencies10;
						OreJob jobData10 = new OreJob
						{
							m_ActiveData = activeData,
							m_MapData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies10),
							m_City = m_CitySystem.City,
							m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef)
						};
						jobData10.m_TextureData = GetTerrainTextureData(jobData10.m_MapData);
						JobHandle jobHandle9 = IJobExtensions.Schedule(jobData10, JobHandle.CombineDependencies(base.Dependency, dependencies10));
						m_NaturalResourceSystem.AddReader(jobHandle9);
						m_Dependency = jobHandle9;
						base.Dependency = jobHandle9;
						break;
					}
					case HeatmapData.Oil:
					{
						JobHandle dependencies9;
						OilJob jobData9 = new OilJob
						{
							m_ActiveData = activeData,
							m_MapData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies9),
							m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef)
						};
						jobData9.m_TextureData = GetTerrainTextureData(jobData9.m_MapData);
						JobHandle job = IJobExtensions.Schedule(jobData9, JobHandle.CombineDependencies(base.Dependency, dependencies9));
						jobData9.m_TextureData = GetWaterTextureData(jobData9.m_MapData);
						jobData9.m_Water = true;
						job = JobHandle.CombineDependencies(job, IJobExtensions.Schedule(jobData9, JobHandle.CombineDependencies(base.Dependency, dependencies9)));
						m_NaturalResourceSystem.AddReader(job);
						m_Dependency = job;
						base.Dependency = job;
						break;
					}
					case HeatmapData.Fish:
					{
						JobHandle dependencies8;
						FishJob jobData8 = new FishJob
						{
							m_ActiveData = activeData,
							m_MapData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies8)
						};
						jobData8.m_TextureData = GetWaterTextureData(jobData8.m_MapData);
						JobHandle jobHandle8 = IJobExtensions.Schedule(jobData8, JobHandle.CombineDependencies(base.Dependency, dependencies8));
						m_NaturalResourceSystem.AddReader(jobHandle8);
						m_Dependency = jobHandle8;
						base.Dependency = jobHandle8;
						break;
					}
					case HeatmapData.LandValue:
					{
						JobHandle dependencies7;
						LandValueJob jobData7 = new LandValueJob
						{
							m_ActiveData = activeData,
							m_MapData = m_LandValueSystem.GetData(readOnly: true, out dependencies7)
						};
						jobData7.m_TextureData = GetTerrainTextureData(jobData7.m_MapData);
						JobHandle jobHandle7 = IJobExtensions.Schedule(jobData7, JobHandle.CombineDependencies(dependencies7, base.Dependency));
						m_LandValueSystem.AddReader(jobHandle7);
						m_Dependency = jobHandle7;
						base.Dependency = jobHandle7;
						break;
					}
					case HeatmapData.Population:
					{
						JobHandle dependencies6;
						PopulationJob jobData6 = new PopulationJob
						{
							m_ActiveData = activeData,
							m_MapData = m_PopulationToGridSystem.GetData(readOnly: true, out dependencies6)
						};
						jobData6.m_TextureData = GetTerrainTextureData(jobData6.m_MapData);
						JobHandle jobHandle6 = IJobExtensions.Schedule(jobData6, JobHandle.CombineDependencies(dependencies6, base.Dependency));
						m_PopulationToGridSystem.AddReader(jobHandle6);
						m_Dependency = jobHandle6;
						base.Dependency = jobHandle6;
						break;
					}
					case HeatmapData.Attraction:
					{
						JobHandle dependencies5;
						AttractionJob jobData5 = new AttractionJob
						{
							m_ActiveData = activeData,
							m_MapData = m_AvailabilityInfoToGridSystem.GetData(readOnly: true, out dependencies5)
						};
						jobData5.m_TextureData = GetTerrainTextureData(jobData5.m_MapData);
						JobHandle jobHandle5 = IJobExtensions.Schedule(jobData5, JobHandle.CombineDependencies(base.Dependency, dependencies5));
						m_AvailabilityInfoToGridSystem.AddReader(jobHandle5);
						m_Dependency = jobHandle5;
						base.Dependency = jobHandle5;
						break;
					}
					case HeatmapData.Customers:
					{
						JobHandle dependencies4;
						CustomerJob jobData4 = new CustomerJob
						{
							m_ActiveData = activeData,
							m_MapData = m_AvailabilityInfoToGridSystem.GetData(readOnly: true, out dependencies4)
						};
						jobData4.m_TextureData = GetTerrainTextureData(jobData4.m_MapData);
						JobHandle jobHandle4 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(base.Dependency, dependencies4));
						m_AvailabilityInfoToGridSystem.AddReader(jobHandle4);
						m_Dependency = jobHandle4;
						base.Dependency = jobHandle4;
						break;
					}
					case HeatmapData.Workplaces:
					{
						JobHandle dependencies3;
						WorkplaceJob jobData3 = new WorkplaceJob
						{
							m_ActiveData = activeData,
							m_MapData = m_AvailabilityInfoToGridSystem.GetData(readOnly: true, out dependencies3)
						};
						jobData3.m_TextureData = GetTerrainTextureData(jobData3.m_MapData);
						JobHandle jobHandle3 = IJobExtensions.Schedule(jobData3, JobHandle.CombineDependencies(base.Dependency, dependencies3));
						m_AvailabilityInfoToGridSystem.AddReader(jobHandle3);
						m_Dependency = jobHandle3;
						base.Dependency = jobHandle3;
						break;
					}
					case HeatmapData.Services:
					{
						JobHandle dependencies2;
						ServiceJob jobData2 = new ServiceJob
						{
							m_ActiveData = activeData,
							m_MapData = m_AvailabilityInfoToGridSystem.GetData(readOnly: true, out dependencies2)
						};
						jobData2.m_TextureData = GetTerrainTextureData(jobData2.m_MapData);
						JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, dependencies2));
						m_AvailabilityInfoToGridSystem.AddReader(jobHandle2);
						m_Dependency = jobHandle2;
						base.Dependency = jobHandle2;
						break;
					}
					case HeatmapData.GroundWaterPollution:
					{
						JobHandle dependencies;
						GroundWaterPollutionJob jobData = new GroundWaterPollutionJob
						{
							m_ActiveData = activeData,
							m_MapData = m_GroundWaterSystem.GetData(readOnly: true, out dependencies)
						};
						jobData.m_TextureData = GetTerrainTextureData(jobData.m_MapData);
						JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, dependencies));
						m_GroundWaterSystem.AddReader(jobHandle);
						m_Dependency = jobHandle;
						base.Dependency = jobHandle;
						break;
					}
					case HeatmapData.WaterPollution:
					{
						float4 overlayPollutionMask = new float4 { [activeData.m_Index - 5] = 1f };
						m_WaterRenderSystem.overlayPollutionMask = overlayPollutionMask;
						break;
					}
					}
				}
			}
			nativeArray.Dispose();
		}
		if (m_ToolSystem.activeInfoview != null)
		{
			if (m_TerrainRenderSystem.overrideOverlaymap == null)
			{
				GetTerrainTextureData(1);
			}
			if (m_WaterRenderSystem.overrideOverlaymap == null)
			{
				GetWaterTextureData(1);
			}
		}
	}
```


## Nested types

- `Game.Rendering.OverlayInfomodeSystem+ClearJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+NoisePollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+AirPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+WindJob`  
- `Game.Rendering.OverlayInfomodeSystem+TelecomCoverageJob`  
- `Game.Rendering.OverlayInfomodeSystem+FertilityJob`  
- `Game.Rendering.OverlayInfomodeSystem+OreJob`  
- `Game.Rendering.OverlayInfomodeSystem+OilJob`  
- `Game.Rendering.OverlayInfomodeSystem+FishJob`  
- `Game.Rendering.OverlayInfomodeSystem+LandValueJob`  
- `Game.Rendering.OverlayInfomodeSystem+PopulationJob`  
- `Game.Rendering.OverlayInfomodeSystem+AttractionJob`  
- `Game.Rendering.OverlayInfomodeSystem+CustomerJob`  
- `Game.Rendering.OverlayInfomodeSystem+WorkplaceJob`  
- `Game.Rendering.OverlayInfomodeSystem+ServiceJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+TypeHandle`  

