# Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier

**Assembly:** `Game`  
**Namespace:** `Game.CinematicCamera`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public sealed struct CinematicCameraCurveModifier : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable
{
    private System.String <id>k__BackingField;
    private UnityEngine.AnimationCurve <curve>k__BackingField;
    private System.Single <min>k__BackingField;
    private System.Single <max>k__BackingField;

    public System.String id { get; set; }
    public UnityEngine.AnimationCurve curve { get; set; }
    public System.Single min { get; set; }
    public System.Single max { get; set; }

    public System.Int32 AddKey(System.Single t, System.Single value);
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private UnityEngine.AnimationCurve <curve>k__BackingField`  

```csharp
private UnityEngine.AnimationCurve <curve>k__BackingField;
```

- `private System.Single <min>k__BackingField`  

```csharp
private System.Single <min>k__BackingField;
```

- `private System.Single <max>k__BackingField`  

```csharp
private System.Single <max>k__BackingField;
```


## Properties

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public UnityEngine.AnimationCurve curve { get; set }`  

```csharp
public UnityEngine.AnimationCurve curve { get; set; }
```

- `public System.Single min { get; set }`  

```csharp
public System.Single min { get; set; }
```

- `public System.Single max { get; set }`  

```csharp
public System.Single max { get; set; }
```


## Methods

- `public AddKey(System.Single t, System.Single value) : System.Int32`  

```csharp
public System.Int32 AddKey(System.Single t, System.Single value);
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


