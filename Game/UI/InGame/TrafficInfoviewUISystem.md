# Game.UI.InGame.TrafficInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_AggregateQuery;
    private Colossal.UI.Binding.RawValueBinding m_TrafficFlow;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private System.Single[] m_Flow;
    private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public TrafficInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void Reset();
    private System.Void UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AggregateQuery`  

```csharp
private Unity.Entities.EntityQuery m_AggregateQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_TrafficFlow`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TrafficFlow;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private System.Single[] m_Flow`  

```csharp
private System.Single[] m_Flow;
```

- `private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public TrafficInfoviewUISystem()`  

```csharp
[Preserve]
	public TrafficInfoviewUISystem()
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
		m_AggregateQuery = GetEntityQuery(ComponentType.ReadOnly<Aggregated>(), ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<Road>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Native>());
		AddBinding(m_TrafficFlow = new RawValueBinding("trafficInfo", "trafficFlow", UpdateTrafficFlowBinding));
		m_Flow = new float[5];
		m_Results = new NativeArray<float>(5, Allocator.Persistent);
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		Reset();
		JobChunkExtensions.Schedule(new UpdateFlowJob
		{
			m_RoadHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_AggregateQuery, base.Dependency).Complete();
		m_TrafficFlow.Update();
	}
```

- `private Reset() : System.Void`  

```csharp
private void Reset()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0f;
		}
		for (int j = 0; j < m_Flow.Length; j++)
		{
			m_Flow[j] = 0f;
		}
	}
```

- `private UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void UpdateTrafficFlowBinding(IJsonWriter writer)
	{
		int num = math.select((int)m_Results[4], 1, (int)m_Results[4] == 0);
		m_Flow[0] = m_Results[0] / (float)num;
		m_Flow[1] = m_Results[1] / (float)num;
		m_Flow[2] = m_Results[2] / (float)num;
		m_Flow[3] = m_Results[3] / (float)num;
		m_Flow[4] = m_Flow[0];
		writer.ArrayBegin(m_Flow.Length);
		for (int i = 0; i < m_Flow.Length; i++)
		{
			writer.Write(m_Flow[i]);
		}
		writer.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.TrafficInfoviewUISystem+UpdateFlowJob`  
- `Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle`  

