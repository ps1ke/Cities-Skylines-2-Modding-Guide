# Colossal.ColorUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly Colossal.Logging.ILog log`  
- `private static System.Random kRnd`  

## Properties

- `public static System.Int32 seed { set }`  

## Methods

- `public static GetColor(System.Byte v) : UnityEngine.Color`  
- `public static GetHSV(System.Byte H, System.Byte S, System.Byte V) : UnityEngine.Color`  
- `public static GetTemperatureGradient(System.Single minKelvin = 1500, System.Single maxKelvin = 20000, System.Int32 steps = 8) : UnityEngine.Gradient`  
- `public static NiceRandomColor() : UnityEngine.Color`  
- `public static NiceRandomColor(System.Int32 seed) : UnityEngine.Color`  
- `public static ReadColor(UnityEngine.Vector2 cursorPosHint) : UnityEngine.Color`  
- `public static ReadPixels(UnityEngine.Vector2 cursorPosHint, UnityEngine.Texture2D targetTexture) : System.Void`  
- `public static ReadPixels(System.Single cursorPosHintX, System.Single cursorPosHintY, System.Int32 sizex, System.Int32 sizey, System.Void* ptr) : System.Void`  

