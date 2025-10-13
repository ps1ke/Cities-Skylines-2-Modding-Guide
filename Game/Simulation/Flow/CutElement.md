# Game.Simulation.Flow.CutElement

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CutElement
{
    public Game.Simulation.Flow.CutElementFlags m_Flags;
    public System.Int32 m_StartNode;
    public System.Int32 m_EndNode;
    public System.Int32 m_Edge;
    public System.Int32 m_Group;
    public System.Int32 m_Version;
    public System.Int32 m_LinkedElements;
    public System.Int32 m_NextIndex;

    public System.Boolean isCreated { get; set; }
    public System.Boolean isAdmissible { get; set; }
    public System.Boolean isChanged { get; set; }
    public System.Boolean isDeleted { get; set; }

    private System.Boolean GetFlag(Game.Simulation.Flow.CutElementFlags flag);
    private System.Void SetFlag(Game.Simulation.Flow.CutElementFlags flag, System.Boolean value);
}
```


## Fields

- `public Game.Simulation.Flow.CutElementFlags m_Flags`  

```csharp
public Game.Simulation.Flow.CutElementFlags m_Flags;
```

- `public System.Int32 m_StartNode`  

```csharp
public System.Int32 m_StartNode;
```

- `public System.Int32 m_EndNode`  

```csharp
public System.Int32 m_EndNode;
```

- `public System.Int32 m_Edge`  

```csharp
public System.Int32 m_Edge;
```

- `public System.Int32 m_Group`  

```csharp
public System.Int32 m_Group;
```

- `public System.Int32 m_Version`  

```csharp
public System.Int32 m_Version;
```

- `public System.Int32 m_LinkedElements`  

```csharp
public System.Int32 m_LinkedElements;
```

- `public System.Int32 m_NextIndex`  

```csharp
public System.Int32 m_NextIndex;
```


## Properties

- `public System.Boolean isCreated { get; set }`  

```csharp
public System.Boolean isCreated { get; set; }
```

- `public System.Boolean isAdmissible { get; set }`  

```csharp
public System.Boolean isAdmissible { get; set; }
```

- `public System.Boolean isChanged { get; set }`  

```csharp
public System.Boolean isChanged { get; set; }
```

- `public System.Boolean isDeleted { get; set }`  

```csharp
public System.Boolean isDeleted { get; set; }
```


## Methods

- `private GetFlag(Game.Simulation.Flow.CutElementFlags flag) : System.Boolean`  

```csharp
private bool GetFlag(CutElementFlags flag)
	{
		return (m_Flags & flag) != 0;
	}
```

- `private SetFlag(Game.Simulation.Flow.CutElementFlags flag, System.Boolean value) : System.Void`  

```csharp
private void SetFlag(CutElementFlags flag, bool value)
	{
		if (value)
		{
			m_Flags |= flag;
		}
		else
		{
			m_Flags &= ~flag;
		}
	}
```


