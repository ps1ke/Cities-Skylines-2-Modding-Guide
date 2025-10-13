# Game.UI.InGame.PoliciesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliciesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;

    protected System.String group { protected get; }

    public PoliciesSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```


## Constructors

- `public PoliciesSection()`  

```csharp
[Preserve]
	public PoliciesSection()
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
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		PoliciesUISystem policiesUISystem = m_PoliciesUISystem;
		policiesUISystem.EventPolicyUnlocked = (Action)Delegate.Combine(policiesUISystem.EventPolicyUnlocked, new Action(m_InfoUISystem.RequestUpdate));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		PoliciesUISystem policiesUISystem = m_PoliciesUISystem;
		policiesUISystem.EventPolicyUnlocked = (Action)Delegate.Remove(policiesUISystem.EventPolicyUnlocked, new Action(m_InfoUISystem.RequestUpdate));
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.HasComponent<Building>(selectedEntity))
		{
			base.tooltipKeys.Add(PoliciesKey.Building.ToString());
		}
		else if (base.EntityManager.HasComponent<District>(selectedEntity))
		{
			base.tooltipKeys.Add(PoliciesKey.District.ToString());
		}
		else if (base.EntityManager.HasComponent<Route>(selectedEntity))
		{
			base.tooltipTags.Add(TooltipTags.CargoRoute.ToString());
			base.tooltipTags.Add(TooltipTags.TransportLine.ToString());
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.HasComponent<Policy>(selectedEntity) && m_PoliciesUISystem.GatherSelectedInfoPolicies(selectedEntity);
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("policies");
		if (base.EntityManager.HasComponent<Building>(selectedEntity))
		{
			m_PoliciesUISystem.BindBuildingPolicies(writer);
		}
		else if (base.EntityManager.HasComponent<District>(selectedEntity))
		{
			m_PoliciesUISystem.BindDistrictPolicies(writer);
		}
		else if (base.EntityManager.HasComponent<Route>(selectedEntity))
		{
			m_PoliciesUISystem.BindRoutePolicies(writer);
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
	}
```


## Nested types

- `Game.UI.InGame.PoliciesSection+PoliciesKey`  

