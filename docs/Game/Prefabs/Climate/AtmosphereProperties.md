# Game.Prefabs.Climate.AtmosphereProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AtmosphereProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisEmissionMultiplier;
    public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisSpeedMultiplier;

    public AtmosphereProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisEmissionMultiplier`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisEmissionMultiplier;
```

- `public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisSpeedMultiplier`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_AuroraBorealisSpeedMultiplier;
```


## Constructors

- `public AtmosphereProperties()`  

```csharp
public AtmosphereProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```


