# Game.UI.Editor.SeasonsField+SeasonCurves

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public sealed struct SeasonCurves : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable
{
    public UnityEngine.AnimationCurve m_Temperature;
    public UnityEngine.AnimationCurve m_Precipitation;
    public UnityEngine.AnimationCurve m_Cloudiness;
    public UnityEngine.AnimationCurve m_Aurora;
    public UnityEngine.AnimationCurve m_Fog;

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public UnityEngine.AnimationCurve m_Temperature`  

```csharp
public UnityEngine.AnimationCurve m_Temperature;
```

- `public UnityEngine.AnimationCurve m_Precipitation`  

```csharp
public UnityEngine.AnimationCurve m_Precipitation;
```

- `public UnityEngine.AnimationCurve m_Cloudiness`  

```csharp
public UnityEngine.AnimationCurve m_Cloudiness;
```

- `public UnityEngine.AnimationCurve m_Aurora`  

```csharp
public UnityEngine.AnimationCurve m_Aurora;
```

- `public UnityEngine.AnimationCurve m_Fog`  

```csharp
public UnityEngine.AnimationCurve m_Fog;
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


