# Game.Rendering.ObjectInterpolateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectInterpolateSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_InterpolateQuery;
    private System.UInt32 m_PrevFrameIndex;
    private Game.Rendering.ObjectInterpolateSystem+TypeHandle __TypeHandle;

    public ObjectInterpolateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void AddMotionOffset(Game.Prefabs.AnimationMotion& motion, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Unity.Mathematics.int2 range, Game.Rendering.BlendWeight weight);
    private static System.Single AnimateIntensity(Game.Prefabs.ProceduralLight proceduralLight, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, System.UInt32 frame, System.Single frameTime, System.Single intensity);
    private static System.Single AnimateIntensity(Game.Prefabs.SignalGroupMask signalGroupMask, System.Int32 signalAnimationIndex, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, System.UInt32 frame, System.Single frameTime, System.Single intensity);
    private static System.Void AnimateInterpolatedBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Unity.Entities.DynamicBuffer<Game.Rendering.Momentum> momentums, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Prefabs.PrefabRef prefabRef, Game.Rendering.Skeleton& skeleton, Unity.Mathematics.quaternion swayRotation, System.Single swayOffset, System.Single steeringRadius, System.Single pivotOffset, System.Int32 index, System.Single deltaTime, Unity.Entities.Entity entity, System.Boolean instantReset, System.UInt32 frameIndex, System.Single frameTime, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Common.PointOfInterest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pointOfInterests, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree);
    private static System.Void AnimateInterpolatedLight(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralLight> proceduralLights, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Entities.DynamicBuffer<Game.Rendering.LightState> lights, Game.Objects.TransformFlags transformFlags, Unity.Mathematics.Random pseudoRandom, Game.Rendering.Emissive& emissive, System.Int32 index, System.UInt32 frame, System.Single frameTime, System.Single deltaTime, System.Boolean instantReset);
    public static System.Void AnimateLight(Game.Prefabs.ProceduralLight proceduralLight, Game.Rendering.Emissive& emissive, Game.Rendering.LightState& light, System.Single deltaTime, System.Single targetIntensity, System.Boolean instantReset);
    public static System.Void AnimateLight(Game.Prefabs.ProceduralLight proceduralLight, Game.Rendering.Emissive& emissive, Game.Rendering.LightState& light, System.Single deltaTime, Unity.Mathematics.float2 target, System.Boolean instantReset);
    private static System.Void AnimateMovingBone(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.float3 moveDirection, System.Single targetOffset, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimatePantographBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, System.Int32 index, System.Single deltaTime, System.Boolean active, System.Boolean instantReset, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree);
    private static System.Void AnimateRotatingBoneX(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimateRotatingBoneX(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimateRotatingBoneY(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimateRotatingBoneY(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimateRotatingBoneZ(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Void AnimateRotatingBoneZ(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset);
    private static System.Single CalculateSteeringRadius(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Skeleton& skeleton, Game.Prefabs.CarData carData);
    public static Game.Rendering.InterpolatedTransform CalculateTransform(Game.Objects.TransformFrame frame1, Game.Objects.TransformFrame frame2, System.Single framePosition);
    public static System.Void CalculateUpdateFrames(System.UInt32 simulationFrameIndex, System.Single simulationFrameTime, System.UInt32 updateFrameIndex, System.UInt32& updateFrame1, System.UInt32& updateFrame2, System.Single& framePosition);
    public static System.Void CalculateUpdateFrames(System.UInt32 simulationFrameIndex, System.UInt32 prevSimulationFrameIndex, System.Single simulationFrameTime, System.UInt32 updateFrameIndex, System.UInt32& updateFrame1, System.UInt32& updateFrame2, System.Single& framePosition, System.Int32& updateFrameChanged);
    public static System.Boolean FindAnimationClip(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Prefabs.AnimationType type, Game.Prefabs.ActivityType activity, Game.Prefabs.AnimationLayer animationLayer, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Game.Prefabs.AnimationClip& clip, System.Int32& index);
    private static System.Single FindCatenaryHeight(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Single defaultHeight, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree);
    private static System.Boolean FindChildBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, System.Int32 index, System.Int32& childIndex);
    public static Game.Prefabs.ActivityCondition GetActivityConditions(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup);
    public static System.Void GetClipType(Game.Prefabs.AnimationClip clip, Game.Objects.TransformState state, System.Single movementDelta, System.Single speedDeltaFactor, Game.Prefabs.AnimationType& type, Game.Prefabs.ActivityType& activity);
    public static System.Single GetInitialTime(Unity.Mathematics.Random& random, Game.Prefabs.AnimationClip& clip, System.Single movementSpeed, System.Single prevClipLength, System.Single prevMovementSpeed, System.Single prevTime);
    public static System.Single GetMovementSpeed(Game.Prefabs.CharacterElement& characterElement, Game.Prefabs.AnimationClip& clip, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup);
    public static Game.Rendering.AnimatedPropID GetPropID(Unity.Entities.Entity entity, Game.Prefabs.ActivityType activity, Unity.Entities.ComponentLookup`1[[Game.Creatures.CurrentVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentVehicleLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& activityLocationLookup);
    public static System.Single GetUpdateFrameTransition(System.Single framePosition);
    private static Unity.Mathematics.quaternion LocalToObject(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.quaternion rotation);
    private static Unity.Mathematics.quaternion LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.quaternion rotation);
    private static Unity.Mathematics.float3 LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.float3 position);
    private static System.Void LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation);
    private static System.Void LookAtLocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, Game.Common.PointOfInterest pointOfInterest, System.Int32 parentIndex, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void SynchronizeMovementTime(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.Animated& animated, System.Single movementDelta, System.Single framePosition);
    public static System.Void UpdateInterpolatedAnimation(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, System.Single stateTimer, Game.Objects.TransformState state, Game.Prefabs.ActivityType activity, System.Single updateFrameToSeconds, System.Single speedDeltaFactor);
    public static System.Void UpdateInterpolatedAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.ComponentLookup`1[[Game.Creatures.CurrentVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentVehicleLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& activityLocationLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Game.Objects.TransformFrame frame0, Game.Objects.TransformFrame frame1, System.Single framePosition, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset);
    public static System.Void UpdateInterpolatedAnimationFace(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Game.Objects.TransformState state, Game.Prefabs.ActivityType activity, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset);
    private static System.Void UpdateSwaying(Game.Prefabs.SwayingData swayingData, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform& newTransform, Game.Rendering.Swaying& swaying, System.Single deltaTime, System.Single speedDeltaFactor, System.Boolean localSway, Unity.Mathematics.quaternion& swayRotation, System.Single& swayOffset);
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

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
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

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_InterpolateQuery`  

```csharp
private Unity.Entities.EntityQuery m_InterpolateQuery;
```

- `private System.UInt32 m_PrevFrameIndex`  

```csharp
private System.UInt32 m_PrevFrameIndex;
```

- `private Game.Rendering.ObjectInterpolateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ObjectInterpolateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectInterpolateSystem()`  

```csharp
[Preserve]
	public ObjectInterpolateSystem()
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

- `private static AddMotionOffset(Game.Prefabs.AnimationMotion& motion, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Unity.Mathematics.int2 range, Game.Rendering.BlendWeight weight) : System.Void`  

```csharp
private static void AddMotionOffset(ref AnimationMotion motion, DynamicBuffer<AnimationMotion> motions, int2 range, BlendWeight weight)
	{
		AnimationMotion animationMotion = motions[range.x + weight.m_Index + 1];
		motion.m_StartOffset += animationMotion.m_StartOffset * weight.m_Weight;
		motion.m_EndOffset += animationMotion.m_EndOffset * weight.m_Weight;
	}
```

- `private static AnimateIntensity(Game.Prefabs.ProceduralLight proceduralLight, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, System.UInt32 frame, System.Single frameTime, System.Single intensity) : System.Single`  

```csharp
private static float AnimateIntensity(SignalGroupMask signalGroupMask, int signalAnimationIndex, DynamicBuffer<LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, uint frame, float frameTime, float intensity)
	{
		if (signalAnimationIndex >= 0 && lightAnimations.IsCreated)
		{
			LightAnimation lightAnimation = lightAnimations[signalAnimationIndex];
			float num = (float)((frame + pseudoRandom.NextUInt(lightAnimation.m_DurationFrames)) % lightAnimation.m_DurationFrames) + frameTime;
			intensity *= lightAnimation.m_SignalAnimation.Evaluate(signalGroupMask, num / (float)lightAnimation.m_DurationFrames);
		}
		return intensity;
	}
```

- `private static AnimateIntensity(Game.Prefabs.SignalGroupMask signalGroupMask, System.Int32 signalAnimationIndex, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, System.UInt32 frame, System.Single frameTime, System.Single intensity) : System.Single`  

```csharp
private static float AnimateIntensity(SignalGroupMask signalGroupMask, int signalAnimationIndex, DynamicBuffer<LightAnimation> lightAnimations, Unity.Mathematics.Random pseudoRandom, uint frame, float frameTime, float intensity)
	{
		if (signalAnimationIndex >= 0 && lightAnimations.IsCreated)
		{
			LightAnimation lightAnimation = lightAnimations[signalAnimationIndex];
			float num = (float)((frame + pseudoRandom.NextUInt(lightAnimation.m_DurationFrames)) % lightAnimation.m_DurationFrames) + frameTime;
			intensity *= lightAnimation.m_SignalAnimation.Evaluate(signalGroupMask, num / (float)lightAnimation.m_DurationFrames);
		}
		return intensity;
	}
```

- `private static AnimateInterpolatedBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Unity.Entities.DynamicBuffer<Game.Rendering.Momentum> momentums, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Prefabs.PrefabRef prefabRef, Game.Rendering.Skeleton& skeleton, Unity.Mathematics.quaternion swayRotation, System.Single swayOffset, System.Single steeringRadius, System.Single pivotOffset, System.Int32 index, System.Single deltaTime, Unity.Entities.Entity entity, System.Boolean instantReset, System.UInt32 frameIndex, System.Single frameTime, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Common.PointOfInterest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pointOfInterests, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree) : System.Void`  

```csharp
private static void AnimateInterpolatedBone(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, DynamicBuffer<Momentum> momentums, InterpolatedTransform oldTransform, InterpolatedTransform newTransform, PrefabRef prefabRef, ref Skeleton skeleton, quaternion swayRotation, float swayOffset, float steeringRadius, float pivotOffset, int index, float deltaTime, Entity entity, bool instantReset, uint frameIndex, float frameTime, ref Unity.Mathematics.Random random, ref ComponentLookup<PointOfInterest> pointOfInterests, ref ComponentLookup<Curve> curveDatas, ref ComponentLookup<PrefabRef> prefabRefDatas, ref ComponentLookup<UtilityLaneData> prefabUtilityLaneDatas, ref ComponentLookup<ObjectGeometryData> prefabObjectGeometryDatas, ref NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree)
	{
		ProceduralBone proceduralBone = proceduralBones[index];
		Momentum momentum = default(Momentum);
		int index2 = skeleton.m_BoneOffset + index;
		ref Bone reference = ref bones.ElementAt(index2);
		ref Momentum momentum2 = ref momentum;
		if (momentums.IsCreated)
		{
			momentum2 = ref momentums.ElementAt(index2);
		}
		switch (proceduralBone.m_Type)
		{
		case BoneType.RollingTire:
		{
			float3 float6 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x3 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - float6;
			float3 y3 = math.forward(newTransform.m_Rotation);
			float num9 = math.dot(x3, y3) / math.max(0.01f, proceduralBone.m_ObjectPosition.y);
			float2 yz = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation)).yz;
			float angle2 = num9 - math.atan2(yz.x, yz.y);
			float3 float7 = math.mul(swayRotation, proceduralBone.m_Position);
			float7.y += swayOffset;
			quaternion quaternion3 = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle2));
			skeleton.m_CurrentUpdated |= !reference.m_Position.Equals(float7) | !reference.m_Rotation.Equals(quaternion3);
			reference.m_Position = float7;
			reference.m_Rotation = quaternion3;
			break;
		}
		case BoneType.SteeringTire:
		{
			float3 float18 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x10 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - float18;
			float3 float19 = math.mul(newTransform.m_Rotation, math.right());
			float3 float20 = math.forward(newTransform.m_Rotation);
			float num22 = math.dot(x10, float20);
			float num23 = math.dot(x10, float19);
			num22 += math.select(0.001f, -0.001f, num22 < 0f);
			float3 float21 = math.normalizesafe(float20 * num22 + float19 * num23);
			float21 = math.select(float21, -float21, num22 < 0f);
			float num24 = math.dot(x10, float21) / math.max(0.01f, proceduralBone.m_ObjectPosition.y);
			quaternion q = math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation);
			float3 float22 = math.forward(q);
			float num25 = math.length(float22.xz);
			float angle6 = num24 - math.atan2(x: math.select(num25, 0f - num25, float22.z < 0f), y: float22.y);
			float num27;
			if (steeringRadius == 0f)
			{
				float num26 = math.asin(math.dot(float19, float21));
				num27 = math.asin(math.mul(q, math.left()).z);
				float num28 = math.length(x10) / math.max(0.01f, proceduralBone.m_ObjectPosition.y);
				num27 += math.clamp(num26 - num27, 0f - num28, num28);
			}
			else
			{
				num27 = math.atan((proceduralBone.m_ObjectPosition.z - pivotOffset) / (steeringRadius - proceduralBone.m_ObjectPosition.x));
			}
			float3 float23 = math.mul(swayRotation, proceduralBone.m_Position);
			float23.y += swayOffset;
			quaternion quaternion9 = math.mul(proceduralBone.m_Rotation, math.mul(quaternion.RotateY(num27), quaternion.RotateX(angle6)));
			skeleton.m_CurrentUpdated |= !reference.m_Position.Equals(float23) | !reference.m_Rotation.Equals(quaternion9);
			reference.m_Position = float23;
			reference.m_Rotation = quaternion9;
			break;
		}
		case BoneType.SuspensionMovement:
		{
			if (FindChildBone(proceduralBones, index, out var childIndex3))
			{
				ProceduralBone proceduralBone3 = proceduralBones[childIndex3];
				float3 position5 = proceduralBone.m_Position;
				position5.z += math.mul(swayRotation, proceduralBone3.m_ObjectPosition).y - proceduralBone3.m_ObjectPosition.y;
				position5.z += swayOffset;
				skeleton.m_CurrentUpdated |= !reference.m_Position.Equals(position5);
				reference.m_Position = position5;
			}
			break;
		}
		case BoneType.SteeringRotation:
		{
			if (FindChildBone(proceduralBones, index, out var childIndex4))
			{
				ProceduralBone proceduralBone4 = proceduralBones[childIndex4];
				if (FindChildBone(proceduralBones, childIndex4, out var childIndex5))
				{
					proceduralBone4 = proceduralBones[childIndex5];
				}
				float num20;
				if (steeringRadius == 0f)
				{
					float3 float14 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone4.m_ObjectPosition);
					float3 x9 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone4.m_ObjectPosition) - float14;
					float3 float15 = math.mul(newTransform.m_Rotation, math.right());
					float3 float16 = math.forward(newTransform.m_Rotation);
					float num17 = math.dot(x9, float16);
					float num18 = math.dot(x9, float15);
					num17 += math.select(0.001f, -0.001f, num17 < 0f);
					float3 float17 = math.normalizesafe(float16 * num17 + float15 * num18);
					float17 = math.select(float17, -float17, num17 < 0f);
					float num19 = math.asin(math.dot(float15, float17));
					num20 = math.asin(math.mul(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation), math.right()).y);
					float num21 = math.length(x9) / math.max(0.01f, proceduralBone4.m_ObjectPosition.y);
					num20 += math.clamp(num19 - num20, 0f - num21, num21);
				}
				else
				{
					num20 = math.atan((proceduralBone4.m_ObjectPosition.z - pivotOffset) / (steeringRadius - proceduralBone4.m_ObjectPosition.x));
				}
				quaternion quaternion7 = math.mul(proceduralBone.m_Rotation, quaternion.RotateZ(num20));
				skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion7);
				reference.m_Rotation = quaternion7;
			}
			break;
		}
		case BoneType.SuspensionRotation:
		{
			if (FindChildBone(proceduralBones, index, out var childIndex6))
			{
				ProceduralBone proceduralBone5 = proceduralBones[childIndex6];
				float angle5 = 0f - math.atan((math.mul(swayRotation, proceduralBone5.m_ObjectPosition).y - proceduralBone5.m_ObjectPosition.y + swayOffset) / proceduralBone5.m_Position.z);
				quaternion quaternion8 = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle5));
				skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion8);
				reference.m_Rotation = quaternion8;
			}
			break;
		}
		case BoneType.FixedRotation:
		{
			ProceduralBone proceduralBone6 = proceduralBones[proceduralBone.m_ParentIndex];
			Bone bone = bones.ElementAt(skeleton.m_BoneOffset + proceduralBone.m_ParentIndex);
			quaternion quaternion10 = math.mul(math.inverse(LocalToObject(proceduralBones, bones, skeleton, proceduralBone6.m_ParentIndex, bone.m_Rotation)), proceduralBone.m_ObjectRotation);
			skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion10);
			reference.m_Rotation = quaternion10;
			break;
		}
		case BoneType.FixedTire:
		{
			float3 float13 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x7 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - float13;
			float3 x8 = math.rotate(LocalToWorld(proceduralBones, bones, newTransform.ToTransform(), skeleton, proceduralBone.m_ParentIndex, proceduralBone.m_Rotation), math.right());
			float3 y6 = math.rotate(newTransform.m_Rotation, math.up());
			float3 y7 = math.normalizesafe(math.cross(x8, y6));
			float num16 = math.dot(x7, y7) / math.max(0.01f, proceduralBone.m_ObjectPosition.y);
			float2 yz3 = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation)).yz;
			float angle4 = num16 - math.atan2(yz3.x, yz3.y);
			quaternion quaternion6 = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle4));
			skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion6);
			reference.m_Rotation = quaternion6;
			break;
		}
		case BoneType.DebugMovement:
		{
			float3 position3 = proceduralBone.m_Position;
			float num8 = ((float)(frameIndex & 0xFF) + frameTime) * (3f / 128f);
			if (num8 < 1f)
			{
				position3.x += math.smoothstep(0f, 1f, num8);
			}
			else if (num8 < 2f)
			{
				position3.x += math.smoothstep(2f, 1f, num8);
			}
			else if (num8 < 3f)
			{
				position3.y += math.smoothstep(2f, 3f, num8);
			}
			else if (num8 < 4f)
			{
				position3.y += math.smoothstep(4f, 3f, num8);
			}
			else if (num8 < 5f)
			{
				position3.z += math.smoothstep(4f, 5f, num8);
			}
			else
			{
				position3.z += math.smoothstep(6f, 5f, num8);
			}
			skeleton.m_CurrentUpdated |= !reference.m_Position.Equals(position3);
			reference.m_Position = position3;
			break;
		}
		case BoneType.RollingRotation:
		{
			float3 float8 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x4 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - float8;
			float3 x5 = math.rotate(LocalToWorld(proceduralBones, bones, newTransform.ToTransform(), skeleton, proceduralBone.m_ParentIndex, proceduralBone.m_Rotation), math.right());
			float3 y4 = math.rotate(newTransform.m_Rotation, math.up());
			float3 y5 = math.normalizesafe(math.cross(x5, y4));
			float num10 = math.dot(x4, y5) * proceduralBone.m_Speed;
			float2 yz2 = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation)).yz;
			float angle3 = num10 - math.atan2(yz2.x, yz2.y);
			quaternion quaternion4 = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle3));
			skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion4);
			reference.m_Rotation = quaternion4;
			break;
		}
		case BoneType.PropellerRotation:
		{
			float3 @float = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - @float;
			float3 y = math.rotate(LocalToWorld(proceduralBones, bones, newTransform.ToTransform(), skeleton, proceduralBone.m_ParentIndex, proceduralBone.m_Rotation), math.up());
			float num = math.dot(x, y) * proceduralBone.m_Speed;
			float2 xz = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation)).xz;
			float angle = num + math.atan2(xz.x, xz.y);
			quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateY(angle));
			skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion);
			reference.m_Rotation = quaternion;
			break;
		}
		case BoneType.PoweredRotation:
		case BoneType.OperatingRotation:
		{
			float speed = proceduralBone.m_Speed;
			AnimateRotatingBoneY(proceduralBone, ref skeleton, ref reference, ref momentum2, ref random, speed, deltaTime, instantReset);
			break;
		}
		case BoneType.PropellerAngle:
		{
			float3 float2 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
			float3 x2 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition) - float2;
			float3 float3 = math.mul(newTransform.m_Rotation, math.right());
			float3 float4 = math.forward(newTransform.m_Rotation);
			float num2 = math.dot(x2, float4);
			float num3 = math.dot(x2, float3);
			num2 += math.select(0.001f, -0.001f, num2 < 0f);
			float3 y2 = math.normalizesafe(float4 * num2 + float3 * num3);
			float num4 = math.atan2(math.dot(float3, y2), math.dot(float4, y2));
			float3 float5 = math.mul(reference.m_Rotation, math.forward());
			float num5 = math.atan2(float5.x, float5.z);
			float num6 = math.length(x2) * proceduralBone.m_Speed;
			float num7 = num4 - num5;
			num7 = math.select(num7, num7 - MathF.PI, num7 > MathF.PI);
			num7 = math.select(num7, num7 + MathF.PI, num7 < -MathF.PI);
			num5 += math.clamp(num7, 0f - num6, num6);
			quaternion quaternion2 = math.mul(quaternion.RotateY(num5), proceduralBone.m_Rotation);
			skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion2);
			reference.m_Rotation = quaternion2;
			break;
		}
		case BoneType.PantographRotation:
		{
			bool active = (newTransform.m_Flags & TransformFlags.Pantograph) != 0;
			AnimatePantographBone(proceduralBones, bones, newTransform.ToTransform(), prefabRef, proceduralBone, ref skeleton, ref reference, index, deltaTime, active, instantReset, ref curveDatas, ref prefabRefDatas, ref prefabUtilityLaneDatas, ref prefabObjectGeometryDatas, ref laneSearchTree);
			break;
		}
		case BoneType.SteeringSuspension:
		{
			if (FindChildBone(proceduralBones, index, out var childIndex))
			{
				ProceduralBone proceduralBone2 = proceduralBones[childIndex];
				if (FindChildBone(proceduralBones, childIndex, out var childIndex2))
				{
					proceduralBone2 = proceduralBones[childIndex2];
				}
				float num14;
				if (steeringRadius == 0f)
				{
					float3 float9 = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone2.m_ObjectPosition);
					float3 x6 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone2.m_ObjectPosition) - float9;
					float3 float10 = math.mul(newTransform.m_Rotation, math.right());
					float3 float11 = math.forward(newTransform.m_Rotation);
					float num11 = math.dot(x6, float11);
					float num12 = math.dot(x6, float10);
					num11 += math.select(0.001f, -0.001f, num11 < 0f);
					float3 float12 = math.normalizesafe(float11 * num11 + float10 * num12);
					float12 = math.select(float12, -float12, num11 < 0f);
					float num13 = math.asin(math.dot(float10, float12));
					num14 = math.asin(math.mul(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation), math.left()).z);
					float num15 = math.length(x6) / math.max(0.01f, proceduralBone2.m_ObjectPosition.y);
					num14 += math.clamp(num13 - num14, 0f - num15, num15);
				}
				else
				{
					num14 = math.atan((proceduralBone2.m_ObjectPosition.z - pivotOffset) / (steeringRadius - proceduralBone2.m_ObjectPosition.x));
				}
				quaternion quaternion5 = math.mul(proceduralBone.m_Rotation, quaternion.RotateY(num14));
				float3 position4 = proceduralBone.m_Position;
				position4.z += math.mul(swayRotation, proceduralBone2.m_ObjectPosition).y - proceduralBone2.m_ObjectPosition.y;
				position4.z += swayOffset;
				skeleton.m_CurrentUpdated |= !reference.m_Rotation.Equals(quaternion5) | !reference.m_Position.Equals(position4);
				reference.m_Rotation = quaternion5;
				reference.m_Position = position4;
			}
			break;
		}
		case BoneType.LookAtRotation:
		case BoneType.LookAtRotationSide:
		{
			if (pointOfInterests.TryGetComponent(entity, out var componentData2) && componentData2.m_IsValid)
			{
				float3 position2 = proceduralBone.m_Position;
				quaternion rotation2 = proceduralBone.m_Rotation;
				LocalToWorld(proceduralBones, bones, newTransform.ToTransform(), skeleton, proceduralBone.m_ParentIndex, ref position2, ref rotation2);
				float3 v2 = componentData2.m_Position - position2;
				v2 = math.mul(math.inverse(rotation2), v2);
				v2.xz = math.select(v2.xz, MathUtils.Right(v2.xz), proceduralBone.m_Type == BoneType.LookAtRotationSide);
				v2 = math.select(v2, -v2, proceduralBone.m_Speed < 0f);
				float targetSpeed2 = math.abs(proceduralBone.m_Speed);
				AnimateRotatingBoneY(proceduralBone, ref skeleton, ref reference, ref momentum2, ref random, v2.xz, targetSpeed2, deltaTime, instantReset);
			}
			else
			{
				AnimateRotatingBoneY(proceduralBone, ref skeleton, ref reference, ref momentum2, ref random, 0f, deltaTime, instantReset);
			}
			break;
		}
		case BoneType.LookAtAim:
		case BoneType.LookAtAimForward:
		{
			if (pointOfInterests.TryGetComponent(entity, out var componentData) && componentData.m_IsValid)
			{
				float3 position = proceduralBone.m_Position;
				quaternion rotation = proceduralBone.m_Rotation;
				LookAtLocalToWorld(proceduralBones, bones, newTransform.ToTransform(), skeleton, componentData, proceduralBone.m_ParentIndex, ref position, ref rotation);
				float3 v = componentData.m_Position - position;
				v = math.mul(math.inverse(rotation), v);
				v.yz = math.select(v.yz, MathUtils.Left(v.yz), proceduralBone.m_Type == BoneType.LookAtAimForward);
				v = math.select(v, -v, proceduralBone.m_Speed < 0f);
				float targetSpeed = math.abs(proceduralBone.m_Speed);
				AnimateRotatingBoneX(proceduralBone, ref skeleton, ref reference, ref momentum2, ref random, v.yz, targetSpeed, deltaTime, instantReset);
			}
			else
			{
				AnimateRotatingBoneX(proceduralBone, ref skeleton, ref reference, ref momentum2, ref random, 0f, deltaTime, instantReset);
			}
			break;
		}
		case BoneType.TrafficBarrierDirection:
		case BoneType.VehicleConnection:
		case BoneType.TrainBogie:
		case BoneType.LengthwiseLookAtRotation:
		case BoneType.WorkingRotation:
		case BoneType.TimeRotation:
		case BoneType.LookAtMovementX:
		case BoneType.LookAtMovementY:
		case BoneType.LookAtMovementZ:
		case BoneType.RotationXFromMovementY:
		case BoneType.ScaledMovement:
			break;
		}
	}
```

- `private static AnimateInterpolatedLight(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralLight> proceduralLights, Unity.Entities.DynamicBuffer<Game.Prefabs.LightAnimation> lightAnimations, Unity.Entities.DynamicBuffer<Game.Rendering.LightState> lights, Game.Objects.TransformFlags transformFlags, Unity.Mathematics.Random pseudoRandom, Game.Rendering.Emissive& emissive, System.Int32 index, System.UInt32 frame, System.Single frameTime, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateInterpolatedLight(DynamicBuffer<ProceduralLight> proceduralLights, DynamicBuffer<LightAnimation> lightAnimations, DynamicBuffer<LightState> lights, TransformFlags transformFlags, Unity.Mathematics.Random pseudoRandom, ref Emissive emissive, int index, uint frame, float frameTime, float deltaTime, bool instantReset)
	{
		ProceduralLight proceduralLight = proceduralLights[index];
		int index2 = emissive.m_LightOffset + index;
		ref LightState light = ref lights.ElementAt(index2);
		switch (proceduralLight.m_Purpose)
		{
		case EmissiveProperties.Purpose.DaytimeRunningLight:
		case EmissiveProperties.Purpose.DaytimeRunningLightAlt:
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, 1f, instantReset);
			break;
		case EmissiveProperties.Purpose.RearLight:
		{
			float targetIntensity5 = math.select(0f, 1f, (transformFlags & TransformFlags.RearLights) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity5, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.Headlight_LowBeam:
		case EmissiveProperties.Purpose.TaxiLights:
		case EmissiveProperties.Purpose.SearchLightsFront:
		{
			float targetIntensity13 = math.select(0f, 1f, (transformFlags & TransformFlags.MainLights) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity13, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.Headlight_HighBeam:
		case EmissiveProperties.Purpose.LandingLights:
		{
			float targetIntensity4 = math.select(0f, 1f, (transformFlags & TransformFlags.ExtraLights) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity4, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.TurnSignalLeft:
		{
			float targetIntensity10 = 0f;
			if ((transformFlags & TransformFlags.TurningLeft) != 0)
			{
				targetIntensity10 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity10, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.TurnSignalRight:
		{
			float targetIntensity14 = 0f;
			if ((transformFlags & TransformFlags.TurningRight) != 0)
			{
				targetIntensity14 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity14, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.BrakeLight:
		{
			float targetIntensity8 = math.select(0f, 1f, (transformFlags & TransformFlags.Braking) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity8, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.DaytimeRunningLightLeft:
		{
			float targetIntensity7 = math.select(1f, 0f, (transformFlags & TransformFlags.TurningLeft) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity7, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.DaytimeRunningLightRight:
		{
			float targetIntensity9 = math.select(1f, 0f, (transformFlags & TransformFlags.TurningRight) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity9, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.BrakeAndTurnSignalLeft:
		{
			float targetIntensity6 = math.select(0f, 1f, (transformFlags & TransformFlags.Braking) != 0);
			if ((transformFlags & TransformFlags.TurningLeft) != 0)
			{
				targetIntensity6 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity6, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.BrakeAndTurnSignalRight:
		{
			float targetIntensity16 = math.select(0f, 1f, (transformFlags & TransformFlags.Braking) != 0);
			if ((transformFlags & TransformFlags.TurningRight) != 0)
			{
				targetIntensity16 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity16, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.ReverseLight:
		{
			float targetIntensity15 = math.select(0f, 1f, (transformFlags & TransformFlags.Reversing) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity15, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.Emergency1:
		case EmissiveProperties.Purpose.Emergency2:
		case EmissiveProperties.Purpose.Emergency3:
		case EmissiveProperties.Purpose.Emergency4:
		case EmissiveProperties.Purpose.Emergency5:
		case EmissiveProperties.Purpose.Emergency6:
		case EmissiveProperties.Purpose.RearAlarmLights:
		case EmissiveProperties.Purpose.FrontAlarmLightsLeft:
		case EmissiveProperties.Purpose.FrontAlarmLightsRight:
		case EmissiveProperties.Purpose.Warning1:
		case EmissiveProperties.Purpose.Warning2:
		case EmissiveProperties.Purpose.Emergency7:
		case EmissiveProperties.Purpose.Emergency8:
		case EmissiveProperties.Purpose.Emergency9:
		case EmissiveProperties.Purpose.Emergency10:
		case EmissiveProperties.Purpose.AntiCollisionLightsRed:
		case EmissiveProperties.Purpose.AntiCollisionLightsWhite:
		{
			float targetIntensity12 = 0f;
			if ((transformFlags & TransformFlags.WarningLights) != 0)
			{
				targetIntensity12 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity12, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.CollectionLights:
		case EmissiveProperties.Purpose.TaxiSign:
		case EmissiveProperties.Purpose.WorkLights:
		case EmissiveProperties.Purpose.SearchLights360:
		{
			float targetIntensity11 = math.select(0f, 1f, (transformFlags & TransformFlags.WorkLights) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity11, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.SignalGroup1:
		case EmissiveProperties.Purpose.SignalGroup2:
		case EmissiveProperties.Purpose.SignalGroup3:
		case EmissiveProperties.Purpose.SignalGroup4:
		case EmissiveProperties.Purpose.SignalGroup5:
		case EmissiveProperties.Purpose.SignalGroup6:
		case EmissiveProperties.Purpose.SignalGroup7:
		case EmissiveProperties.Purpose.SignalGroup8:
		case EmissiveProperties.Purpose.SignalGroup9:
		case EmissiveProperties.Purpose.SignalGroup10:
		case EmissiveProperties.Purpose.SignalGroup11:
		{
			int num = (int)(proceduralLight.m_Purpose - 12);
			SignalGroupMask signalGroupMask = (SignalGroupMask)(1 << num);
			float targetIntensity3 = 0f;
			if ((transformFlags & (TransformFlags.SignalAnimation1 | TransformFlags.SignalAnimation2)) != 0)
			{
				int num2 = 0;
				num2 |= (((transformFlags & TransformFlags.SignalAnimation1) != 0) ? 1 : 0);
				num2 |= (((transformFlags & TransformFlags.SignalAnimation2) != 0) ? 2 : 0);
				num2--;
				targetIntensity3 = AnimateIntensity(signalGroupMask, num2, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			}
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity3, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.NeonSign:
		case EmissiveProperties.Purpose.DecorativeLight:
		{
			float targetIntensity2 = AnimateIntensity(proceduralLight, lightAnimations, pseudoRandom, frame, frameTime, 1f);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity2, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.BoardingLightLeft:
		{
			float y2 = math.select(1f, 0f, (transformFlags & TransformFlags.BoardingLeft) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, new float2(1f, y2), instantReset);
			break;
		}
		case EmissiveProperties.Purpose.BoardingLightRight:
		{
			float y = math.select(1f, 0f, (transformFlags & TransformFlags.BoardingRight) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, new float2(1f, y), instantReset);
			break;
		}
		case EmissiveProperties.Purpose.Interior1:
		case EmissiveProperties.Purpose.Interior2:
		{
			float targetIntensity = math.select(0f, 0.003f, (transformFlags & TransformFlags.InteriorLights) != 0);
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, targetIntensity, instantReset);
			break;
		}
		case EmissiveProperties.Purpose.Clearance:
		case EmissiveProperties.Purpose.Dashboard:
		case EmissiveProperties.Purpose.Clearance2:
		case EmissiveProperties.Purpose.MarkerLights:
		case EmissiveProperties.Purpose.WingInspectionLights:
		case EmissiveProperties.Purpose.LogoLights:
		case EmissiveProperties.Purpose.PositionLightLeft:
		case EmissiveProperties.Purpose.PositionLightRight:
		case EmissiveProperties.Purpose.PositionLights:
		case EmissiveProperties.Purpose.NumberLight:
			AnimateLight(proceduralLight, ref emissive, ref light, deltaTime, 1f, instantReset);
			break;
		case EmissiveProperties.Purpose.TrafficLight_Red:
		case EmissiveProperties.Purpose.TrafficLight_Yellow:
		case EmissiveProperties.Purpose.TrafficLight_Green:
		case EmissiveProperties.Purpose.PedestrianLight_Stop:
		case EmissiveProperties.Purpose.PedestrianLight_Walk:
		case EmissiveProperties.Purpose.RailCrossing_Stop:
			break;
		}
	}
```

- `public static AnimateLight(Game.Prefabs.ProceduralLight proceduralLight, Game.Rendering.Emissive& emissive, Game.Rendering.LightState& light, System.Single deltaTime, System.Single targetIntensity, System.Boolean instantReset) : System.Void`  

```csharp
public static void AnimateLight(ProceduralLight proceduralLight, ref Emissive emissive, ref LightState light, float deltaTime, float2 target, bool instantReset)
	{
		float2 @float = new float2(light.m_Intensity, light.m_Color);
		float num = math.abs(deltaTime) * proceduralLight.m_ResponseSpeed;
		float2 float2 = math.select(math.clamp(target, @float - num, @float + num), target, instantReset);
		emissive.m_Updated |= math.any(float2 != @float);
		light.m_Intensity = float2.x;
		light.m_Color = float2.y;
	}
```

- `public static AnimateLight(Game.Prefabs.ProceduralLight proceduralLight, Game.Rendering.Emissive& emissive, Game.Rendering.LightState& light, System.Single deltaTime, Unity.Mathematics.float2 target, System.Boolean instantReset) : System.Void`  

```csharp
public static void AnimateLight(ProceduralLight proceduralLight, ref Emissive emissive, ref LightState light, float deltaTime, float2 target, bool instantReset)
	{
		float2 @float = new float2(light.m_Intensity, light.m_Color);
		float num = math.abs(deltaTime) * proceduralLight.m_ResponseSpeed;
		float2 float2 = math.select(math.clamp(target, @float - num, @float + num), target, instantReset);
		emissive.m_Updated |= math.any(float2 != @float);
		light.m_Intensity = float2.x;
		light.m_Color = float2.y;
	}
```

- `private static AnimateMovingBone(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.float3 moveDirection, System.Single targetOffset, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateMovingBone(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, float3 moveDirection, float targetOffset, float targetSpeed, float deltaTime, bool instantReset)
	{
		float3 position = proceduralBone.m_Position;
		if (instantReset)
		{
			position += moveDirection * targetOffset;
			momentum.m_Momentum = 0f;
		}
		else
		{
			float num = math.dot(bone.m_Position - position, moveDirection);
			float num2 = targetOffset - num;
			targetSpeed = math.select(targetSpeed, 0f - targetSpeed, num2 < 0f);
			float num3 = math.sqrt(math.abs(num2 * proceduralBone.m_Acceleration));
			targetSpeed = math.clamp(targetSpeed, 0f - num3, num3);
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num4 = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num4, num4);
			position += moveDirection * (num + momentum.m_Momentum * deltaTime);
		}
		skeleton.m_CurrentUpdated |= !bone.m_Position.Equals(position);
		bone.m_Position = position;
	}
```

- `private static AnimatePantographBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, System.Int32 index, System.Single deltaTime, System.Boolean active, System.Boolean instantReset, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree) : System.Void`  

```csharp
private static void AnimatePantographBone(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Transform transform, PrefabRef prefabRef, ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, int index, float deltaTime, bool active, bool instantReset, ref ComponentLookup<Curve> curveDatas, ref ComponentLookup<PrefabRef> prefabRefDatas, ref ComponentLookup<UtilityLaneData> prefabUtilityLaneDatas, ref ComponentLookup<ObjectGeometryData> prefabObjectGeometryDatas, ref NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree)
	{
		ProceduralBone proceduralBone2 = proceduralBones[proceduralBone.m_ParentIndex];
		quaternion quaternion2;
		int childIndex;
		if (proceduralBone2.m_Type == BoneType.PantographRotation)
		{
			Bone bone2 = bones.ElementAt(skeleton.m_BoneOffset + proceduralBone.m_ParentIndex);
			quaternion quaternion = math.mul(math.inverse(proceduralBone2.m_Rotation), bone2.m_Rotation);
			quaternion.value.x = 0f - quaternion.value.x;
			quaternion2 = math.mul(math.mul(quaternion, quaternion), proceduralBone.m_Rotation);
		}
		else if (FindChildBone(proceduralBones, index, out childIndex))
		{
			float num = 0f;
			if (active)
			{
				ProceduralBone proceduralBone3 = proceduralBones[childIndex];
				ObjectGeometryData objectGeometryData = prefabObjectGeometryDatas[prefabRef.m_Prefab];
				float3 objectPosition = proceduralBone.m_ObjectPosition;
				objectPosition.y = objectGeometryData.m_Bounds.max.y;
				objectPosition = ObjectUtils.LocalToWorld(transform, objectPosition);
				float num2 = math.length(proceduralBone3.m_Position.yz);
				if (proceduralBone3.m_Type == BoneType.PantographRotation && FindChildBone(proceduralBones, childIndex, out var childIndex2))
				{
					num2 += math.length(proceduralBones[childIndex2].m_Position.yz);
				}
				float defaultHeight = num2 * 0.38268343f;
				float num3 = FindCatenaryHeight(objectPosition, transform.m_Rotation, defaultHeight, ref curveDatas, ref prefabRefDatas, ref prefabUtilityLaneDatas, ref laneSearchTree);
				num = math.asin(math.min(0.9f, num3 / math.max(num2, 0.001f)));
				num = math.select(num, 0f - num, proceduralBone3.m_Position.z > 0f);
			}
			float2 yz = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation)).yz;
			float num4 = 0f - math.atan2(yz.x, yz.y);
			float num5 = proceduralBone.m_Speed * deltaTime;
			num = math.select(math.clamp(num, num4 - num5, num4 + num5), num, instantReset);
			quaternion2 = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(num));
		}
		else
		{
			quaternion2 = bone.m_Rotation;
		}
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion2);
		bone.m_Rotation = quaternion2;
	}
```

- `private static AnimateRotatingBoneX(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneX(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 yz = math.rotate(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation), math.up()).yz;
			angle = math.atan2(yz.y, yz.x) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static AnimateRotatingBoneX(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneX(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 yz = math.rotate(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation), math.up()).yz;
			angle = math.atan2(yz.y, yz.x) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateX(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static AnimateRotatingBoneY(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneY(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 xz = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation)).xz;
			angle = math.atan2(xz.x, xz.y) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateY(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static AnimateRotatingBoneY(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneY(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 xz = math.forward(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation)).xz;
			angle = math.atan2(xz.x, xz.y) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateY(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static AnimateRotatingBoneZ(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, Unity.Mathematics.float2 targetDir, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneZ(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 xy = math.rotate(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation), math.up()).xy;
			angle = math.atan2(0f - xy.x, xy.y) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateZ(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static AnimateRotatingBoneZ(Game.Prefabs.ProceduralBone proceduralBone, Game.Rendering.Skeleton& skeleton, Game.Rendering.Bone& bone, Game.Rendering.Momentum& momentum, Unity.Mathematics.Random& random, System.Single targetSpeed, System.Single deltaTime, System.Boolean instantReset) : System.Void`  

```csharp
private static void AnimateRotatingBoneZ(ProceduralBone proceduralBone, ref Skeleton skeleton, ref Bone bone, ref Momentum momentum, ref Unity.Mathematics.Random random, float targetSpeed, float deltaTime, bool instantReset)
	{
		float angle;
		if (instantReset)
		{
			momentum.m_Momentum = targetSpeed;
			angle = random.NextFloat(-MathF.PI, MathF.PI);
		}
		else
		{
			float valueToClamp = targetSpeed - momentum.m_Momentum;
			float num = math.abs(deltaTime * proceduralBone.m_Acceleration);
			momentum.m_Momentum += math.clamp(valueToClamp, 0f - num, num);
			float2 xy = math.rotate(math.mul(math.inverse(proceduralBone.m_Rotation), bone.m_Rotation), math.up()).xy;
			angle = math.atan2(0f - xy.x, xy.y) + momentum.m_Momentum * deltaTime;
		}
		quaternion quaternion = math.mul(proceduralBone.m_Rotation, quaternion.RotateZ(angle));
		skeleton.m_CurrentUpdated |= !bone.m_Rotation.Equals(quaternion);
		bone.m_Rotation = quaternion;
	}
```

- `private static CalculateSteeringRadius(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Skeleton& skeleton, Game.Prefabs.CarData carData) : System.Single`  

```csharp
private static float CalculateSteeringRadius(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, InterpolatedTransform oldTransform, InterpolatedTransform newTransform, ref Skeleton skeleton, CarData carData)
	{
		float num = float.PositiveInfinity;
		float num2 = -1f;
		float num3 = 0f;
		for (int i = 0; i < proceduralBones.Length; i++)
		{
			ProceduralBone proceduralBone = proceduralBones[i];
			int index = skeleton.m_BoneOffset + i;
			ref Bone reference = ref bones.ElementAt(index);
			BoneType type = proceduralBone.m_Type;
			ProceduralBone proceduralBone2;
			float3 @float;
			float3 float2;
			float num4;
			if (type != BoneType.SteeringTire)
			{
				if (type != BoneType.SteeringRotation)
				{
					if (type != BoneType.SteeringSuspension || !FindChildBone(proceduralBones, i, out var childIndex))
					{
						continue;
					}
					proceduralBone2 = proceduralBones[childIndex];
					if (FindChildBone(proceduralBones, childIndex, out var childIndex2))
					{
						proceduralBone2 = proceduralBones[childIndex2];
					}
					@float = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone2.m_ObjectPosition);
					float2 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone2.m_ObjectPosition);
					num4 = math.asin(math.mul(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation), math.left()).z);
				}
				else
				{
					if (!FindChildBone(proceduralBones, i, out var childIndex3))
					{
						continue;
					}
					proceduralBone2 = proceduralBones[childIndex3];
					if (FindChildBone(proceduralBones, childIndex3, out var childIndex4))
					{
						proceduralBone2 = proceduralBones[childIndex4];
					}
					@float = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone2.m_ObjectPosition);
					float2 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone2.m_ObjectPosition);
					num4 = math.asin(math.mul(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation), math.right()).y);
				}
			}
			else
			{
				@float = ObjectUtils.LocalToWorld(oldTransform.ToTransform(), proceduralBone.m_ObjectPosition);
				float2 = ObjectUtils.LocalToWorld(newTransform.ToTransform(), proceduralBone.m_ObjectPosition);
				proceduralBone2 = proceduralBone;
				num4 = math.asin(math.mul(math.mul(math.inverse(proceduralBone.m_Rotation), reference.m_Rotation), math.left()).z);
			}
			float2 x = new float2(proceduralBone2.m_ObjectPosition.x, proceduralBone2.m_ObjectPosition.z - carData.m_PivotOffset);
			x.y *= 0.5f;
			num3 = math.max(num3, math.csum(math.abs(x)));
			float3 x2 = float2 - @float;
			float3 float3 = math.mul(newTransform.m_Rotation, math.right());
			float3 float4 = math.forward(newTransform.m_Rotation);
			float num5 = math.dot(x2, float4);
			float num6 = math.dot(x2, float3);
			num5 += math.select(0.001f, -0.001f, num5 < 0f);
			float3 float5 = math.normalizesafe(float4 * num5 + float3 * num6);
			float5 = math.select(float5, -float5, num5 < 0f);
			float num7 = math.abs(math.dot(x2, float5));
			if (!(num7 <= num2))
			{
				num2 = num7;
				float num8 = math.asin(math.dot(float3, float5));
				float num9 = num7 / math.max(0.01f, proceduralBone2.m_ObjectPosition.y * 2f);
				num4 += math.clamp(num8 - num4, 0f - num9, num9);
				num = (proceduralBone2.m_ObjectPosition.z - carData.m_PivotOffset) / math.tan(num4) + proceduralBone2.m_ObjectPosition.x;
			}
		}
		num = math.select(num, num3, num < num3 && num >= 0f);
		return math.select(num, 0f - num3, num > 0f - num3 && num < 0f);
	}
```

- `public static CalculateTransform(Game.Objects.TransformFrame frame1, Game.Objects.TransformFrame frame2, System.Single framePosition) : Game.Rendering.InterpolatedTransform`  

```csharp
public static InterpolatedTransform CalculateTransform(TransformFrame frame1, TransformFrame frame2, float framePosition)
	{
		Bezier4x3 curve = new Bezier4x3(frame1.m_Position, frame1.m_Position + frame1.m_Velocity * (4f / 45f), frame2.m_Position - frame2.m_Velocity * (4f / 45f), frame2.m_Position);
		InterpolatedTransform result = default(InterpolatedTransform);
		result.m_Position = MathUtils.Position(curve, framePosition);
		result.m_Rotation = math.slerp(frame1.m_Rotation, frame2.m_Rotation, framePosition);
		result.m_Flags = ((framePosition >= 0.5f) ? frame2.m_Flags : frame1.m_Flags);
		return result;
	}
```

- `public static CalculateUpdateFrames(System.UInt32 simulationFrameIndex, System.Single simulationFrameTime, System.UInt32 updateFrameIndex, System.UInt32& updateFrame1, System.UInt32& updateFrame2, System.Single& framePosition) : System.Void`  

```csharp
public static void CalculateUpdateFrames(uint simulationFrameIndex, uint prevSimulationFrameIndex, float simulationFrameTime, uint updateFrameIndex, out uint updateFrame1, out uint updateFrame2, out float framePosition, out int updateFrameChanged)
	{
		uint num = simulationFrameIndex - updateFrameIndex - 32;
		uint num2 = prevSimulationFrameIndex - updateFrameIndex - 32;
		updateFrame1 = num >> 4;
		uint num3 = num2 >> 4;
		updateFrameChanged = math.select(0, math.select(-1, 1, updateFrame1 > num3), updateFrame1 != num3);
		updateFrame1 &= 3u;
		updateFrame2 = (updateFrame1 + 1) & 3;
		framePosition = ((float)(num & 0xF) + simulationFrameTime) * 0.0625f;
	}
```

- `public static CalculateUpdateFrames(System.UInt32 simulationFrameIndex, System.UInt32 prevSimulationFrameIndex, System.Single simulationFrameTime, System.UInt32 updateFrameIndex, System.UInt32& updateFrame1, System.UInt32& updateFrame2, System.Single& framePosition, System.Int32& updateFrameChanged) : System.Void`  

```csharp
public static void CalculateUpdateFrames(uint simulationFrameIndex, uint prevSimulationFrameIndex, float simulationFrameTime, uint updateFrameIndex, out uint updateFrame1, out uint updateFrame2, out float framePosition, out int updateFrameChanged)
	{
		uint num = simulationFrameIndex - updateFrameIndex - 32;
		uint num2 = prevSimulationFrameIndex - updateFrameIndex - 32;
		updateFrame1 = num >> 4;
		uint num3 = num2 >> 4;
		updateFrameChanged = math.select(0, math.select(-1, 1, updateFrame1 > num3), updateFrame1 != num3);
		updateFrame1 &= 3u;
		updateFrame2 = (updateFrame1 + 1) & 3;
		framePosition = ((float)(num & 0xF) + simulationFrameTime) * 0.0625f;
	}
```

- `public static FindAnimationClip(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Prefabs.AnimationType type, Game.Prefabs.ActivityType activity, Game.Prefabs.AnimationLayer animationLayer, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Game.Prefabs.AnimationClip& clip, System.Int32& index) : System.Boolean`  

```csharp
public static bool FindAnimationClip(DynamicBuffer<AnimationClip> clips, Game.Prefabs.AnimationType type, ActivityType activity, AnimationLayer animationLayer, AnimatedPropID propID, ActivityCondition conditions, out AnimationClip clip, out int index)
	{
		int num = int.MaxValue;
		clip = clips[0];
		index = 0;
		for (int i = 0; i < clips.Length; i++)
		{
			AnimationClip animationClip = clips[i];
			if (animationClip.m_Type == type && animationClip.m_Activity == activity && animationClip.m_Layer == animationLayer && animationClip.m_PropID == propID)
			{
				ActivityCondition activityCondition = animationClip.m_Conditions ^ conditions;
				if (activityCondition == (ActivityCondition)0u)
				{
					clip = animationClip;
					index = i;
					return true;
				}
				int num2 = math.countbits((uint)activityCondition);
				if (num2 < num)
				{
					num = num2;
					clip = animationClip;
					index = i;
				}
			}
		}
		return num != int.MaxValue;
	}
```

- `private static FindCatenaryHeight(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, System.Single defaultHeight, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.UtilityLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabUtilityLaneDatas, Colossal.Collections.NativeQuadTree`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Common.QuadTreeBoundsXZ, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneSearchTree) : System.Single`  

```csharp
private static float FindCatenaryHeight(float3 position, quaternion rotation, float defaultHeight, ref ComponentLookup<Curve> curveDatas, ref ComponentLookup<PrefabRef> prefabRefDatas, ref ComponentLookup<UtilityLaneData> prefabUtilityLaneDatas, ref NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree)
	{
		Line3.Segment line = new Line3.Segment(position, position + math.mul(rotation, new float3(0f, defaultHeight * 2f, 0f)));
		float3 @float = MathUtils.Position(line, 0.5f);
		CatenaryIterator iterator = new CatenaryIterator
		{
			m_Bounds = new Bounds3(@float - defaultHeight, @float + defaultHeight),
			m_Line = line,
			m_Result = 1000f,
			m_Default = defaultHeight,
			m_CurveData = curveDatas,
			m_PrefabRefData = prefabRefDatas,
			m_PrefabUtilityLaneData = prefabUtilityLaneDatas
		};
		laneSearchTree.Iterate(ref iterator);
		curveDatas = iterator.m_CurveData;
		prefabRefDatas = iterator.m_PrefabRefData;
		prefabUtilityLaneDatas = iterator.m_PrefabUtilityLaneData;
		return math.lerp(iterator.m_Result.x, defaultHeight, math.min(1f, iterator.m_Result.y / (defaultHeight * 0.5f)));
	}
```

- `private static FindChildBone(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, System.Int32 index, System.Int32& childIndex) : System.Boolean`  

```csharp
private static bool FindChildBone(DynamicBuffer<ProceduralBone> proceduralBones, int index, out int childIndex)
	{
		for (int i = 0; i < proceduralBones.Length; i++)
		{
			if (proceduralBones[i].m_ParentIndex == index)
			{
				childIndex = i;
				return true;
			}
		}
		childIndex = -1;
		return false;
	}
```

- `public static GetActivityConditions(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup) : Game.Prefabs.ActivityCondition`  

```csharp
public static ActivityCondition GetActivityConditions(Entity entity, ref ComponentLookup<Human> humanLookup)
	{
		if (humanLookup.TryGetComponent(entity, out var componentData))
		{
			return CreatureUtils.GetConditions(componentData);
		}
		return (ActivityCondition)0u;
	}
```

- `public static GetClipType(Game.Prefabs.AnimationClip clip, Game.Objects.TransformState state, System.Single movementDelta, System.Single speedDeltaFactor, Game.Prefabs.AnimationType& type, Game.Prefabs.ActivityType& activity) : System.Void`  

```csharp
public static void GetClipType(AnimationClip clip, TransformState state, float movementDelta, float speedDeltaFactor, out Game.Prefabs.AnimationType type, ref ActivityType activity)
	{
		switch (state)
		{
		case TransformState.Move:
			type = Game.Prefabs.AnimationType.Move;
			if (activity == ActivityType.None)
			{
				switch (clip.m_Activity)
				{
				case ActivityType.Walking:
				{
					float num2 = math.abs(movementDelta * speedDeltaFactor);
					activity = ((speedDeltaFactor != 0f && num2 > clip.m_SpeedRange.max) ? ActivityType.Running : ActivityType.Walking);
					break;
				}
				case ActivityType.Running:
				{
					float num = math.abs(movementDelta * speedDeltaFactor);
					activity = ((speedDeltaFactor != 0f && num < clip.m_SpeedRange.min) ? ActivityType.Walking : ActivityType.Running);
					break;
				}
				default:
					activity = ActivityType.Walking;
					break;
				}
			}
			break;
		case TransformState.Start:
			type = Game.Prefabs.AnimationType.Start;
			break;
		case TransformState.End:
			type = Game.Prefabs.AnimationType.End;
			break;
		case TransformState.Action:
		case TransformState.Done:
			type = Game.Prefabs.AnimationType.Action;
			break;
		default:
			type = Game.Prefabs.AnimationType.Idle;
			if (activity == ActivityType.None)
			{
				activity = ActivityType.Standing;
			}
			break;
		}
	}
```

- `public static GetInitialTime(Unity.Mathematics.Random& random, Game.Prefabs.AnimationClip& clip, System.Single movementSpeed, System.Single prevClipLength, System.Single prevMovementSpeed, System.Single prevTime) : System.Single`  

```csharp
public static float GetInitialTime(ref Unity.Mathematics.Random random, in AnimationClip clip, float movementSpeed, float prevClipLength, float prevMovementSpeed, float prevTime)
	{
		if (movementSpeed != 0f && prevMovementSpeed != 0f && prevClipLength != 0f)
		{
			return prevTime / prevClipLength * clip.m_AnimationLength;
		}
		return clip.m_Playback switch
		{
			AnimationPlayback.RandomLoop => random.NextFloat(clip.m_AnimationLength), 
			AnimationPlayback.HalfLoop => math.select(0f, clip.m_AnimationLength * 0.5f, random.NextBool()), 
			_ => 0f, 
		};
	}
```

- `public static GetMovementSpeed(Game.Prefabs.CharacterElement& characterElement, Game.Prefabs.AnimationClip& clip, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup) : System.Single`  

```csharp
public static float GetMovementSpeed(in CharacterElement characterElement, in AnimationClip clip, ref BufferLookup<AnimationMotion> motionLookup)
	{
		if (clip.m_Type == Game.Prefabs.AnimationType.Move && clip.m_MotionRange.y > clip.m_MotionRange.x + 1)
		{
			DynamicBuffer<AnimationMotion> motions = motionLookup[characterElement.m_Style];
			AnimationMotion motion = motions[clip.m_MotionRange.x];
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight0);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight1);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight2);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight3);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight4);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight5);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight6);
			AddMotionOffset(ref motion, motions, clip.m_MotionRange, characterElement.m_ShapeWeights.m_Weight7);
			float num = clip.m_AnimationLength * clip.m_FrameRate;
			float num2 = clip.m_FrameRate / math.max(1f, num - 1f);
			return math.length(motion.m_EndOffset - motion.m_StartOffset) * num2;
		}
		return clip.m_MovementSpeed;
	}
```

- `public static GetPropID(Unity.Entities.Entity entity, Game.Prefabs.ActivityType activity, Unity.Entities.ComponentLookup`1[[Game.Creatures.CurrentVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentVehicleLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& activityLocationLookup) : Game.Rendering.AnimatedPropID`  

```csharp
public static AnimatedPropID GetPropID(Entity entity, ActivityType activity, ref ComponentLookup<CurrentVehicle> currentVehicleLookup, ref ComponentLookup<PrefabRef> prefabRefLookup, ref BufferLookup<ActivityLocationElement> activityLocationLookup)
	{
		AnimatedPropID result = new AnimatedPropID(-1);
		if ((activity == ActivityType.Enter || activity == ActivityType.Exit) && currentVehicleLookup.TryGetComponent(entity, out var componentData) && prefabRefLookup.TryGetComponent(componentData.m_Vehicle, out var componentData2) && activityLocationLookup.TryGetBuffer(componentData2.m_Prefab, out var bufferData) && bufferData.Length != 0)
		{
			return bufferData[0].m_PropID;
		}
		return result;
	}
```

- `public static GetUpdateFrameTransition(System.Single framePosition) : System.Single`  

```csharp
public static float GetUpdateFrameTransition(float framePosition)
	{
		float num = framePosition * framePosition;
		return 3f * num - 2f * num * framePosition;
	}
```

- `private static LocalToObject(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.quaternion rotation) : Unity.Mathematics.quaternion`  

```csharp
private static quaternion LocalToObject(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Skeleton skeleton, int index, quaternion rotation)
	{
		while (index >= 0)
		{
			rotation = math.mul(bones[skeleton.m_BoneOffset + index].m_Rotation, rotation);
			index = proceduralBones[index].m_ParentIndex;
		}
		return rotation;
	}
```

- `private static LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.quaternion rotation) : Unity.Mathematics.quaternion`  

```csharp
private static void LocalToWorld(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Transform transform, Skeleton skeleton, int index, ref float3 position, ref quaternion rotation)
	{
		while (index >= 0)
		{
			Bone bone = bones[skeleton.m_BoneOffset + index];
			position = bone.m_Position + math.mul(bone.m_Rotation, position);
			rotation = math.mul(bone.m_Rotation, rotation);
			index = proceduralBones[index].m_ParentIndex;
		}
		position = transform.m_Position + math.mul(transform.m_Rotation, position);
		rotation = math.mul(transform.m_Rotation, rotation);
	}
```

- `private static LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  

```csharp
private static void LocalToWorld(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Transform transform, Skeleton skeleton, int index, ref float3 position, ref quaternion rotation)
	{
		while (index >= 0)
		{
			Bone bone = bones[skeleton.m_BoneOffset + index];
			position = bone.m_Position + math.mul(bone.m_Rotation, position);
			rotation = math.mul(bone.m_Rotation, rotation);
			index = proceduralBones[index].m_ParentIndex;
		}
		position = transform.m_Position + math.mul(transform.m_Rotation, position);
		rotation = math.mul(transform.m_Rotation, rotation);
	}
```

- `private static LocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, System.Int32 index, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation) : System.Void`  

```csharp
private static void LocalToWorld(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Transform transform, Skeleton skeleton, int index, ref float3 position, ref quaternion rotation)
	{
		while (index >= 0)
		{
			Bone bone = bones[skeleton.m_BoneOffset + index];
			position = bone.m_Position + math.mul(bone.m_Rotation, position);
			rotation = math.mul(bone.m_Rotation, rotation);
			index = proceduralBones[index].m_ParentIndex;
		}
		position = transform.m_Position + math.mul(transform.m_Rotation, position);
		rotation = math.mul(transform.m_Rotation, rotation);
	}
```

- `private static LookAtLocalToWorld(Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> proceduralBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Objects.Transform transform, Game.Rendering.Skeleton skeleton, Game.Common.PointOfInterest pointOfInterest, System.Int32 parentIndex, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation) : System.Void`  

```csharp
private static void LookAtLocalToWorld(DynamicBuffer<ProceduralBone> proceduralBones, DynamicBuffer<Bone> bones, Transform transform, Skeleton skeleton, PointOfInterest pointOfInterest, int parentIndex, ref float3 position, ref quaternion rotation)
	{
		ProceduralBone proceduralBone = proceduralBones[parentIndex];
		if (proceduralBone.m_Type == BoneType.LookAtRotation || proceduralBone.m_Type == BoneType.LookAtRotationSide)
		{
			float3 position2 = proceduralBone.m_Position;
			quaternion rotation2 = proceduralBone.m_Rotation;
			LocalToWorld(proceduralBones, bones, transform, skeleton, proceduralBone.m_ParentIndex, ref position2, ref rotation2);
			float3 v = pointOfInterest.m_Position - position2;
			v = math.mul(math.inverse(rotation2), v);
			v.xz = math.select(v.xz, MathUtils.Right(v.xz), proceduralBone.m_Type == BoneType.LookAtRotationSide);
			float2 value = math.select(v, -v, proceduralBone.m_Speed < 0f).xz;
			if (MathUtils.TryNormalize(ref value))
			{
				float angle = MathUtils.RotationAngleSignedRight(math.forward().xz, value);
				rotation2 = math.mul(rotation2, quaternion.RotateY(angle));
			}
			position = position2 + math.mul(rotation2, position);
			rotation = math.mul(rotation2, rotation);
		}
		else if (proceduralBone.m_Type == BoneType.LengthwiseLookAtRotation)
		{
			float3 position3 = proceduralBone.m_Position;
			quaternion rotation3 = proceduralBone.m_Rotation;
			LocalToWorld(proceduralBones, bones, transform, skeleton, proceduralBone.m_ParentIndex, ref position3, ref rotation3);
			float3 v2 = pointOfInterest.m_Position - position3;
			v2 = math.mul(math.inverse(rotation3), v2);
			float2 value2 = math.select(v2, -v2, proceduralBone.m_Speed < 0f).xy;
			if (MathUtils.TryNormalize(ref value2))
			{
				float angle2 = MathUtils.RotationAngleSignedLeft(math.up().xy, value2);
				rotation3 = math.mul(rotation3, quaternion.RotateZ(angle2));
			}
			position = position3 + math.mul(rotation3, position);
			rotation = math.mul(rotation3, rotation);
		}
		else
		{
			LocalToWorld(proceduralBones, bones, transform, skeleton, parentIndex, ref position, ref rotation);
		}
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
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_AnimatedSystem = base.World.GetOrCreateSystemManaged<AnimatedSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_InterpolateQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Temp>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadWrite<InterpolatedTransform>(),
				ComponentType.ReadWrite<Animated>(),
				ComponentType.ReadWrite<Bone>(),
				ComponentType.ReadWrite<LightState>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Relative>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<IconElement>(),
				ComponentType.ReadWrite<InterpolatedTransform>(),
				ComponentType.ReadOnly<UpdateFrame>(),
				ComponentType.ReadOnly<TransformFrame>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Relative>()
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeList<PreCullingData> cullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies2);
		JobHandle dependencies3;
		NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies3);
		JobHandle dependencies4;
		AnimatedSystem.AnimationData animationData = m_AnimatedSystem.GetAnimationData(out dependencies4);
		JobHandle deps;
		WaterSurfaceData surfaceData = m_WaterSystem.GetSurfaceData(out deps);
		JobHandle deps2;
		WaterSurfaceData velocitiesSurfaceData = m_WaterSystem.GetVelocitiesSurfaceData(out deps2);
		TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
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
		JobHandle dependencies5;
		UpdateTransformDataJob jobData = new UpdateTransformDataJob
		{
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PointOfInterestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PointOfInterest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_TrafficLight_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencyData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingElectricityConsumer = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingExtractorFacility = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ExtractorFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarTrailerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarTrailer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSwayingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SwayingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_EffectInstances = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationMotions = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationMotion_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralLights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RO_BufferLookup, ref base.CheckedStateRef),
			m_LightAnimations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LightAnimation_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ActivityLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SwayingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_Swaying_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RW_BufferLookup, ref base.CheckedStateRef),
			m_Emissives = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RW_BufferLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RW_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RW_BufferLookup, ref base.CheckedStateRef),
			m_Momentums = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Momentum_RW_BufferLookup, ref base.CheckedStateRef),
			m_Lights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_LightState_RW_BufferLookup, ref base.CheckedStateRef),
			m_PrevFrameIndex = m_PrevFrameIndex,
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_FrameDelta = m_RenderingSystem.frameDelta,
			m_TimeOfDay = m_RenderingSystem.timeOfDay,
			m_LodParameters = lodParameters,
			m_CameraPosition = cameraPosition,
			m_CameraDirection = cameraDirection,
			m_RandomSeed = RandomSeed.Next(),
			m_WindData = m_WindSystem.GetData(readOnly: true, out dependencies5),
			m_LaneSearchTree = laneSearchTree,
			m_CullingData = cullingData,
			m_EnabledData = enabledData,
			m_AnimationData = animationData,
			m_WaterSurfaceData = surfaceData,
			m_WaterVelocityData = velocitiesSurfaceData,
			m_TerrainHeightData = heightData
		};
		UpdateTrailerTransformDataJob jobData2 = new UpdateTrailerTransformDataJob
		{
			m_PointOfInterestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PointOfInterest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSwayingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SwayingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarTractorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarTractorData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarTrailerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarTrailerData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_BogieFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_TrainBogieFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralLights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RO_BufferLookup, ref base.CheckedStateRef),
			m_LightAnimations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LightAnimation_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SwayingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_Swaying_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RW_BufferLookup, ref base.CheckedStateRef),
			m_Emissive = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RW_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RW_BufferLookup, ref base.CheckedStateRef),
			m_Momentums = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Momentum_RW_BufferLookup, ref base.CheckedStateRef),
			m_LightStates = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_LightState_RW_BufferLookup, ref base.CheckedStateRef),
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_FrameDelta = m_RenderingSystem.frameDelta,
			m_RandomSeed = RandomSeed.Next(),
			m_LaneSearchTree = laneSearchTree,
			m_CullingData = cullingData
		};
		UpdateQueryTransformDataJob jobData3 = new UpdateQueryTransformDataJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SwayingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_Swaying_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StaticType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Static_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StoppedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Animation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_MeshGroupType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EffectInstancesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_IconElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralLights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RO_BufferLookup, ref base.CheckedStateRef),
			m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RW_BufferLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RW_BufferLookup, ref base.CheckedStateRef),
			m_Emissives = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RW_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RW_BufferLookup, ref base.CheckedStateRef),
			m_Lights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_LightState_RW_BufferLookup, ref base.CheckedStateRef),
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_LodParameters = lodParameters,
			m_CameraPosition = cameraPosition,
			m_CameraDirection = cameraDirection,
			m_CullingData = cullingData,
			m_EnabledData = enabledData,
			m_AnimationData = animationData,
			m_WaterSurfaceData = surfaceData,
			m_TerrainHeightData = heightData
		};
		JobHandle jobHandle = jobData.Schedule(cullingData, 16, JobUtils.CombineDependencies(base.Dependency, dependencies, dependencies2, dependencies3, dependencies5, dependencies4, deps, deps2));
		JobHandle jobHandle2 = jobData2.Schedule(cullingData, 16, jobHandle);
		JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(jobData3, m_InterpolateQuery, jobHandle2);
		m_WindSystem.AddReader(jobHandle);
		m_NetSearchSystem.AddLaneSearchTreeReader(jobHandle2);
		m_PreCullingSystem.AddCullingDataReader(jobHandle3);
		m_EffectControlSystem.AddEnabledDataReader(jobHandle3);
		m_AnimatedSystem.AddAnimationWriter(jobHandle3);
		m_WaterSystem.AddSurfaceReader(jobHandle3);
		m_WaterSystem.AddVelocitySurfaceReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle3);
		base.Dependency = jobHandle3;
		m_PrevFrameIndex = m_RenderingSystem.frameIndex;
	}
```

- `public static SynchronizeMovementTime(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.Animated& animated, System.Single movementDelta, System.Single framePosition) : System.Void`  

```csharp
public static void SynchronizeMovementTime(DynamicBuffer<AnimationClip> clips, ref Animated animated, float movementDelta, float framePosition)
	{
		AnimationClip animationClip = clips[animated.m_ClipIndexBody0];
		AnimationClip animationClip2 = clips[animated.m_ClipIndexBody1];
		float2 @float = new float2(animationClip.m_AnimationLength, animationClip2.m_AnimationLength);
		float2 float2 = movementDelta / (animated.m_MovementSpeed * @float);
		animated.m_Time.xy += math.lerp(float2.x, float2.y, framePosition) * @float;
	}
```

- `public static UpdateInterpolatedAnimation(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, System.Single stateTimer, Game.Objects.TransformState state, Game.Prefabs.ActivityType activity, System.Single updateFrameToSeconds, System.Single speedDeltaFactor) : System.Void`  

```csharp
public static void UpdateInterpolatedAnimation(DynamicBuffer<AnimationClip> clips, InterpolatedTransform oldTransform, InterpolatedTransform newTransform, ref Animated animated, float stateTimer, TransformState state, ActivityType activity, float updateFrameToSeconds, float speedDeltaFactor)
	{
		AnimationClip clip = clips[animated.m_ClipIndexBody0];
		float3 y = math.forward(newTransform.m_Rotation);
		float num = math.dot(newTransform.m_Position - oldTransform.m_Position, y);
		GetClipType(clip, state, num, speedDeltaFactor, out var type, ref activity);
		if (clip.m_Type != type || clip.m_Activity != activity || clip.m_Layer != AnimationLayer.Body)
		{
			FindAnimationClip(clips, type, activity, AnimationLayer.Body, new AnimatedPropID(-1), (ActivityCondition)0u, out clip, out var index);
			animated.m_ClipIndexBody0 = (short)index;
			animated.m_Time.x = 0f;
		}
		animated.m_PreviousTime = animated.m_Time.x;
		if (clip.m_MovementSpeed != 0f)
		{
			animated.m_Time.x += num / clip.m_MovementSpeed;
		}
		else
		{
			animated.m_Time.x = stateTimer * updateFrameToSeconds;
		}
	}
```

- `public static UpdateInterpolatedAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.ComponentLookup`1[[Game.Creatures.CurrentVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentVehicleLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& activityLocationLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Game.Objects.TransformFrame frame0, Game.Objects.TransformFrame frame1, System.Single framePosition, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset) : System.Void`  

```csharp
public static void UpdateInterpolatedAnimationBody(Entity entity, in CharacterElement characterElement, DynamicBuffer<AnimationClip> clips, ref ComponentLookup<Human> humanLookup, ref ComponentLookup<CurrentVehicle> currentVehicleLookup, ref ComponentLookup<PrefabRef> prefabRefLookup, ref BufferLookup<ActivityLocationElement> activityLocationLookup, ref BufferLookup<AnimationMotion> motionLookup, InterpolatedTransform oldTransform, InterpolatedTransform newTransform, ref Animated animated, ref Unity.Mathematics.Random random, TransformFrame frame0, TransformFrame frame1, float framePosition, float updateFrameToSeconds, float speedDeltaFactor, float deltaTime, int updateFrameChanged, bool instantReset)
	{
		float3 y = math.forward(newTransform.m_Rotation);
		float num = math.dot(newTransform.m_Position - oldTransform.m_Position, y);
		if (instantReset)
		{
			AnimationClip clip = clips[animated.m_ClipIndexBody0];
			ActivityType activity = (ActivityType)frame1.m_Activity;
			GetClipType(clip, frame1.m_State, num, speedDeltaFactor, out var type, ref activity);
			AnimatedPropID propID = GetPropID(entity, activity, ref currentVehicleLookup, ref prefabRefLookup, ref activityLocationLookup);
			ActivityCondition activityConditions = GetActivityConditions(entity, ref humanLookup);
			FindAnimationClip(clips, type, activity, AnimationLayer.Body, propID, activityConditions, out clip, out var index);
			animated.m_ClipIndexBody0 = (short)index;
			animated.m_ClipIndexBody0I = -1;
			animated.m_ClipIndexBody1 = -1;
			animated.m_ClipIndexBody1I = -1;
			animated.m_MovementSpeed = new float2(GetMovementSpeed(in characterElement, in clip, ref motionLookup), 0f);
			animated.m_Time.xy = 0f;
			if (animated.m_MovementSpeed.x != 0f || frame1.m_State == TransformState.Idle)
			{
				animated.m_Time.x = random.NextFloat(clip.m_AnimationLength);
			}
		}
		else if (updateFrameChanged > 0)
		{
			AnimationClip clip2;
			if (animated.m_ClipIndexBody1 != -1)
			{
				clip2 = clips[animated.m_ClipIndexBody1];
				animated.m_ClipIndexBody0 = animated.m_ClipIndexBody1;
				animated.m_ClipIndexBody0I = animated.m_ClipIndexBody1I;
				animated.m_Time.x = animated.m_Time.y;
				animated.m_MovementSpeed.x = animated.m_MovementSpeed.y;
			}
			else
			{
				clip2 = clips[animated.m_ClipIndexBody0];
			}
			ActivityType activity2 = (ActivityType)frame1.m_Activity;
			GetClipType(clip2, frame1.m_State, num, speedDeltaFactor, out var type2, ref activity2);
			AnimatedPropID propID2 = GetPropID(entity, activity2, ref currentVehicleLookup, ref prefabRefLookup, ref activityLocationLookup);
			animated.m_ClipIndexBody1 = -1;
			animated.m_ClipIndexBody1I = -1;
			animated.m_MovementSpeed.y = 0f;
			animated.m_Time.y = 0f;
			if (clip2.m_Type != type2 || clip2.m_Activity != activity2 || clip2.m_PropID != propID2)
			{
				ActivityCondition activityConditions2 = GetActivityConditions(entity, ref humanLookup);
				float animationLength = clip2.m_AnimationLength;
				if (FindAnimationClip(clips, type2, activity2, AnimationLayer.Body, propID2, activityConditions2, out clip2, out var index2))
				{
					animated.m_ClipIndexBody1 = (short)index2;
					animated.m_ClipIndexBody1I = -1;
					animated.m_MovementSpeed.y = GetMovementSpeed(in characterElement, in clip2, ref motionLookup);
					animated.m_Time.y = GetInitialTime(ref random, in clip2, animated.m_MovementSpeed.y, animationLength, animated.m_MovementSpeed.x, animated.m_Time.x);
				}
			}
		}
		else if (updateFrameChanged < 0)
		{
			AnimationClip clip3 = clips[animated.m_ClipIndexBody0];
			ActivityType activity3 = (ActivityType)frame0.m_Activity;
			GetClipType(clip3, frame0.m_State, num, speedDeltaFactor, out var type3, ref activity3);
			AnimatedPropID propID3 = GetPropID(entity, activity3, ref currentVehicleLookup, ref prefabRefLookup, ref activityLocationLookup);
			animated.m_ClipIndexBody1 = -1;
			animated.m_ClipIndexBody1I = -1;
			animated.m_Time.y = 0f;
			animated.m_MovementSpeed.y = 0f;
			if (clip3.m_Type != type3 || clip3.m_Activity != activity3 || clip3.m_PropID != propID3)
			{
				ActivityCondition activityConditions3 = GetActivityConditions(entity, ref humanLookup);
				float animationLength2 = clip3.m_AnimationLength;
				if (FindAnimationClip(clips, type3, activity3, AnimationLayer.Body, propID3, activityConditions3, out clip3, out var index3))
				{
					animated.m_ClipIndexBody1 = animated.m_ClipIndexBody0;
					animated.m_ClipIndexBody1I = animated.m_ClipIndexBody0I;
					animated.m_MovementSpeed.y = animated.m_MovementSpeed.x;
					animated.m_Time.y = animated.m_Time.x;
					animated.m_ClipIndexBody0 = (short)index3;
					animated.m_ClipIndexBody0I = -1;
					animated.m_MovementSpeed.x = GetMovementSpeed(in characterElement, in clip3, ref motionLookup);
					animated.m_Time.x = GetInitialTime(ref random, in clip3, animated.m_MovementSpeed.x, animationLength2, animated.m_MovementSpeed.y, animated.m_Time.y);
				}
			}
		}
		if (animated.m_ClipIndexBody1 != -1)
		{
			if (math.all(animated.m_MovementSpeed != 0f))
			{
				SynchronizeMovementTime(clips, ref animated, num, framePosition);
				return;
			}
			if (animated.m_MovementSpeed.y != 0f)
			{
				animated.m_Time.y += num / animated.m_MovementSpeed.y;
			}
			else if (clips[animated.m_ClipIndexBody1].m_Type == Game.Prefabs.AnimationType.Idle)
			{
				animated.m_Time.y += deltaTime;
			}
			else
			{
				animated.m_Time.y = ((float)(int)frame1.m_StateTimer + framePosition - 1f) * updateFrameToSeconds;
			}
		}
		if (animated.m_MovementSpeed.x != 0f)
		{
			animated.m_Time.x += num / animated.m_MovementSpeed.x;
		}
		else if (clips[animated.m_ClipIndexBody0].m_Type == Game.Prefabs.AnimationType.Idle)
		{
			animated.m_Time.x += deltaTime;
		}
		else
		{
			animated.m_Time.x = ((float)(int)frame0.m_StateTimer + framePosition) * updateFrameToSeconds;
		}
	}
```

- `public static UpdateInterpolatedAnimationFace(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Game.Objects.TransformState state, Game.Prefabs.ActivityType activity, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset) : System.Void`  

```csharp
public static void UpdateInterpolatedAnimationFace(Entity entity, DynamicBuffer<AnimationClip> clips, ref ComponentLookup<Human> humanLookup, ref Animated animated, ref Unity.Mathematics.Random random, TransformState state, ActivityType activity, float deltaTime, int updateFrameChanged, bool instantReset)
	{
		if (instantReset)
		{
			ActivityCondition activityConditions = GetActivityConditions(entity, ref humanLookup);
			FindAnimationClip(clips, Game.Prefabs.AnimationType.Idle, ActivityType.None, AnimationLayer.Facial, new AnimatedPropID(-1), activityConditions, out var clip, out var index);
			animated.m_ClipIndexFace0 = (short)index;
			animated.m_Time.z = random.NextFloat(clip.m_AnimationLength);
		}
		else if (updateFrameChanged > 0)
		{
			AnimationClip clip2;
			if (animated.m_ClipIndexFace1 != -1)
			{
				clip2 = clips[animated.m_ClipIndexFace1];
				animated.m_ClipIndexFace0 = animated.m_ClipIndexFace1;
				animated.m_Time.z = animated.m_Time.w;
			}
			else
			{
				clip2 = clips[animated.m_ClipIndexFace0];
			}
			ActivityCondition activityConditions2 = GetActivityConditions(entity, ref humanLookup);
			animated.m_ClipIndexFace1 = -1;
			animated.m_Time.w = 0f;
			if (((clip2.m_Conditions ^ activityConditions2) & (ActivityCondition.Angry | ActivityCondition.Sad | ActivityCondition.Happy | ActivityCondition.Waiting)) != 0 && FindAnimationClip(clips, Game.Prefabs.AnimationType.Idle, ActivityType.None, AnimationLayer.Facial, new AnimatedPropID(-1), activityConditions2, out clip2, out var index2))
			{
				animated.m_ClipIndexFace1 = (short)index2;
				animated.m_Time.w = random.NextFloat(clip2.m_AnimationLength);
			}
		}
		else if (updateFrameChanged < 0)
		{
			AnimationClip clip3 = clips[animated.m_ClipIndexFace0];
			ActivityCondition activityConditions3 = GetActivityConditions(entity, ref humanLookup);
			animated.m_ClipIndexFace1 = -1;
			animated.m_Time.w = 0f;
			if (((clip3.m_Conditions ^ activityConditions3) & (ActivityCondition.Angry | ActivityCondition.Sad | ActivityCondition.Happy | ActivityCondition.Waiting)) != 0 && FindAnimationClip(clips, Game.Prefabs.AnimationType.Idle, ActivityType.None, AnimationLayer.Facial, new AnimatedPropID(-1), activityConditions3, out clip3, out var index3))
			{
				animated.m_ClipIndexFace1 = animated.m_ClipIndexFace0;
				animated.m_Time.w = animated.m_Time.z;
				animated.m_ClipIndexFace0 = (short)index3;
				animated.m_Time.z = random.NextFloat(clip3.m_AnimationLength);
			}
		}
		animated.m_Time.zw += deltaTime;
		animated.m_Time.w = 0f;
	}
```

- `private static UpdateSwaying(Game.Prefabs.SwayingData swayingData, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform& newTransform, Game.Rendering.Swaying& swaying, System.Single deltaTime, System.Single speedDeltaFactor, System.Boolean localSway, Unity.Mathematics.quaternion& swayRotation, System.Single& swayOffset) : System.Void`  

```csharp
private static void UpdateSwaying(SwayingData swayingData, InterpolatedTransform oldTransform, ref InterpolatedTransform newTransform, ref Swaying swaying, float deltaTime, float speedDeltaFactor, bool localSway, out quaternion swayRotation, out float swayOffset)
	{
		if (deltaTime != 0f)
		{
			float3 position = oldTransform.m_Position;
			if (localSway)
			{
				position -= math.mul(oldTransform.m_Rotation, new float3(0f, swaying.m_SwayPosition.y, 0f));
			}
			else
			{
				position.y -= swaying.m_SwayPosition.y;
			}
			float3 @float = (newTransform.m_Position - position) * speedDeltaFactor;
			float3 float2 = @float - swaying.m_LastVelocity;
			if (localSway)
			{
				float2 = math.mul(math.inverse(newTransform.m_Rotation), float2);
			}
			swaying.m_SwayVelocity += float2 * swayingData.m_VelocityFactors - swaying.m_SwayPosition * swayingData.m_SpringFactors * deltaTime;
			swaying.m_SwayVelocity *= math.pow(swayingData.m_DampingFactors, deltaTime);
			swaying.m_SwayPosition += swaying.m_SwayVelocity * deltaTime;
			swaying.m_SwayVelocity = math.select(swaying.m_SwayVelocity, 0f, ((swaying.m_SwayPosition >= swayingData.m_MaxPosition) & (swaying.m_SwayVelocity >= 0f)) | ((swaying.m_SwayPosition <= -swayingData.m_MaxPosition) & (swaying.m_SwayVelocity <= 0f)));
			swaying.m_SwayPosition = math.clamp(swaying.m_SwayPosition, -swayingData.m_MaxPosition, swayingData.m_MaxPosition);
			swaying.m_LastVelocity = @float;
		}
		float2 value = swaying.m_SwayPosition.xz;
		if (MathUtils.TryNormalize(ref value))
		{
			swayRotation = quaternion.AxisAngle(new float3(0f - value.y, 0f, value.x), math.length(swaying.m_SwayPosition.xz));
			if (localSway)
			{
				newTransform.m_Rotation = math.mul(newTransform.m_Rotation, swayRotation);
			}
			else
			{
				newTransform.m_Rotation = math.mul(swayRotation, newTransform.m_Rotation);
			}
			swayRotation = math.inverse(swayRotation);
		}
		else
		{
			swayRotation = quaternion.identity;
		}
		if (localSway)
		{
			newTransform.m_Position += math.mul(newTransform.m_Rotation, new float3(0f, swaying.m_SwayPosition.y, 0f));
		}
		else
		{
			newTransform.m_Position.y += swaying.m_SwayPosition.y;
		}
		swayOffset = 0f - swaying.m_SwayPosition.y;
	}
```


## Nested types

- `Game.Rendering.ObjectInterpolateSystem+UpdateTransformDataJob`  
- `Game.Rendering.ObjectInterpolateSystem+UpdateTrailerTransformDataJob`  
- `Game.Rendering.ObjectInterpolateSystem+UpdateQueryTransformDataJob`  
- `Game.Rendering.ObjectInterpolateSystem+CatenaryIterator`  
- `Game.Rendering.ObjectInterpolateSystem+TypeHandle`  

