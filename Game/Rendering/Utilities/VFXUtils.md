# Game.Rendering.Utilities.VFXUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class VFXUtils
{
    public static System.Boolean SetCheckedFloat(UnityEngine.VFX.VisualEffect effect, System.Int32 id, System.Single v);
    public static System.Boolean SetCheckedInt(UnityEngine.VFX.VisualEffect effect, System.Int32 id, System.Int32 v);
    public static System.Boolean SetCheckedTexture(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Texture v);
    public static System.Boolean SetCheckedVector3(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Vector3 v);
    public static System.Boolean SetCheckedVector4(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Vector4 v);
}
```


## Methods

- `public static SetCheckedFloat(UnityEngine.VFX.VisualEffect effect, System.Int32 id, System.Single v) : System.Boolean`  

```csharp
public static bool SetCheckedFloat(this VisualEffect effect, int id, float v)
	{
		if (effect.HasFloat(id))
		{
			effect.SetFloat(id, v);
			return true;
		}
		return false;
	}
```

- `public static SetCheckedInt(UnityEngine.VFX.VisualEffect effect, System.Int32 id, System.Int32 v) : System.Boolean`  

```csharp
public static bool SetCheckedInt(this VisualEffect effect, int id, int v)
	{
		if (effect.HasInt(id))
		{
			effect.SetInt(id, v);
			return true;
		}
		return false;
	}
```

- `public static SetCheckedTexture(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Texture v) : System.Boolean`  

```csharp
public static bool SetCheckedTexture(this VisualEffect effect, int id, Texture v)
	{
		if (effect.HasTexture(id))
		{
			effect.SetTexture(id, v);
			return true;
		}
		return false;
	}
```

- `public static SetCheckedVector3(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Vector3 v) : System.Boolean`  

```csharp
public static bool SetCheckedVector3(this VisualEffect effect, int id, Vector3 v)
	{
		if (effect.HasVector3(id))
		{
			effect.SetVector3(id, v);
			return true;
		}
		return false;
	}
```

- `public static SetCheckedVector4(UnityEngine.VFX.VisualEffect effect, System.Int32 id, UnityEngine.Vector4 v) : System.Boolean`  

```csharp
public static bool SetCheckedVector4(this VisualEffect effect, int id, Vector4 v)
	{
		if (effect.HasVector4(id))
		{
			effect.SetVector4(id, v);
			return true;
		}
		return false;
	}
```


