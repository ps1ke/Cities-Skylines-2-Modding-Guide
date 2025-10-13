# Game.Prefabs.Climate.WeatherPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WeatherPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Climate.WeatherPrefab+RandomizationLayer m_RandomizationLayer;
    public Unity.Mathematics.float2 m_CloudinessRange;
    public Game.Simulation.ClimateSystem+WeatherClassification m_Classification;
    private System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> <overrideableProperties>k__BackingField;

    public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> overrideableProperties { get; private set; }

    public WeatherPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual System.Void OnEnable();
}
```


## Fields

- `public Game.Prefabs.Climate.WeatherPrefab+RandomizationLayer m_RandomizationLayer`  

```csharp
public Game.Prefabs.Climate.WeatherPrefab+RandomizationLayer m_RandomizationLayer;
```

- `public Unity.Mathematics.float2 m_CloudinessRange`  

```csharp
public Unity.Mathematics.float2 m_CloudinessRange;
```

- `public Game.Simulation.ClimateSystem+WeatherClassification m_Classification`  

```csharp
public Game.Simulation.ClimateSystem+WeatherClassification m_Classification;
```

- `private System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> <overrideableProperties>k__BackingField`  

```csharp
private System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> <overrideableProperties>k__BackingField;
```


## Properties

- `public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> overrideableProperties { get; private set }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.Climate.OverrideablePropertiesComponent> overrideableProperties { get; private set; }
```


## Constructors

- `public WeatherPrefab()`  

```csharp
public WeatherPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual System.Void OnEnable();
```


## Nested types

- `Game.Prefabs.Climate.WeatherPrefab+RandomizationLayer`  

