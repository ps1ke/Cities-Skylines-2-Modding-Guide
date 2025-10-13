# Game.Rendering.Climate.WeatherPropertiesStack+InterpolatedProperties

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Climate`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class InterpolatedProperties
{
    public System.Single time;
    public Colossal.Mathematics.Bounds1 remapLimits;
    public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent current;
    public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent previous;
    public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent target;
    public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent from;
    public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent to;
    internal Game.Prefabs.Climate.OverrideablePropertiesComponent source;

    public InterpolatedProperties(Game.Prefabs.Climate.OverrideablePropertiesComponent current, Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent target, Game.Prefabs.Climate.OverrideablePropertiesComponent from, Game.Prefabs.Climate.OverrideablePropertiesComponent to);

    public System.Void Advance(System.Single deltaTime, System.Single renderingDeltaTime);
    public System.Single GetLerp(Game.Simulation.ClimateSystem+ClimateSample sample);
    private static System.Single Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2);
    public System.Void SetFrom(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo);
    public System.Void SetPrevious(Game.Prefabs.Climate.OverrideablePropertiesComponent newSource);
    public System.Void SetTarget(Game.Prefabs.Climate.OverrideablePropertiesComponent newTarget);
    public System.Void SetTo(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo);
}
```


## Fields

- `public System.Single time`  

```csharp
public System.Single time;
```

- `public Colossal.Mathematics.Bounds1 remapLimits`  

```csharp
public Colossal.Mathematics.Bounds1 remapLimits;
```

- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent current`  

```csharp
public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent current;
```

- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent previous`  

```csharp
public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent previous;
```

- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent target`  

```csharp
public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent target;
```

- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent from`  

```csharp
public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent from;
```

- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent to`  

```csharp
public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent to;
```

- `internal Game.Prefabs.Climate.OverrideablePropertiesComponent source`  

```csharp
internal Game.Prefabs.Climate.OverrideablePropertiesComponent source;
```


## Constructors

- `public InterpolatedProperties(Game.Prefabs.Climate.OverrideablePropertiesComponent current, Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent target, Game.Prefabs.Climate.OverrideablePropertiesComponent from, Game.Prefabs.Climate.OverrideablePropertiesComponent to)`  

```csharp
public InterpolatedProperties(Game.Prefabs.Climate.OverrideablePropertiesComponent current, Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent target, Game.Prefabs.Climate.OverrideablePropertiesComponent from, Game.Prefabs.Climate.OverrideablePropertiesComponent to);
```


## Methods

- `public Advance(System.Single deltaTime, System.Single renderingDeltaTime) : System.Void`  

```csharp
public System.Void Advance(System.Single deltaTime, System.Single renderingDeltaTime);
```

- `public GetLerp(Game.Simulation.ClimateSystem+ClimateSample sample) : System.Single`  

```csharp
public System.Single GetLerp(Game.Simulation.ClimateSystem+ClimateSample sample);
```

- `private static Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2) : System.Single`  

```csharp
private static System.Single Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2);
```

- `public SetFrom(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo) : System.Void`  

```csharp
public System.Void SetFrom(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo);
```

- `public SetPrevious(Game.Prefabs.Climate.OverrideablePropertiesComponent newSource) : System.Void`  

```csharp
public System.Void SetPrevious(Game.Prefabs.Climate.OverrideablePropertiesComponent newSource);
```

- `public SetTarget(Game.Prefabs.Climate.OverrideablePropertiesComponent newTarget) : System.Void`  

```csharp
public System.Void SetTarget(Game.Prefabs.Climate.OverrideablePropertiesComponent newTarget);
```

- `public SetTo(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo) : System.Void`  

```csharp
public System.Void SetTo(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo);
```


