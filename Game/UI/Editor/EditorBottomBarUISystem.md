# Game.UI.Editor.EditorBottomBarUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorBottomBarUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private static readonly System.String kGroup;

    public Game.GameMode gameMode { get; }
    private System.Single m_NormalizedTimeBindingValue { private get; }
    private System.Single m_NormalizedDateBindingValue { private get; }

    public EditorBottomBarUISystem();

    private System.Single <OnCreate>b__9_0();
    private System.Single <OnCreate>b__9_1();
    private System.Single <OnCreate>b__9_2();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStopRunning();
    private System.Void ResetCloudiness();
    private System.Void ResetDate();
    private System.Void ResetTimeOfDay();
    private System.Void SetCloudiness(System.Single cloudiness);
    private System.Void SetDate(System.Single date);
    private System.Void SetTimeOfDay(System.Single time);
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `private System.Single m_NormalizedTimeBindingValue { private get }`  

```csharp
private System.Single m_NormalizedTimeBindingValue { private get; }
```

- `private System.Single m_NormalizedDateBindingValue { private get }`  

```csharp
private System.Single m_NormalizedDateBindingValue { private get; }
```


## Constructors

- `public EditorBottomBarUISystem()`  

```csharp
[Preserve]
	public EditorBottomBarUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__9_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__9_0();
```

- `private <OnCreate>b__9_1() : System.Single`  

```csharp
private System.Single <OnCreate>b__9_1();
```

- `private <OnCreate>b__9_2() : System.Single`  

```csharp
private System.Single <OnCreate>b__9_2();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "timeOfDay", () => m_NormalizedTimeBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "date", () => m_NormalizedDateBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "cloudiness", () => m_ClimateSystem.cloudiness));
		AddBinding(new TriggerBinding<float>(kGroup, "setTimeOfDay", SetTimeOfDay));
		AddBinding(new TriggerBinding(kGroup, "resetTimeOfDay", ResetTimeOfDay));
		AddBinding(new TriggerBinding<float>(kGroup, "setDate", SetDate));
		AddBinding(new TriggerBinding(kGroup, "resetDate", ResetDate));
		AddBinding(new TriggerBinding<float>(kGroup, "setCloudiness", SetCloudiness));
		AddBinding(new TriggerBinding(kGroup, "resetCloudiness", ResetCloudiness));
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		m_PlanetarySystem.overrideTime = false;
		m_ClimateSystem.currentDate.overrideState = false;
		m_ClimateSystem.cloudiness.overrideState = false;
	}
```

- `private ResetCloudiness() : System.Void`  

```csharp
private void ResetCloudiness()
	{
		m_ClimateSystem.cloudiness.overrideState = false;
	}
```

- `private ResetDate() : System.Void`  

```csharp
private void ResetDate()
	{
		m_ClimateSystem.currentDate.overrideState = false;
	}
```

- `private ResetTimeOfDay() : System.Void`  

```csharp
private void ResetTimeOfDay()
	{
		m_PlanetarySystem.overrideTime = false;
	}
```

- `private SetCloudiness(System.Single cloudiness) : System.Void`  

```csharp
private void SetCloudiness(float cloudiness)
	{
		m_ClimateSystem.cloudiness.overrideValue = cloudiness;
	}
```

- `private SetDate(System.Single date) : System.Void`  

```csharp
private void SetDate(float date)
	{
		m_ClimateSystem.currentDate.overrideValue = date;
	}
```

- `private SetTimeOfDay(System.Single time) : System.Void`  

```csharp
private void SetTimeOfDay(float time)
	{
		m_PlanetarySystem.overrideTime = true;
		m_PlanetarySystem.normalizedTime = time;
	}
```


