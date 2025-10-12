# Game.Rendering.RelativeObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  
- `private Unity.Entities.EntityQuery m_RelativeQuery`  
- `private Unity.Entities.EntityQuery m_InterpolateQuery`  
- `private System.UInt32 m_PrevFrameIndex`  
- `private Game.Rendering.RelativeObjectSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RelativeObjectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetRelativeTransform(Game.Objects.Relative relative, Unity.Entities.Entity parent, Unity.Entities.BufferLookup`1[[Game.Rendering.BoneHistory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boneHistoryLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshLookup) : Game.Objects.Transform`  
- `public static GetTargetRotation(Game.Prefabs.AnimationClip& clip, System.Single def, System.Single prev) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static UpdateDrivingAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Unity.Mathematics.float3 velocity, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset) : System.Void`  
- `public static UpdateDrivingClips(Unity.Entities.Entity entity, Game.Prefabs.AnimationClip& clip, Game.Prefabs.AnimationClip& clipI, System.Int16& clipIndex, System.Int16& clipIndexI, System.Single& movementSpeed, System.Single& interpolation, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityType targetActivity) : System.Void`  

## Nested types

- `Game.Rendering.RelativeObjectSystem+UpdateRelativeTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+UpdateQueryTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+TypeHandle`  

