# Game.Prefabs.AnimatedPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimatedPrefabSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle;

    public AnimatedPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target);
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

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimatedPrefabSystem()`  

```csharp
[Preserve]
	public AnimatedPrefabSystem()
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

- `private CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target) : System.Void`  

```csharp
private void CleanUpRootMotion(CharacterStyle.AnimationMotion[] source, NativeArray<AnimationMotion> target)
	{
		for (int i = 0; i < source.Length; i++)
		{
			CharacterStyle.AnimationMotion animationMotion = source[i];
			ref AnimationMotion reference = ref target.ElementAt(i);
			reference.m_StartOffset = animationMotion.startOffset;
			reference.m_EndOffset = animationMotion.endOffset;
			reference.m_StartRotation = animationMotion.startRotation;
			reference.m_EndRotation = animationMotion.endRotation;
			if (i != 0)
			{
				ref AnimationMotion reference2 = ref target.ElementAt(0);
				reference.m_StartOffset -= reference2.m_StartOffset;
				reference.m_StartRotation = math.mul(reference.m_StartRotation, math.inverse(reference2.m_StartRotation));
				reference.m_EndOffset -= reference2.m_EndOffset;
				reference.m_EndRotation = math.mul(reference.m_EndRotation, math.inverse(reference2.m_EndRotation));
			}
			reference.m_StartOffset.y = 0f;
			reference.m_EndOffset.y = 0f;
			float3 forward = math.forward(reference.m_StartRotation);
			float3 forward2 = math.forward(reference.m_EndRotation);
			forward.y = 0f;
			forward2.y = 0f;
			reference.m_StartRotation = quaternion.LookRotationSafe(forward, math.up());
			reference.m_EndRotation = quaternion.LookRotationSafe(forward2, math.up());
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_AnimatedSystem = base.World.GetOrCreateSystemManaged<AnimatedSystem>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadWrite<CharacterStyleData>());
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
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.Temp);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<CharacterStyleData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CharacterStyleData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<AnimationClip> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_AnimationClip_RW_BufferTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<AnimationMotion> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_AnimationMotion_RW_BufferTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		Dictionary<(ActivityType, AnimationType, AnimatedPropID), int> dictionary = new Dictionary<(ActivityType, AnimationType, AnimatedPropID), int>();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ArchetypeChunk archetypeChunk = nativeArray[i];
			NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
			NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
			NativeArray<CharacterStyleData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
			BufferAccessor<AnimationClip> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
			BufferAccessor<AnimationMotion> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				CharacterStyle prefab = m_PrefabSystem.GetPrefab<CharacterStyle>(nativeArray3[j]);
				ref CharacterStyleData reference = ref nativeArray4.ElementAt(j);
				DynamicBuffer<AnimationClip> dynamicBuffer = bufferAccessor[j];
				DynamicBuffer<AnimationMotion> dynamicBuffer2 = bufferAccessor2[j];
				reference.m_ActivityMask = default(ActivityMask);
				reference.m_RestPoseClipIndex = -1;
				int num = prefab.m_Animations.Length;
				int num2 = 0;
				dynamicBuffer.ResizeUninitialized(num);
				for (int k = 0; k < num; k++)
				{
					CharacterStyle.AnimationInfo animationInfo = prefab.m_Animations[k];
					ref AnimationClip reference2 = ref dynamicBuffer.ElementAt(k);
					reference2 = default(AnimationClip);
					reference2.m_InfoIndex = -1;
					reference2.m_RootMotionBone = animationInfo.rootMotionBone;
					reference2.m_PropClipIndex = -1;
					switch (animationInfo.layer)
					{
					case Colossal.Animations.AnimationLayer.BodyLayer:
						reference2.m_Layer = AnimationLayer.Body;
						break;
					case Colossal.Animations.AnimationLayer.PropLayer:
						reference2.m_Layer = AnimationLayer.Prop;
						break;
					case Colossal.Animations.AnimationLayer.FacialLayer:
						reference2.m_Layer = AnimationLayer.Facial;
						break;
					case Colossal.Animations.AnimationLayer.CorrectiveLayer:
						reference2.m_Layer = AnimationLayer.Corrective;
						break;
					default:
						reference2.m_Layer = AnimationLayer.None;
						break;
					}
					if (animationInfo.rootMotion != null)
					{
						num2 += animationInfo.rootMotion.Length;
					}
					if (animationInfo.type == Colossal.Animations.AnimationType.RestPose && animationInfo.target == null)
					{
						reference.m_RestPoseClipIndex = k;
					}
					if (animationInfo.target != null && animationInfo.target.TryGet<CharacterProperties>(out var component))
					{
						reference2.m_PropID = m_AnimatedSystem.GetPropID(component.m_AnimatedPropName);
						if (animationInfo.layer == Colossal.Animations.AnimationLayer.PropLayer)
						{
							dictionary[(animationInfo.activity, animationInfo.state, reference2.m_PropID)] = k;
						}
					}
					else
					{
						reference2.m_PropID = m_AnimatedSystem.GetPropID(null);
					}
				}
				dynamicBuffer2.ResizeUninitialized(num2);
				num2 = 0;
				float num3 = float.MaxValue;
				float num4 = 0f;
				for (int l = 0; l < num; l++)
				{
					CharacterStyle.AnimationInfo animationInfo2 = prefab.m_Animations[l];
					ref AnimationClip reference3 = ref dynamicBuffer.ElementAt(l);
					reference3.m_Type = animationInfo2.state;
					reference3.m_Activity = animationInfo2.activity;
					reference3.m_Conditions = animationInfo2.conditions;
					reference3.m_Playback = animationInfo2.playback;
					reference3.m_TargetValue = float.MinValue;
					if (reference3.m_Playback == AnimationPlayback.RandomLoop || reference3.m_Type == AnimationType.Move)
					{
						reference3.m_AnimationLength = (float)animationInfo2.frameCount / (float)animationInfo2.frameRate;
						reference3.m_FrameRate = animationInfo2.frameRate;
					}
					else
					{
						float num5 = (float)(animationInfo2.frameCount - 1) * (60f / (float)animationInfo2.frameRate);
						num5 = math.max(1f, math.round(num5 / 16f)) * 16f;
						reference3.m_AnimationLength = num5 * (1f / 60f);
						reference3.m_FrameRate = (float)math.max(1, animationInfo2.frameCount - 1) / reference3.m_AnimationLength;
						reference3.m_AnimationLength -= 0.001f;
					}
					if (animationInfo2.rootMotion != null)
					{
						NativeArray<AnimationMotion> subArray = dynamicBuffer2.AsNativeArray().GetSubArray(num2, animationInfo2.rootMotion.Length);
						CleanUpRootMotion(animationInfo2.rootMotion, subArray);
						reference3.m_MotionRange = new int2(num2, num2 + animationInfo2.rootMotion.Length);
						num2 += animationInfo2.rootMotion.Length;
						if (reference3.m_Type == AnimationType.Move)
						{
							AnimationMotion animationMotion = subArray[0];
							reference3.m_MovementSpeed = math.length(animationMotion.m_EndOffset - animationMotion.m_StartOffset) * reference3.m_FrameRate / (float)math.max(1, animationInfo2.frameCount - 1);
							if (reference3.m_Conditions == (ActivityCondition)0u)
							{
								switch (reference3.m_Activity)
								{
								case ActivityType.Walking:
									num3 = reference3.m_MovementSpeed;
									break;
								case ActivityType.Running:
									num4 = reference3.m_MovementSpeed;
									break;
								}
							}
						}
					}
					else
					{
						reference3.m_RootMotionBone = -1;
					}
					if (animationInfo2.layer != Colossal.Animations.AnimationLayer.PropLayer && reference3.m_PropID.isValid && dictionary.TryGetValue((animationInfo2.activity, animationInfo2.state, reference3.m_PropID), out var value))
					{
						reference3.m_PropClipIndex = value;
					}
					reference.m_ActivityMask.m_Mask |= new ActivityMask(reference3.m_Activity).m_Mask;
					reference.m_AnimationLayerMask.m_Mask |= new AnimationLayerMask(reference3.m_Layer).m_Mask;
				}
				for (int m = 0; m < dynamicBuffer.Length; m++)
				{
					ref AnimationClip reference4 = ref dynamicBuffer.ElementAt(m);
					if (reference4.m_Layer == AnimationLayer.Body && reference4.m_Type == AnimationType.Move)
					{
						reference4.m_SpeedRange = new Bounds1(0f, float.MaxValue);
						switch (reference4.m_Activity)
						{
						case ActivityType.Walking:
							reference4.m_SpeedRange.max = math.select((num3 + num4) * 0.5f, float.MaxValue, num4 <= num3);
							break;
						case ActivityType.Running:
							reference4.m_SpeedRange.min = math.select((num3 + num4) * 0.5f, 0f, num3 >= num4);
							break;
						}
					}
				}
				reference.m_BoneCount = prefab.m_BoneCount;
				reference.m_ShapeCount = prefab.m_ShapeCount;
			}
		}
		nativeArray.Dispose();
	}
```


## Nested types

- `Game.Prefabs.AnimatedPrefabSystem+TypeHandle`  

