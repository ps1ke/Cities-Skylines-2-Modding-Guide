# Game.UI.InGame.PresetDescriptor

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class PresetDescriptor
{
    private System.Collections.Generic.List<System.String> m_OptionsId;
    private System.Collections.Generic.Dictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> m_Values;

    public System.Collections.Generic.IReadOnlyCollection<System.String> optionsId { get; }
    public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> values { get; }

    public PresetDescriptor();

    public System.Void AddOption(System.String optionId);
    public System.Void AddOptions(System.Collections.Generic.IEnumerable<System.String> optionIds);
    public System.Void AddValues(Game.Rendering.CinematicCamera.PhotoModeProperty targetProperty, System.Single[] values);
    public System.Boolean Validate();
}
```


## Fields

- `private System.Collections.Generic.List<System.String> m_OptionsId`  

```csharp
private System.Collections.Generic.List<System.String> m_OptionsId;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> m_Values`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> m_Values;
```


## Properties

- `public System.Collections.Generic.IReadOnlyCollection<System.String> optionsId { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> optionsId { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> values { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> values { get; }
```


## Constructors

- `public PresetDescriptor()`  

```csharp
public PresetDescriptor();
```


## Methods

- `public AddOption(System.String optionId) : System.Void`  

```csharp
public void AddOption(string optionId)
	{
		m_OptionsId.Add(optionId);
	}
```

- `public AddOptions(System.Collections.Generic.IEnumerable<System.String> optionIds) : System.Void`  

```csharp
public void AddOptions(IEnumerable<string> optionIds)
	{
		foreach (string optionId in optionIds)
		{
			AddOption(optionId);
		}
	}
```

- `public AddValues(Game.Rendering.CinematicCamera.PhotoModeProperty targetProperty, System.Single[] values) : System.Void`  

```csharp
public void AddValues(PhotoModeProperty targetProperty, float[] values)
	{
		m_Values.Add(targetProperty, values);
	}
```

- `public Validate() : System.Boolean`  

```csharp
public bool Validate()
	{
		int count = m_OptionsId.Count;
		foreach (KeyValuePair<PhotoModeProperty, float[]> value in m_Values)
		{
			if (value.Value.Length != count)
			{
				return false;
			}
		}
		return true;
	}
```


