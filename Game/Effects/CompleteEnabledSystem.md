# Game.Effects.CompleteEnabledSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompleteEnabledSystem : Game.GameSystemBase
{
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Effects.VFXSystem m_VFXSystem;
    private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle;

    public CompleteEnabledSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Effects.VFXSystem m_VFXSystem`  

```csharp
private Game.Effects.VFXSystem m_VFXSystem;
```

- `private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.CompleteEnabledSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompleteEnabledSystem()`  

```csharp
[Preserve]
	public CompleteEnabledSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_VFXSystem = base.World.GetOrCreateSystemManaged<VFXSystem>();
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
		JobHandle jobHandle = IJobExtensions.Schedule(new EffectCleanupJob
		{
			m_EffectOwners = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RW_BufferLookup, ref base.CheckedStateRef),
			m_EnabledData = m_EffectControlSystem.GetEnabledData(readOnly: false, out dependencies),
			m_VFXUpdateQueue = m_VFXSystem.GetSourceUpdateData()
		}, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_EffectControlSystem.AddEnabledDataWriter(jobHandle);
		m_VFXSystem.AddSourceUpdateWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Effects.CompleteEnabledSystem+EffectCleanupJob`  
- `Game.Effects.CompleteEnabledSystem+TypeHandle`  

