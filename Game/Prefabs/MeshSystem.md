# Game.Prefabs.MeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex;
    private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
    private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle;

    public MeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Int32 GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex;
```

- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
```

- `private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeshSystem()`  

```csharp
[Preserve]
	public MeshSystem()
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

- `public GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Int32`  

```csharp
public int GetMaterialIndex(SurfaceAsset surface)
	{
		ManagedBatchSystem.MaterialKey materialKey;
		if (m_CachedMaterialKey != null)
		{
			materialKey = m_CachedMaterialKey;
			m_CachedMaterialKey = null;
		}
		else
		{
			materialKey = new ManagedBatchSystem.MaterialKey();
		}
		surface.LoadProperties(useVT: true);
		materialKey.Initialize(surface);
		if (m_MaterialIndex.TryGetValue(materialKey, out var value))
		{
			materialKey.Clear();
			m_CachedMaterialKey = materialKey;
		}
		else
		{
			value = m_MaterialIndex.Count;
			m_MaterialIndex.Add(materialKey, value);
		}
		surface.Unload();
		return value;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<MeshData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_MaterialIndex = new Dictionary<ManagedBatchSystem.MaterialKey, int>();
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> chunks = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<MeshData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MeshData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<LodMesh> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LodMesh_RW_BufferTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<ProceduralBone> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RW_BufferTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<ProceduralLight> bufferTypeHandle3 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RW_BufferTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<LightAnimation> bufferTypeHandle4 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LightAnimation_RW_BufferTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<MeshMaterial> bufferTypeHandle5 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_MeshMaterial_RW_BufferTypeHandle, ref base.CheckedStateRef);
		bool flag = false;
		CompleteDependency();
		LodMesh value2 = default(LodMesh);
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<PrefabData> nativeArray = archetypeChunk.GetNativeArray(ref typeHandle2);
			if (archetypeChunk.Has(ref typeHandle))
			{
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (nativeArray[j].m_Index < 0)
					{
						m_ManagedBatchSystem.RemoveMesh(nativeArray2[j]);
						flag = true;
					}
				}
				continue;
			}
			NativeArray<MeshData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
			BufferAccessor<LodMesh> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
			BufferAccessor<ProceduralBone> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
			BufferAccessor<ProceduralLight> bufferAccessor3 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle3);
			BufferAccessor<LightAnimation> bufferAccessor4 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle4);
			BufferAccessor<MeshMaterial> bufferAccessor5 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle5);
			for (int k = 0; k < nativeArray.Length; k++)
			{
				RenderPrefab prefab = m_PrefabSystem.GetPrefab<RenderPrefab>(nativeArray[k]);
				MeshData value = nativeArray3[k];
				value.m_Bounds = prefab.bounds;
				value.m_SubMeshCount = prefab.meshCount;
				value.m_IndexCount = prefab.indexCount;
				value.m_SmoothingDistance = 0.001f;
				value.m_ShadowBias = 0.5f;
				if (prefab.meshCount != prefab.materialCount)
				{
					COSystemBase.baseLog.WarnFormat(prefab, "{0}: subMeshCount ({1}) != materialCount ({2})", prefab.name, prefab.meshCount, prefab.materialCount);
				}
				if (bufferAccessor5.Length != 0)
				{
					int materialCount = prefab.materialCount;
					DynamicBuffer<MeshMaterial> dynamicBuffer = bufferAccessor5[k];
					dynamicBuffer.ResizeUninitialized(materialCount);
					int num = 0;
					foreach (SurfaceAsset surfaceAsset in prefab.surfaceAssets)
					{
						dynamicBuffer[num++] = new MeshMaterial
						{
							m_MaterialIndex = GetMaterialIndex(surfaceAsset)
						};
					}
				}
				if (prefab.isImpostor)
				{
					value.m_State |= MeshFlags.Impostor;
				}
				if (bufferAccessor.Length != 0)
				{
					LodProperties component = prefab.GetComponent<LodProperties>();
					DynamicBuffer<LodMesh> dynamicBuffer2 = bufferAccessor[k];
					value.m_LodBias = component.m_Bias;
					value.m_ShadowBias += component.m_Bias + component.m_ShadowBias;
					if (component.m_LodMeshes != null)
					{
						dynamicBuffer2.ResizeUninitialized(component.m_LodMeshes.Length);
						for (int l = 0; l < component.m_LodMeshes.Length; l++)
						{
							RenderPrefab renderPrefab = component.m_LodMeshes[l];
							int index = l;
							for (int num2 = l - 1; num2 >= 0; num2--)
							{
								RenderPrefab renderPrefab2 = component.m_LodMeshes[num2];
								if (renderPrefab.indexCount <= renderPrefab2.indexCount)
								{
									break;
								}
								dynamicBuffer2[index] = dynamicBuffer2[num2];
								index = num2;
							}
							value2.m_LodMesh = m_PrefabSystem.GetEntity(renderPrefab);
							dynamicBuffer2[index] = value2;
						}
					}
				}
				if (prefab.surfaceArea > 0f)
				{
					float3 @float = value.m_Bounds.max - value.m_Bounds.min;
					float num3 = math.log2(math.sqrt(math.clamp(prefab.surfaceArea / (math.csum(@float * @float.yzx) * 2f), 1E-06f, 1f)));
					float num4 = math.log2(math.sqrt(math.clamp(math.cmax(math.min(@float, @float.yzx)) * 3f / math.csum(@float), 1E-06f, 1f)));
					value.m_LodBias -= num3;
					value.m_ShadowBias -= 1.5f * num3 + num4;
				}
				if (bufferAccessor2.Length != 0)
				{
					ProceduralAnimationProperties component2 = prefab.GetComponent<ProceduralAnimationProperties>();
					if (component2.m_Bones != null)
					{
						DynamicBuffer<ProceduralBone> dynamicBuffer3 = bufferAccessor2[k];
						dynamicBuffer3.ResizeUninitialized(component2.m_Bones.Length);
						for (int m = 0; m < component2.m_Bones.Length; m++)
						{
							ProceduralAnimationProperties.BoneInfo boneInfo = component2.m_Bones[m];
							float speed;
							float acceleration;
							switch (boneInfo.m_Type)
							{
							case BoneType.LookAtDirection:
							case BoneType.WindTurbineRotation:
							case BoneType.WindSpeedRotation:
							case BoneType.PoweredRotation:
							case BoneType.TrafficBarrierDirection:
							case BoneType.RollingRotation:
							case BoneType.PropellerRotation:
							case BoneType.LookAtRotation:
							case BoneType.LookAtAim:
							case BoneType.PropellerAngle:
							case BoneType.PantographRotation:
							case BoneType.WorkingRotation:
							case BoneType.OperatingRotation:
							case BoneType.TimeRotation:
							case BoneType.LookAtRotationSide:
							case BoneType.RotationXFromMovementY:
							case BoneType.LookAtAimForward:
								speed = boneInfo.m_Speed * (MathF.PI * 2f);
								acceleration = boneInfo.m_Acceleration * (MathF.PI * 2f);
								break;
							default:
								speed = boneInfo.m_Speed;
								acceleration = boneInfo.m_Acceleration;
								break;
							}
							int num5 = boneInfo.m_ConnectionID;
							if (num5 < 0 || num5 > 900)
							{
								COSystemBase.baseLog.ErrorFormat(prefab, "{0}: boneInfo[{1}].ConnectionID ({2}) != 0->900", prefab.name, m, num5);
								num5 = 0;
							}
							dynamicBuffer3[m] = new ProceduralBone
							{
								m_Position = boneInfo.position,
								m_Rotation = boneInfo.rotation,
								m_Scale = boneInfo.scale,
								m_BindPose = boneInfo.bindPose,
								m_ParentIndex = boneInfo.parentId,
								m_BindIndex = m,
								m_Type = boneInfo.m_Type,
								m_ConnectionID = num5,
								m_SourceIndex = boneInfo.m_SourceID,
								m_Speed = speed,
								m_Acceleration = acceleration
							};
						}
					}
				}
				if (bufferAccessor3.Length != 0)
				{
					EmissiveProperties component3 = prefab.GetComponent<EmissiveProperties>();
					if (component3.hasAnyLights)
					{
						DynamicBuffer<ProceduralLight> dynamicBuffer4 = bufferAccessor3[k];
						dynamicBuffer4.ResizeUninitialized(component3.lightsCount);
						int num6 = 0;
						int num7 = 0;
						if (bufferAccessor4.Length != 0)
						{
							DynamicBuffer<LightAnimation> dynamicBuffer5 = bufferAccessor4[k];
							int num8 = 0;
							if (component3.m_SignalGroupAnimations != null)
							{
								num8 += component3.m_SignalGroupAnimations.Count;
							}
							num6 = num8;
							if (component3.m_AnimationCurves != null)
							{
								num8 += component3.m_AnimationCurves.Count;
								num7 = component3.m_AnimationCurves.Count;
							}
							dynamicBuffer5.ResizeUninitialized(num8);
							if (component3.m_SignalGroupAnimations != null)
							{
								for (int n = 0; n < component3.m_SignalGroupAnimations.Count; n++)
								{
									EmissiveProperties.SignalGroupAnimation signalGroupAnimation = component3.m_SignalGroupAnimations[n];
									dynamicBuffer5[n] = new LightAnimation
									{
										m_DurationFrames = (uint)math.max(1, Mathf.RoundToInt(signalGroupAnimation.m_Duration * 60f)),
										m_SignalAnimation = new SignalAnimation(signalGroupAnimation.m_SignalGroupMasks)
									};
								}
							}
							if (component3.m_AnimationCurves != null)
							{
								for (int num9 = 0; num9 < component3.m_AnimationCurves.Count; num9++)
								{
									EmissiveProperties.AnimationProperties animationProperties = component3.m_AnimationCurves[num9];
									dynamicBuffer5[num6 + num9] = new LightAnimation
									{
										m_DurationFrames = (uint)math.max(1, Mathf.RoundToInt(animationProperties.m_Duration * 60f)),
										m_AnimationCurve = new AnimationCurve1(animationProperties.m_Curve)
									};
								}
							}
						}
						int num10 = 0;
						if (component3.hasMultiLights)
						{
							num10 = component3.m_MultiLights.Count;
							for (int num11 = 0; num11 < component3.m_MultiLights.Count; num11++)
							{
								EmissiveProperties.MultiLightMapping multiLightMapping = component3.m_MultiLights[num11];
								Color linear = multiLightMapping.color.linear;
								Color linear2 = multiLightMapping.colorOff.linear;
								dynamicBuffer4[num11] = new ProceduralLight
								{
									m_Color = new float4(linear.r, linear.g, linear.b, multiLightMapping.intensity * 100f),
									m_Color2 = new float4(linear2.r, linear2.g, linear2.b, multiLightMapping.intensity * 100f),
									m_Purpose = multiLightMapping.purpose,
									m_ResponseSpeed = 1f / math.max(0.001f, multiLightMapping.responseTime),
									m_AnimationIndex = math.select(-1, num6 + multiLightMapping.animationIndex, multiLightMapping.animationIndex >= 0 && multiLightMapping.animationIndex < num7)
								};
							}
						}
						if (component3.hasSingleLights)
						{
							for (int num12 = 0; num12 < component3.m_SingleLights.Count; num12++)
							{
								EmissiveProperties.SingleLightMapping singleLightMapping = component3.m_SingleLights[num12];
								Color linear3 = singleLightMapping.color.linear;
								Color linear4 = singleLightMapping.colorOff.linear;
								dynamicBuffer4[num10 + num12] = new ProceduralLight
								{
									m_Color = new float4(linear3.r, linear3.g, linear3.b, singleLightMapping.intensity * 100f),
									m_Color2 = new float4(linear4.r, linear4.g, linear4.b, singleLightMapping.intensity * 100f),
									m_Purpose = singleLightMapping.purpose,
									m_ResponseSpeed = 1f / math.max(0.001f, singleLightMapping.responseTime),
									m_AnimationIndex = math.select(-1, num6 + singleLightMapping.animationIndex, singleLightMapping.animationIndex >= 0 && singleLightMapping.animationIndex < num7)
								};
							}
						}
					}
				}
				UndergroundMesh component4 = prefab.GetComponent<UndergroundMesh>();
				if (component4 != null)
				{
					if (component4.m_IsTunnel)
					{
						value.m_DefaultLayers |= MeshLayer.Tunnel;
					}
					if (component4.m_IsPipeline)
					{
						value.m_DefaultLayers |= MeshLayer.Pipeline;
					}
					if (component4.m_IsSubPipeline)
					{
						value.m_DefaultLayers |= MeshLayer.SubPipeline;
					}
				}
				OverlayProperties component5 = prefab.GetComponent<OverlayProperties>();
				if (component5 != null && component5.m_IsWaterway)
				{
					value.m_DefaultLayers |= MeshLayer.Waterway;
				}
				if (prefab.GetComponent<DecalProperties>() != null)
				{
					value.m_State |= MeshFlags.Decal;
				}
				StackProperties component6 = prefab.GetComponent<StackProperties>();
				if (component6 != null)
				{
					switch (component6.m_Direction)
					{
					case StackDirection.Right:
						value.m_State |= MeshFlags.StackX;
						break;
					case StackDirection.Up:
						value.m_State |= MeshFlags.StackY;
						break;
					case StackDirection.Forward:
						value.m_State |= MeshFlags.StackZ;
						break;
					}
				}
				if (prefab.GetComponent<AnimationProperties>() != null)
				{
					value.m_State |= MeshFlags.Animated;
				}
				if (prefab.GetComponent<ProceduralAnimationProperties>() != null)
				{
					value.m_State |= MeshFlags.Skeleton;
				}
				CurveProperties component7 = prefab.GetComponent<CurveProperties>();
				if (component7 != null)
				{
					value.m_TilingCount = component7.m_TilingCount;
					if (component7.m_OverrideLength != 0f)
					{
						value.m_Bounds.min.z = component7.m_OverrideLength * -0.5f;
						value.m_Bounds.max.z = component7.m_OverrideLength * 0.5f;
					}
					if (component7.m_SmoothingDistance > value.m_SmoothingDistance)
					{
						value.m_SmoothingDistance = component7.m_SmoothingDistance;
					}
					if (component7.m_GeometryTiling)
					{
						value.m_State |= MeshFlags.Tiling;
					}
					if (component7.m_InvertCurve)
					{
						value.m_State |= MeshFlags.Invert;
					}
				}
				BaseProperties component8 = prefab.GetComponent<BaseProperties>();
				if (component8 != null && component8.m_BaseType != null)
				{
					value.m_State |= MeshFlags.Base;
					if (component8.m_UseMinBounds)
					{
						value.m_State |= MeshFlags.MinBounds;
					}
				}
				if (prefab.Has<DefaultMesh>())
				{
					float renderingSize = RenderingUtils.GetRenderingSize(MathUtils.Size(value.m_Bounds));
					value.m_State |= MeshFlags.Default;
					value.m_MinLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, value.m_LodBias);
					value.m_ShadowLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, value.m_ShadowBias);
				}
				nativeArray3[k] = value;
			}
		}
		InitializeMeshJob jobData = new InitializeMeshJob
		{
			m_Chunks = chunks,
			m_DeletedType = typeHandle,
			m_ProceduralBoneType = bufferTypeHandle2
		};
		base.Dependency = IJobParallelForExtensions.Schedule(jobData, chunks.Length, 1, base.Dependency);
		if (flag)
		{
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			JobHandle jobHandle = JobChunkExtensions.Schedule(new RemoveBatchGroupsJob
			{
				m_EntityType = entityTypeHandle,
				m_DeletedType = typeHandle,
				m_PrefabDataType = typeHandle2,
				m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferLookup, ref base.CheckedStateRef),
				m_FadeBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_FadeBatch_RW_BufferLookup, ref base.CheckedStateRef),
				m_BatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RW_BufferLookup, ref base.CheckedStateRef),
				m_NativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies),
				m_NativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies2),
				m_NativeSubBatches = m_BatchManagerSystem.GetNativeSubBatches(readOnly: false, out dependencies3)
			}, m_PrefabQuery, JobUtils.CombineDependencies(base.Dependency, dependencies, dependencies2, dependencies3));
			m_BatchManagerSystem.AddNativeBatchGroupsWriter(jobHandle);
			m_BatchManagerSystem.AddNativeBatchInstancesWriter(jobHandle);
			m_BatchManagerSystem.AddNativeSubBatchesWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Prefabs.MeshSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.MeshSystem+InitializeMeshJob`  
- `Game.Prefabs.MeshSystem+TypeHandle`  

