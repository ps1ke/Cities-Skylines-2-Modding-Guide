# Colossal.ColorUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ColorUtils
{
    private static readonly Colossal.Logging.ILog log;
    private static System.Random kRnd;

    public static System.Int32 seed { set; }

    public static UnityEngine.Color GetColor(System.Byte v);
    public static UnityEngine.Color GetHSV(System.Byte H, System.Byte S, System.Byte V);
    public static UnityEngine.Gradient GetTemperatureGradient(System.Single minKelvin, System.Single maxKelvin, System.Int32 steps);
    public static UnityEngine.Color NiceRandomColor();
    public static UnityEngine.Color NiceRandomColor(System.Int32 seed);
    public static UnityEngine.Color ReadColor(UnityEngine.Vector2 cursorPosHint);
    public static System.Void ReadPixels(UnityEngine.Vector2 cursorPosHint, UnityEngine.Texture2D targetTexture);
    public static System.Void ReadPixels(System.Single cursorPosHintX, System.Single cursorPosHintY, System.Int32 sizex, System.Int32 sizey, System.Void* ptr);
}
```


## Fields

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```

- `private static System.Random kRnd`  

```csharp
private static System.Random kRnd;
```


## Properties

- `public static System.Int32 seed { set }`  

```csharp
public static System.Int32 seed { set; }
```


## Methods

- `public static GetColor(System.Byte v) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color GetColor(System.Byte v);
```

- `public static GetHSV(System.Byte H, System.Byte S, System.Byte V) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color GetHSV(System.Byte H, System.Byte S, System.Byte V);
```

- `public static GetTemperatureGradient(System.Single minKelvin = 1500, System.Single maxKelvin = 20000, System.Int32 steps = 8) : UnityEngine.Gradient`  

```csharp
public static UnityEngine.Gradient GetTemperatureGradient(System.Single minKelvin, System.Single maxKelvin, System.Int32 steps);
```

- `public static NiceRandomColor() : UnityEngine.Color`  

```csharp
public static UnityEngine.Color NiceRandomColor();
```

- `public static NiceRandomColor(System.Int32 seed) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color NiceRandomColor(System.Int32 seed);
```

- `public static ReadColor(UnityEngine.Vector2 cursorPosHint) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color ReadColor(UnityEngine.Vector2 cursorPosHint);
```

- `public static ReadPixels(UnityEngine.Vector2 cursorPosHint, UnityEngine.Texture2D targetTexture) : System.Void`  

```csharp
public static System.Void ReadPixels(UnityEngine.Vector2 cursorPosHint, UnityEngine.Texture2D targetTexture);
```

- `public static ReadPixels(System.Single cursorPosHintX, System.Single cursorPosHintY, System.Int32 sizex, System.Int32 sizey, System.Void* ptr) : System.Void`  

```csharp
public static System.Void ReadPixels(System.Single cursorPosHintX, System.Single cursorPosHintY, System.Int32 sizex, System.Int32 sizey, System.Void* ptr);
```


