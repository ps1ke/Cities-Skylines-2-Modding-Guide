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
public RelativeObjectSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetRelativeTransform(Game.Objects.Relative relative, Unity.Entities.Entity parent, Unity.Entities.BufferLookup`1[[Game.Rendering.BoneHistory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boneHistoryLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshLookup) : Game.Objects.Transform`  

```csharp
private static Game.Objects.Transform GetRelativeTransform(Game.Objects.Relative relative, Unity.Entities.Entity parent, Unity.Entities.BufferLookup`1[[Game.Rendering.BoneHistory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boneHistoryLookup, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshLookup);
```

- `public static GetTargetRotation(Game.Prefabs.AnimationClip& clip, System.Single def, System.Single prev) : System.Single`  

```csharp
public static System.Single GetTargetRotation(Game.Prefabs.AnimationClip& clip, System.Single def, System.Single prev);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static UpdateDrivingAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Unity.Mathematics.float3 velocity, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset) : System.Void`  

```csharp
public static System.Void UpdateDrivingAnimationBody(Unity.Entities.Entity entity, Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& motionLookup, Game.Rendering.InterpolatedTransform oldTransform, Game.Rendering.InterpolatedTransform newTransform, Game.Rendering.Animated& animated, Unity.Mathematics.Random& random, Unity.Mathematics.float3 velocity, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, System.Single updateFrameToSeconds, System.Single speedDeltaFactor, System.Single deltaTime, System.Int32 updateFrameChanged, System.Boolean instantReset);
```

- `public static UpdateDrivingClips(Unity.Entities.Entity entity, Game.Prefabs.AnimationClip& clip, Game.Prefabs.AnimationClip& clipI, System.Int16& clipIndex, System.Int16& clipIndexI, System.Single& movementSpeed, System.Single& interpolation, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityType targetActivity) : System.Void`  

```csharp
public static System.Void UpdateDrivingClips(Unity.Entities.Entity entity, Game.Prefabs.AnimationClip& clip, Game.Prefabs.AnimationClip& clipI, System.Int16& clipIndex, System.Int16& clipIndexI, System.Single& movementSpeed, System.Single& interpolation, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Unity.Entities.ComponentLookup`1[[Game.Creatures.Human, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& humanLookup, System.Single steerAngle, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityType targetActivity);
```


## Nested types

- `Game.Rendering.RelativeObjectSystem+UpdateRelativeTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+UpdateQueryTransformDataJob`  
- `Game.Rendering.RelativeObjectSystem+TypeHandle`  

