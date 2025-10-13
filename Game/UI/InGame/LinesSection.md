# Game.UI.InGame.LinesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LinesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField;
    private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
    private Unity.Collections.NativeArray<System.Int32> m_PassengersResult;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult;
    private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set; }

    public LinesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    private System.Void OnToggle(Unity.Entities.Entity entity, System.Boolean state);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem`  

```csharp
private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_BoolResult`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
```

- `private Unity.Collections.NativeArray<System.Int32> m_PassengersResult`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_PassengersResult;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult;
```

- `private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set; }
```


## Constructors

- `public LinesSection()`  

```csharp
[Preserve]
	public LinesSection()
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
		m_TransportationOverviewUISystem = base.World.GetOrCreateSystemManaged<TransportationOverviewUISystem>();
		m_BoolResult = new NativeArray<bool>(2, Allocator.Persistent);
		m_PassengersResult = new NativeArray<int>(1, Allocator.Persistent);
		m_LinesResult = new NativeList<Entity>(Allocator.Persistent);
		lines = new NativeList<Entity>(Allocator.Persistent);
		AddBinding(new TriggerBinding<Entity, bool>(group, "toggle", OnToggle));
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
		lines.Dispose();
		m_LinesResult.Dispose();
		m_PassengersResult.Dispose();
		m_BoolResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		m_InfoUISystem.SetRoutesVisible();
		for (int i = 0; i < m_LinesResult.Length; i++)
		{
			lines.Add(m_LinesResult[i]);
		}
		base.tooltipTags.Add(TooltipTags.CargoRoute.ToString());
		base.tooltipTags.Add(TooltipTags.TransportLine.ToString());
		base.tooltipTags.Add(TooltipTags.TransportStop.ToString());
	}
```

- `private OnToggle(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  

```csharp
private void OnToggle(Entity entity, bool state)
	{
		m_TransportationOverviewUISystem.SetLineState(entity, state);
		m_InfoUISystem.RequestUpdate();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		IJobExtensions.Schedule(new LinesJob
		{
			m_SelectedEntity = selectedEntity,
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaitingPassengers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_WaitingPassengers_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjectBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedRouteBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_BoolResult = m_BoolResult,
			m_LinesResult = m_LinesResult,
			m_PassengersResult = m_PassengersResult
		}, base.Dependency).Complete();
		base.visible = m_BoolResult[0] || m_BoolResult[1];
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("hasLines");
		writer.Write(m_BoolResult[0]);
		writer.PropertyName("lines");
		writer.ArrayBegin(lines.Length);
		for (int i = 0; i < lines.Length; i++)
		{
			writer.TypeBegin("Game.UI.LinesSection.Line");
			writer.PropertyName("name");
			m_NameSystem.BindName(writer, lines[i]);
			writer.PropertyName("color");
			if (base.EntityManager.TryGetComponent<Game.Routes.Color>(lines[i], out var component))
			{
				writer.Write(component.m_Color);
			}
			else
			{
				writer.Write(UnityEngine.Color.white);
			}
			writer.PropertyName("entity");
			writer.Write(lines[i]);
			bool value = !RouteUtils.CheckOption(base.EntityManager.GetComponentData<Route>(lines[i]), RouteOption.Inactive);
			writer.PropertyName("active");
			writer.Write(value);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		writer.PropertyName("hasPassengers");
		writer.Write(m_BoolResult[1]);
		writer.PropertyName("passengers");
		writer.Write(m_PassengersResult[0]);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		lines.Clear();
		m_LinesResult.Clear();
	}
```


## Nested types

- `Game.UI.InGame.LinesSection+Result`  
- `Game.UI.InGame.LinesSection+LinesJob`  
- `Game.UI.InGame.LinesSection+TypeHandle`  

