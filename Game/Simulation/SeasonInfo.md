# Game.Simulation.ClimateSystem+SeasonInfo

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`  

**Attributes:** `Serializable`  

## Code

```csharp
public class SeasonInfo : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable
{
    public Game.Prefabs.Climate.SeasonPrefab m_Prefab;
    public System.String m_NameID;
    public System.String m_IconPath;
    public System.Single m_StartTime;
    public Unity.Mathematics.float2 m_TempNightDay;
    public Unity.Mathematics.float2 m_TempDeviationNightDay;
    public System.Single m_CloudChance;
    public System.Single m_CloudAmount;
    public System.Single m_CloudAmountDeviation;
    public System.Single m_PrecipitationChance;
    public System.Single m_PrecipitationAmount;
    public System.Single m_PrecipitationAmountDeviation;
    public System.Single m_Turbulence;
    public System.Single m_AuroraAmount;
    public System.Single m_AuroraChance;

    public SeasonInfo();

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.Prefabs.Climate.SeasonPrefab m_Prefab`  

```csharp
public Game.Prefabs.Climate.SeasonPrefab m_Prefab;
```

- `public System.String m_NameID`  

```csharp
public System.String m_NameID;
```

- `public System.String m_IconPath`  

```csharp
public System.String m_IconPath;
```

- `public System.Single m_StartTime`  

```csharp
public System.Single m_StartTime;
```

- `public Unity.Mathematics.float2 m_TempNightDay`  

```csharp
public Unity.Mathematics.float2 m_TempNightDay;
```

- `public Unity.Mathematics.float2 m_TempDeviationNightDay`  

```csharp
public Unity.Mathematics.float2 m_TempDeviationNightDay;
```

- `public System.Single m_CloudChance`  

```csharp
public System.Single m_CloudChance;
```

- `public System.Single m_CloudAmount`  

```csharp
public System.Single m_CloudAmount;
```

- `public System.Single m_CloudAmountDeviation`  

```csharp
public System.Single m_CloudAmountDeviation;
```

- `public System.Single m_PrecipitationChance`  

```csharp
public System.Single m_PrecipitationChance;
```

- `public System.Single m_PrecipitationAmount`  

```csharp
public System.Single m_PrecipitationAmount;
```

- `public System.Single m_PrecipitationAmountDeviation`  

```csharp
public System.Single m_PrecipitationAmountDeviation;
```

- `public System.Single m_Turbulence`  

```csharp
public System.Single m_Turbulence;
```

- `public System.Single m_AuroraAmount`  

```csharp
public System.Single m_AuroraAmount;
```

- `public System.Single m_AuroraChance`  

```csharp
public System.Single m_AuroraChance;
```


## Constructors

- `public SeasonInfo()`  

```csharp
public SeasonInfo();
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


