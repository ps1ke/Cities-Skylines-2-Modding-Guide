# Game.Rendering.RelativeObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RelativeObjectSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Unity.Entities.EntityQuery m_RelativeQuery;
    private Unity.Entities.EntityQuery m_InterpolateQuery;
    private System.UInt32 m_PrevFrameIndex;
    private Game.Rendering.RelativeObjectSystem+TypeHandle __TypeHandle;

    public RelativeObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Objects.Transform GetRelativeTransform(Game.Objects.Relative relative, Unity.Entities.Entity parent, Unity.Entities.BufferLookup`1[[Game.Rendering.BoneHistory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boneHistoryLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshLookup);
    public static System.Single GetTargetRotation(Game.Prefabs.AnimationClip& clip, System.Single def, System.Single prev);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void UpdateDrivingAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Unity.Mathematics.float3 velocity, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset);
    public static System.Void UpdateDrivingClips(Unity.Entities.Entity entity, Game.Prefabs.AnimationClip& clip, Game.Prefabs.AnimationClip& clipI, System.Int16& clipIndex, System.Int16& clipIndexI, System.Single& movementSpeed, System.Single& interpolation, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityType targetActivity);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Unity.Entities.EntityQuery m_RelativeQuery`  

```csharp
private Unity.Entities.EntityQuery m_RelativeQuery;
```

- `private Unity.Entities.EntityQuery m_InterpolateQuery`  

```csharp
private Unity.Entities.EntityQuery m_InterpolateQuery;
```

- `private System.UInt32 m_PrevFrameIndex`  

```csharp
private System.UInt32 m_PrevFrameIndex;
```

- `private Game.Rendering.RelativeObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RelativeObjectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RelativeObjectSystem()`  

```csharp
[Preserve]
	public RelativeObjectSystem()
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

- `private static GetRelativeTransform(Game.Objects.Relative relative, Unity.Entities.Entity parent, Unity.Entities.BufferLookup`1[[Game.Rendering.BoneHistory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boneHistoryLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshLookup) : Game.Objects.Transform`  

```csharp
private static Transform GetRelativeTransform(Relative relative, Entity parent, ref BufferLookup<BoneHistory> boneHistoryLookup, ref ComponentLookup<PrefabRef> prefabRefLookup, ref BufferLookup<SubMesh> subMeshLookup)
	{
		if (relative.m_BoneIndex.y >= 0)
		{
			DynamicBuffer<BoneHistory> dynamicBuffer = boneHistoryLookup[parent];
			if (dynamicBuffer.Length > relative.m_BoneIndex.y)
			{
				float4x4 matrix = dynamicBuffer[relative.m_BoneIndex.y].m_Matrix;
				float3 @float = math.transform(matrix, relative.m_Position);
				float3 forward = math.rotate(matrix, math.forward(relative.m_Rotation));
				float3 up = math.rotate(matrix, math.mul(relative.m_Rotation, math.up()));
				quaternion quaternion = quaternion.LookRotation(forward, up);
				if (relative.m_BoneIndex.z >= 0)
				{
					SubMesh subMesh = subMeshLookup[prefabRefLookup[parent].m_Prefab][relative.m_BoneIndex.z];
					@float = subMesh.m_Position + math.rotate(subMesh.m_Rotation, @float);
					quaternion = math.mul(subMesh.m_Rotation, quaternion);
				}
				return new Transform(@float, quaternion);
			}
		}
		return new Transform(relative.m_Position, relative.m_Rotation);
	}
```

- `public static GetTargetRotation(Game.Prefabs.AnimationClip& clip, System.Single def, System.Single prev) : System.Single`  

```csharp
public static float GetTargetRotation(in AnimationClip clip, float def, float prev)
	{
		return math.max(math.select(clip.m_TargetValue, def, clip.m_TargetValue == float.MinValue), prev + math.radians(1f));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_AnimatedSystem = base.World.GetOrCreateSystemManaged<AnimatedSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_InterpolateQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Relative>()
			},
			Any = new ComponentType[1] { ComponentType.ReadWrite<InterpolatedTransform>() },
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeList<PreCullingData> cullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies);
		JobHandle dependencies2;
		AnimatedSystem.AnimationData animationData = m_AnimatedSystem.GetAnimationData(out dependencies2);
		float3 cameraPosition = default(float3);
		float3 cameraDirection = default(float3);
		float4 lodParameters = default(float4);
		if (m_CameraUpdateSystem.TryGetLODParameters(out var lodParameters2))
		{
			cameraPosition = lodParameters2.cameraPosition;
			IGameCameraController activeCameraController = m_CameraUpdateSystem.activeCameraController;
			lodParameters = RenderingUtils.CalculateLodParameters(m_BatchDataSystem.GetLevelOfDetail(m_RenderingSystem.frameLod, activeCameraController), lodParameters2);
			cameraDirection = m_CameraUpdateSystem.activeViewer.forward;
		}
		UpdateRelativeTransformDataJob jobData = new UpdateRelativeTransformDataJob
		{
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RelativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Relative_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_VehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RO_BufferLookup, ref base.CheckedStateRef),
			m_BoneHistories = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_BoneHistory_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationMotions = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationMotion_RO_BufferLookup, ref base.CheckedStateRef),
			m_ActivityLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RW_BufferLookup, ref base.CheckedStateRef),
			m_PrevFrameIndex = m_PrevFrameIndex,
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_FrameDelta = m_RenderingSystem.frameDelta,
			m_LodParameters = lodParameters,
			m_CameraPosition = cameraPosition,
			m_CameraDirection = cameraDirection,
			m_RandomSeed = RandomSeed.Next(),
			m_CullingData = cullingData,
			m_AnimationData = animationData
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateQueryTransformDataJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StaticType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Static_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MeshGroupType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RelativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Relative_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_BoneHistories = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_BoneHistory_RO_BufferLookup, ref base.CheckedStateRef),
			m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RW_BufferLookup, ref base.CheckedStateRef),
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_LodParameters = lodParameters,
			m_CameraPosition = cameraPosition,
			m_CameraDirection = cameraDirection,
			m_CullingData = cullingData,
			m_AnimationData = animationData
		}, dependsOn: jobData.Schedule(cullingData, 16, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2)), query: m_InterpolateQuery);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		m_AnimatedSystem.AddAnimationWriter(jobHandle);
		base.Dependency = jobHandle;
		m_PrevFrameIndex = m_RenderingSystem.frameIndex;
	}
```

- `public static UpdateDrivingAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Unity.Mathematics.float3 velocity, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset) : System.Void`  

```csharp
public static void UpdateDrivingAnimationBody(Entity entity, in CharacterElement characterElement, DynamicBuffer<AnimationClip> clips, ref ComponentLookup<Human> humanLookup, ref BufferLookup<AnimationMotion> motionLookup, InterpolatedTransform oldTransform, InterpolatedTransform newTransform, ref Animated animated, ref Random random, float3 velocity, float steerAngle, AnimatedPropID propID, float updateFrameToSeconds, float speedDeltaFactor, float deltaTime, int updateFrameChanged, bool instantReset)
	{
		AnimationClip clip = default(AnimationClip);
		AnimationClip clip2 = default(AnimationClip);
		AnimationClip clip3 = default(AnimationClip);
		AnimationClip clip4 = default(AnimationClip);
		if (!instantReset)
		{
			clip = clips[animated.m_ClipIndexBody0];
			if (animated.m_ClipIndexBody0I != -1)
			{
				clip2 = clips[animated.m_ClipIndexBody0I];
			}
			if (animated.m_ClipIndexBody1 != -1)
			{
				clip3 = clips[animated.m_ClipIndexBody1];
			}
			if (animated.m_ClipIndexBody1I != -1)
			{
				clip4 = clips[animated.m_ClipIndexBody1I];
			}
		}
		float3 y = math.forward(newTransform.m_Rotation);
		float num = math.dot(velocity, y);
		float num2 = math.abs(steerAngle);
		float prev = math.radians(1f);
		ActivityType activityType = ((!(num >= 1f)) ? ActivityType.Standing : ActivityType.Driving);
		if (clip2.m_Activity == ActivityType.Driving)
		{
			float targetRotation = GetTargetRotation(in clip2, math.radians(10f), prev);
			if (num2 > targetRotation)
			{
				activityType = ActivityType.Driving;
			}
		}
		else if (clip4.m_Activity == ActivityType.Driving)
		{
			float targetRotation2 = GetTargetRotation(in clip4, math.radians(10f), prev);
			if (num2 > targetRotation2)
			{
				activityType = ActivityType.Driving;
			}
		}
		if (clip.m_Activity == ActivityType.Driving)
		{
			if (clip3.m_Activity == ActivityType.Driving)
			{
				if (activityType == ActivityType.Standing)
				{
					clip3.m_Activity = ActivityType.Standing;
				}
				else
				{
					clip.m_Activity = ActivityType.Standing;
				}
			}
			else if (clip3.m_Activity == ActivityType.None && activityType == ActivityType.Standing && clip.m_Type != AnimationType.Idle)
			{
				clip.m_Activity = ActivityType.Standing;
			}
		}
		bool flag = updateFrameChanged > 0 && ((clip.m_Activity != ActivityType.None && (clip.m_Activity != activityType || clip.m_Type == AnimationType.Start || clip.m_PropID != propID)) || (clip3.m_Activity != ActivityType.None && (clip3.m_Activity != activityType || clip3.m_Type == AnimationType.Start || clip3.m_PropID != propID)));
		if (flag && clip3.m_Type != AnimationType.None)
		{
			animated.m_ClipIndexBody0 = animated.m_ClipIndexBody1;
			animated.m_ClipIndexBody0I = animated.m_ClipIndexBody1I;
			animated.m_ClipIndexBody1 = -1;
			animated.m_ClipIndexBody1I = -1;
			animated.m_Time.x = animated.m_Time.y;
			animated.m_Time.y = 0f;
			animated.m_MovementSpeed.x = animated.m_MovementSpeed.y;
			animated.m_MovementSpeed.y = 0f;
			clip = clip3;
			clip2 = clip4;
			clip3 = default(AnimationClip);
			clip4 = default(AnimationClip);
			flag &= clip.m_Activity != activityType;
		}
		if (clip.m_Activity == ActivityType.None || ((clip.m_Activity == ActivityType.Driving || clip.m_Activity == ActivityType.Standing) && clip.m_Type != AnimationType.Start && clip.m_PropID == propID))
		{
			bool num3 = clip.m_Type == AnimationType.None;
			UpdateDrivingClips(targetActivity: num3 ? activityType : clip.m_Activity, entity: entity, clip: ref clip, clipI: ref clip2, clipIndex: ref animated.m_ClipIndexBody0, clipIndexI: ref animated.m_ClipIndexBody0I, movementSpeed: ref animated.m_MovementSpeed.x, interpolation: ref animated.m_Interpolation, clips: clips, humanLookup: ref humanLookup, steerAngle: steerAngle, propID: propID);
			if (num3)
			{
				animated.m_Time.x = random.NextFloat(clip.m_AnimationLength);
			}
		}
		if (flag || ((clip3.m_Activity == ActivityType.Driving || clip3.m_Activity == ActivityType.Standing) && clip3.m_Type != AnimationType.Start && clip3.m_PropID == propID))
		{
			bool num4 = clip3.m_Type == AnimationType.None;
			UpdateDrivingClips(targetActivity: num4 ? activityType : clip3.m_Activity, entity: entity, clip: ref clip3, clipI: ref clip4, clipIndex: ref animated.m_ClipIndexBody1, clipIndexI: ref animated.m_ClipIndexBody1I, movementSpeed: ref animated.m_MovementSpeed.y, interpolation: ref animated.m_Interpolation, clips: clips, humanLookup: ref humanLookup, steerAngle: steerAngle, propID: propID);
			if (num4)
			{
				if ((clip.m_Activity == ActivityType.Driving || clip.m_Activity == ActivityType.Standing) && clip.m_Type != AnimationType.Start && clip.m_PropID == propID)
				{
					animated.m_Time.y = animated.m_Time.x;
				}
				else
				{
					animated.m_Time.y = random.NextFloat(clip3.m_AnimationLength);
				}
			}
		}
		if (animated.m_ClipIndexBody1 != -1 && animated.m_MovementSpeed.y == 0f)
		{
			animated.m_Time.y += deltaTime;
		}
		if (animated.m_MovementSpeed.x == 0f)
		{
			animated.m_Time.x += deltaTime;
		}
	}
```

- `public static UpdateDrivingClips(Unity.Entities.Entity entity, Game.Prefabs.AnimationClip& clip, Game.Prefabs.AnimationClip& clipI, System.Int16& clipIndex, System.Int16& clipIndexI, System.Single& movementSpeed, System.Single& interpolation, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityType targetActivity) : System.Void`  

```csharp
public static void UpdateDrivingClips(Entity entity, ref AnimationClip clip, ref AnimationClip clipI, ref short clipIndex, ref short clipIndexI, ref float movementSpeed, ref float interpolation, DynamicBuffer<AnimationClip> clips, ref ComponentLookup<Human> humanLookup, float steerAngle, AnimatedPropID propID, ActivityType targetActivity)
	{
		float num = math.abs(steerAngle);
		float num2 = math.radians(1f);
		if (num > num2)
		{
			AnimationType animationType = ((steerAngle > 0f) ? AnimationType.RightMin : AnimationType.LeftMin);
			if (clipI.m_Type != animationType || clipI.m_Activity != ActivityType.Driving || clipI.m_PropID != propID)
			{
				ActivityCondition activityConditions = ObjectInterpolateSystem.GetActivityConditions(entity, ref humanLookup);
				ObjectInterpolateSystem.FindAnimationClip(clips, animationType, ActivityType.Driving, AnimationLayer.Body, propID, activityConditions, out clipI, out var index);
				clipIndexI = (short)index;
			}
			float targetRotation = GetTargetRotation(in clipI, math.radians(10f), num2);
			AnimationType animationType2 = AnimationType.Idle;
			ActivityType activity = targetActivity;
			if (num > targetRotation)
			{
				animationType2 = ((steerAngle > 0f) ? AnimationType.RightMax : AnimationType.LeftMax);
				activity = ActivityType.Driving;
			}
			if (clip.m_Type != animationType2 || clip.m_Activity != targetActivity || clip.m_PropID != propID)
			{
				ActivityCondition activityConditions2 = ObjectInterpolateSystem.GetActivityConditions(entity, ref humanLookup);
				ObjectInterpolateSystem.FindAnimationClip(clips, animationType2, activity, AnimationLayer.Body, propID, activityConditions2, out clip, out var index2);
				clipIndex = (short)index2;
				movementSpeed = 0f;
			}
			if (num > targetRotation)
			{
				float targetRotation2 = GetTargetRotation(in clip, math.radians(45f), targetRotation);
				interpolation = math.saturate(1f - (num - targetRotation) / (targetRotation2 - targetRotation));
			}
			else
			{
				interpolation = math.saturate((num - num2) / (targetRotation - num2));
			}
		}
		else
		{
			if (clip.m_Type != AnimationType.Idle || clip.m_Activity != targetActivity || clip.m_PropID != propID)
			{
				ActivityCondition activityConditions3 = ObjectInterpolateSystem.GetActivityConditions(entity, ref humanLookup);
				ObjectInterpolateSystem.FindAnimationClip(clips, AnimationType.Idle, targetActivity, AnimationLayer.Body, propID, activityConditions3, out clip, out var index3);
				clipIndex = (short)index3;
				movementSpeed = 0f;
			}
			interpolation = 0f;
			clipIndexI = -1;
			clipI = default(AnimationClip);
		}
	}
```


## Nested types

- `Game.Rendering.RelativeObjectSystem+UpdateRelativeTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+UpdateQueryTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+TypeHandle`  

