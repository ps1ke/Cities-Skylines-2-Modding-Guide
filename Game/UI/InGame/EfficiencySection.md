# Game.UI.InGame.EfficiencySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EfficiencySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <efficiency>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 efficiency { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set; }

    public EfficiencySection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <efficiency>k__BackingField`  

```csharp
private System.Int32 <efficiency>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 efficiency { private get; private set }`  

```csharp
private System.Int32 efficiency { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set; }
```


## Constructors

- `public EfficiencySection()`  

```csharp
[Preserve]
	public EfficiencySection()
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
		factors = new List<EfficiencyFactor>(30);
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		DynamicBuffer<Efficiency> buffer = base.EntityManager.GetBuffer<Efficiency>(selectedEntity, isReadOnly: true);
		efficiency = (int)math.round(100f * BuildingUtils.GetEfficiency(buffer));
		using NativeArray<Efficiency> array = buffer.ToNativeArray(Allocator.Temp);
		array.Sort();
		factors.Clear();
		if (array.Length == 0)
		{
			return;
		}
		if (efficiency > 0)
		{
			float num = 100f;
			{
				foreach (Efficiency item in array)
				{
					float num2 = math.max(0f, item.m_Efficiency);
					num *= num2;
					int num3 = math.max(-99, (int)math.round(100f * num2) - 100);
					int result = math.max(1, (int)math.round(num));
					if (num3 != 0)
					{
						factors.Add(new EfficiencyFactor(item.m_Factor, num3, result));
					}
				}
				return;
			}
		}
		foreach (Efficiency item2 in array)
		{
			if (math.max(0f, item2.m_Efficiency) == 0f)
			{
				factors.Add(new EfficiencyFactor(item2.m_Factor, -100, -100));
				if ((int)item2.m_Factor <= 3)
				{
					break;
				}
			}
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
		if (base.visible)
		{
			DynamicBuffer<Efficiency> buffer = base.EntityManager.GetBuffer<Efficiency>(selectedEntity, isReadOnly: true);
			m_Dirty = (int)math.round(100f * BuildingUtils.GetEfficiency(buffer)) != efficiency;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("efficiency");
		writer.Write(efficiency);
		writer.PropertyName("factors");
		writer.ArrayBegin(factors.Count);
		for (int i = 0; i < factors.Count; i++)
		{
			writer.Write(factors[i]);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		efficiency = 0;
		factors.Clear();
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Building>(selectedEntity) && base.EntityManager.HasComponent<Efficiency>(selectedEntity) && !base.EntityManager.HasComponent<Abandoned>(selectedEntity) && !base.EntityManager.HasComponent<Destroyed>(selectedEntity))
		{
			if (CompanyUIUtils.HasCompany(base.EntityManager, selectedEntity, selectedPrefab, out var company))
			{
				return company != Entity.Null;
			}
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.UI.InGame.EfficiencySection+EfficiencyFactor`  

