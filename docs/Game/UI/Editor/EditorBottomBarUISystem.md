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
public EditorBottomBarUISystem();
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
protected virtual System.Void OnCreate();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `private ResetCloudiness() : System.Void`  

```csharp
private System.Void ResetCloudiness();
```

- `private ResetDate() : System.Void`  

```csharp
private System.Void ResetDate();
```

- `private ResetTimeOfDay() : System.Void`  

```csharp
private System.Void ResetTimeOfDay();
```

- `private SetCloudiness(System.Single cloudiness) : System.Void`  

```csharp
private System.Void SetCloudiness(System.Single cloudiness);
```

- `private SetDate(System.Single date) : System.Void`  

```csharp
private System.Void SetDate(System.Single date);
```

- `private SetTimeOfDay(System.Single time) : System.Void`  

```csharp
private System.Void SetTimeOfDay(System.Single time);
```


