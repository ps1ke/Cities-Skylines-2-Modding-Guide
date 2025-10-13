# Game.UI.InGame.MaintenanceVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MaintenanceVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <workShift>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 workShift { private get; private set; }

    public MaintenanceVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    protected System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <workShift>k__BackingField`  

```csharp
private System.Int32 <workShift>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 workShift { private get; private set }`  

```csharp
private System.Int32 workShift { private get; private set; }
```


## Constructors

- `public MaintenanceVehicleSection()`  

```csharp
[Preserve]
	public MaintenanceVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.MaintenanceVehicle componentData = base.EntityManager.GetComponentData<Game.Vehicles.MaintenanceVehicle>(selectedEntity);
		MaintenanceVehicleData componentData2 = base.EntityManager.GetComponentData<MaintenanceVehicleData>(selectedPrefab);
		componentData2.m_MaintenanceCapacity = Mathf.CeilToInt((float)componentData2.m_MaintenanceCapacity * componentData.m_Efficiency);
		workShift = Mathf.CeilToInt((1f - math.select((float)componentData.m_Maintained / (float)componentData2.m_MaintenanceCapacity, 0f, componentData2.m_MaintenanceCapacity == 0)) * 100f);
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, base.EntityManager);
		base.OnProcess();
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
		base.OnWriteProperties(writer);
		writer.PropertyName("workShift");
		writer.Write(workShift);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		base.Reset();
		workShift = 0;
	}
```

- `protected Visible() : System.Boolean`  

```csharp
protected bool Visible()
	{
		if (base.EntityManager.HasComponent<Owner>(selectedEntity) && base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Game.Vehicles.MaintenanceVehicle>(selectedEntity))
		{
			return base.EntityManager.HasComponent<MaintenanceVehicleData>(selectedPrefab);
		}
		return false;
	}
```


