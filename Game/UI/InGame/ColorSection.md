# Game.UI.InGame.ColorSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ColorSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private UnityEngine.Color32 <color>k__BackingField;
    private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;

    protected System.String group { protected get; }
    private UnityEngine.Color32 color { private get; private set; }

    public ColorSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    private System.Void OnSetColor(UnityEngine.Color uiColor);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  

```csharp
private UnityEngine.Color32 <color>k__BackingField;
```

- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private UnityEngine.Color32 color { private get; private set }`  

```csharp
private UnityEngine.Color32 color { private get; private set; }
```


## Constructors

- `public ColorSection()`  

```csharp
[Preserve]
	public ColorSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(new TriggerBinding<UnityEngine.Color>(group, "setColor", OnSetColor));
		m_ColorUpdateArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<ColorUpdated>());
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		color = base.EntityManager.GetComponentData<Game.Routes.Color>(selectedEntity).m_Color;
	}
```

- `private OnSetColor(UnityEngine.Color uiColor) : System.Void`  

```csharp
private void OnSetColor(UnityEngine.Color uiColor)
	{
		if (!base.EntityManager.HasComponent<Route>(selectedEntity) || !base.EntityManager.HasComponent<TransportLine>(selectedEntity) || !base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity) || !base.EntityManager.HasComponent<Game.Routes.Color>(selectedEntity))
		{
			return;
		}
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		entityCommandBuffer.SetComponent(selectedEntity, new Game.Routes.Color(uiColor));
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<RouteVehicle> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				entityCommandBuffer.AddComponent(buffer[i].m_Vehicle, new Game.Routes.Color(uiColor));
			}
		}
		Entity e = entityCommandBuffer.CreateEntity(m_ColorUpdateArchetype);
		entityCommandBuffer.SetComponent(e, new ColorUpdated(selectedEntity));
		m_InfoUISystem.RequestUpdate();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("color");
		writer.Write(color);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		color = default(Color32);
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Game.Routes.Color>(selectedEntity);
		}
		return false;
	}
```


