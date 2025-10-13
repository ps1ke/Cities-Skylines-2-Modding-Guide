# Game.UI.Widgets.WidgetAttributeUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class WidgetAttributeUtils
{
    public static System.Boolean AllowsMinGreaterMax(System.Object[] attributes);
    public static System.Void GetColorUsage(System.Object[] attributes, System.Boolean& hdr, System.Boolean& showAlpha);
    public static System.Type GetCustomFieldFactory(System.Object[] attributes);
    public static System.Boolean GetNumberRange(System.Object[] attributes, System.Int32& min, System.Int32& max);
    public static System.Boolean GetNumberRange(System.Object[] attributes, System.UInt32& min, System.UInt32& max);
    public static System.Boolean GetNumberRange(System.Object[] attributes, System.Single& min, System.Single& max);
    public static System.Boolean GetNumberRange(System.Object[] attributes, Unity.Mathematics.float4& min, Unity.Mathematics.float4& max);
    public static System.Boolean GetNumberRange(System.Object[] attributes, System.Double& min, System.Double& max);
    public static System.Int32 GetNumberStep(System.Object[] attributes, System.Int32 defaultStep);
    public static System.UInt32 GetNumberStep(System.Object[] attributes, System.UInt32 defaultStep);
    public static System.Single GetNumberStep(System.Object[] attributes, System.Single defaultStep);
    public static System.Double GetNumberStep(System.Object[] attributes, System.Double defaultStep);
    public static System.String GetNumberUnit(System.Object[] attributes);
    public static System.Boolean IsTimeField(System.Object[] attributes);
    public static System.Boolean RequiresInputField(System.Object[] attributes);
}
```


## Methods

- `public static AllowsMinGreaterMax(System.Object[] attributes) : System.Boolean`  

```csharp
public static bool AllowsMinGreaterMax(object[] attributes)
	{
		return attributes.OfType<AllowMinGreaterMaxAttribute>().Any();
	}
```

- `public static GetColorUsage(System.Object[] attributes, System.Boolean& hdr, System.Boolean& showAlpha) : System.Void`  

```csharp
public static void GetColorUsage(object[] attributes, ref bool hdr, ref bool showAlpha)
	{
		ColorUsageAttribute colorUsageAttribute = attributes.OfType<ColorUsageAttribute>().FirstOrDefault();
		if (colorUsageAttribute != null)
		{
			hdr = colorUsageAttribute.hdr;
			showAlpha = colorUsageAttribute.showAlpha;
		}
	}
```

- `public static GetCustomFieldFactory(System.Object[] attributes) : System.Type`  

```csharp
public static Type GetCustomFieldFactory(object[] attributes)
	{
		return attributes.OfType<CustomFieldAttribute>().FirstOrDefault()?.Factory;
	}
```

- `public static GetNumberRange(System.Object[] attributes, System.Int32& min, System.Int32& max) : System.Boolean`  

```csharp
public static bool GetNumberRange(object[] attributes, ref double min, ref double max)
	{
		RangeAttribute rangeAttribute = attributes.OfType<RangeAttribute>().FirstOrDefault();
		if (rangeAttribute != null)
		{
			min = rangeAttribute.min;
			max = rangeAttribute.max;
			return true;
		}
		RangeNAttribute rangeNAttribute = attributes.OfType<RangeNAttribute>().FirstOrDefault();
		if (rangeNAttribute != null)
		{
			min = rangeNAttribute.min.x;
			max = rangeNAttribute.max.x;
			return true;
		}
		return false;
	}
```

- `public static GetNumberRange(System.Object[] attributes, System.UInt32& min, System.UInt32& max) : System.Boolean`  

```csharp
public static bool GetNumberRange(object[] attributes, ref double min, ref double max)
	{
		RangeAttribute rangeAttribute = attributes.OfType<RangeAttribute>().FirstOrDefault();
		if (rangeAttribute != null)
		{
			min = rangeAttribute.min;
			max = rangeAttribute.max;
			return true;
		}
		RangeNAttribute rangeNAttribute = attributes.OfType<RangeNAttribute>().FirstOrDefault();
		if (rangeNAttribute != null)
		{
			min = rangeNAttribute.min.x;
			max = rangeNAttribute.max.x;
			return true;
		}
		return false;
	}
```

- `public static GetNumberRange(System.Object[] attributes, System.Single& min, System.Single& max) : System.Boolean`  

```csharp
public static bool GetNumberRange(object[] attributes, ref double min, ref double max)
	{
		RangeAttribute rangeAttribute = attributes.OfType<RangeAttribute>().FirstOrDefault();
		if (rangeAttribute != null)
		{
			min = rangeAttribute.min;
			max = rangeAttribute.max;
			return true;
		}
		RangeNAttribute rangeNAttribute = attributes.OfType<RangeNAttribute>().FirstOrDefault();
		if (rangeNAttribute != null)
		{
			min = rangeNAttribute.min.x;
			max = rangeNAttribute.max.x;
			return true;
		}
		return false;
	}
```

- `public static GetNumberRange(System.Object[] attributes, Unity.Mathematics.float4& min, Unity.Mathematics.float4& max) : System.Boolean`  

```csharp
public static bool GetNumberRange(object[] attributes, ref double min, ref double max)
	{
		RangeAttribute rangeAttribute = attributes.OfType<RangeAttribute>().FirstOrDefault();
		if (rangeAttribute != null)
		{
			min = rangeAttribute.min;
			max = rangeAttribute.max;
			return true;
		}
		RangeNAttribute rangeNAttribute = attributes.OfType<RangeNAttribute>().FirstOrDefault();
		if (rangeNAttribute != null)
		{
			min = rangeNAttribute.min.x;
			max = rangeNAttribute.max.x;
			return true;
		}
		return false;
	}
```

- `public static GetNumberRange(System.Object[] attributes, System.Double& min, System.Double& max) : System.Boolean`  

```csharp
public static bool GetNumberRange(object[] attributes, ref double min, ref double max)
	{
		RangeAttribute rangeAttribute = attributes.OfType<RangeAttribute>().FirstOrDefault();
		if (rangeAttribute != null)
		{
			min = rangeAttribute.min;
			max = rangeAttribute.max;
			return true;
		}
		RangeNAttribute rangeNAttribute = attributes.OfType<RangeNAttribute>().FirstOrDefault();
		if (rangeNAttribute != null)
		{
			min = rangeNAttribute.min.x;
			max = rangeNAttribute.max.x;
			return true;
		}
		return false;
	}
```

- `public static GetNumberStep(System.Object[] attributes, System.Int32 defaultStep = 1) : System.Int32`  

```csharp
public static double GetNumberStep(object[] attributes, double defaultStep = 0.01)
	{
		NumberStepAttribute numberStepAttribute = attributes.OfType<NumberStepAttribute>().FirstOrDefault();
		if (numberStepAttribute == null || !(numberStepAttribute.Step > 0f))
		{
			return defaultStep;
		}
		return numberStepAttribute.Step;
	}
```

- `public static GetNumberStep(System.Object[] attributes, System.UInt32 defaultStep = 1) : System.UInt32`  

```csharp
public static double GetNumberStep(object[] attributes, double defaultStep = 0.01)
	{
		NumberStepAttribute numberStepAttribute = attributes.OfType<NumberStepAttribute>().FirstOrDefault();
		if (numberStepAttribute == null || !(numberStepAttribute.Step > 0f))
		{
			return defaultStep;
		}
		return numberStepAttribute.Step;
	}
```

- `public static GetNumberStep(System.Object[] attributes, System.Single defaultStep = 0,01) : System.Single`  

```csharp
public static double GetNumberStep(object[] attributes, double defaultStep = 0.01)
	{
		NumberStepAttribute numberStepAttribute = attributes.OfType<NumberStepAttribute>().FirstOrDefault();
		if (numberStepAttribute == null || !(numberStepAttribute.Step > 0f))
		{
			return defaultStep;
		}
		return numberStepAttribute.Step;
	}
```

- `public static GetNumberStep(System.Object[] attributes, System.Double defaultStep = 0,01) : System.Double`  

```csharp
public static double GetNumberStep(object[] attributes, double defaultStep = 0.01)
	{
		NumberStepAttribute numberStepAttribute = attributes.OfType<NumberStepAttribute>().FirstOrDefault();
		if (numberStepAttribute == null || !(numberStepAttribute.Step > 0f))
		{
			return defaultStep;
		}
		return numberStepAttribute.Step;
	}
```

- `public static GetNumberUnit(System.Object[] attributes) : System.String`  

```csharp
[CanBeNull]
	public static string GetNumberUnit(object[] attributes)
	{
		return attributes.OfType<NumberUnitAttribute>().FirstOrDefault()?.Unit;
	}
```

- `public static IsTimeField(System.Object[] attributes) : System.Boolean`  

```csharp
public static bool IsTimeField(object[] attributes)
	{
		return attributes.OfType<TimeFieldAttribute>().Any();
	}
```

- `public static RequiresInputField(System.Object[] attributes) : System.Boolean`  

```csharp
public static bool RequiresInputField(object[] attributes)
	{
		return attributes.OfType<InputFieldAttribute>().Any();
	}
```


