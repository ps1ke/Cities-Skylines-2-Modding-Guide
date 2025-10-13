# Game.UI.InGame.LandValueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue;
    private Unity.Entities.EntityQuery m_LandValueQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public LandValueInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateLandValue();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue;
```

- `private Unity.Entities.EntityQuery m_LandValueQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public LandValueInfoviewUISystem()`  

```csharp
[Preserve]
	public LandValueInfoviewUISystem()
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
		m_LandValueQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<BuildingCondition>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		AddBinding(m_AverageLandValue = new ValueBinding<float>("landValueInfo", "averageLandValue", 0f));
		m_Results = new NativeArray<float>(2, Allocator.Persistent);
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
		base.OnDestroy();
		m_Results.Dispose();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateLandValue();
	}
```

- `private UpdateLandValue() : System.Void`  

```csharp
private void UpdateLandValue()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0f;
		}
		JobChunkExtensions.Schedule(new CalculateAverageLandValueJob
		{
			m_BuildingTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_LandValueQuery, base.Dependency).Complete();
		float num = m_Results[1];
		float newValue = ((num > 0f) ? (m_Results[0] / num) : 0f);
		m_AverageLandValue.Update(newValue);
	}
```


## Nested types

- `Game.UI.InGame.LandValueInfoviewUISystem+CalculateAverageLandValueJob`  
- `Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle`  

