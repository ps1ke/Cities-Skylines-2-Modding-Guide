# Game.Rendering.OptionalProperties

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Rendering.IOptionalProperties<Game.Rendering.OptionalProperties>`, `System.IEquatable<Game.Rendering.OptionalProperties>`  

## Code

```csharp
public sealed struct OptionalProperties : Colossal.Rendering.IOptionalProperties<Game.Rendering.OptionalProperties>, System.IEquatable<Game.Rendering.OptionalProperties>
{
    private Game.Rendering.BatchFlags m_Flags;
    private Game.Prefabs.MeshType m_MeshTypes;

    public OptionalProperties(Game.Rendering.BatchFlags flags, Game.Prefabs.MeshType meshTypes);

    public System.Boolean EnableProperty(Game.Rendering.OptionalProperties required);
    public System.Boolean Equals(Game.Rendering.OptionalProperties other);
    public System.Boolean MergeRequirements(Game.Rendering.OptionalProperties other);
}
```


## Fields

- `private Game.Rendering.BatchFlags m_Flags`  

```csharp
private Game.Rendering.BatchFlags m_Flags;
```

- `private Game.Prefabs.MeshType m_MeshTypes`  

```csharp
private Game.Prefabs.MeshType m_MeshTypes;
```


## Constructors

- `public OptionalProperties(Game.Rendering.BatchFlags flags, Game.Prefabs.MeshType meshTypes)`  

```csharp
public OptionalProperties(BatchFlags flags, MeshType meshTypes)
	{
		m_Flags = flags;
		m_MeshTypes = meshTypes;
	}
```


## Methods

- `public EnableProperty(Game.Rendering.OptionalProperties required) : System.Boolean`  

```csharp
public bool EnableProperty(OptionalProperties required)
	{
		if ((m_Flags & required.m_Flags) == required.m_Flags)
		{
			if ((m_MeshTypes & required.m_MeshTypes) == 0)
			{
				return required.m_MeshTypes == (MeshType)0;
			}
			return true;
		}
		return false;
	}
```

- `public Equals(Game.Rendering.OptionalProperties other) : System.Boolean`  

```csharp
public bool Equals(OptionalProperties other)
	{
		if (m_Flags == other.m_Flags)
		{
			return m_MeshTypes == other.m_MeshTypes;
		}
		return false;
	}
```

- `public MergeRequirements(Game.Rendering.OptionalProperties other) : System.Boolean`  

```csharp
public bool MergeRequirements(OptionalProperties other)
	{
		m_MeshTypes |= other.m_MeshTypes;
		return m_Flags == other.m_Flags;
	}
```


