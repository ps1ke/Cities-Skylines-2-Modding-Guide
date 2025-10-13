# Game.Rendering.AnimatedSystem+ClipPriorityData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Rendering.AnimatedSystem+ClipPriorityData>`  

## Code

```csharp
public sealed struct ClipPriorityData : System.IComparable<Game.Rendering.AnimatedSystem+ClipPriorityData>
{
    public Game.Rendering.AnimatedSystem+ClipIndex m_ClipIndex;
    public System.Int32 m_Priority;
    public System.Boolean m_IsLoading;
    public System.Boolean m_IsLoaded;

    public System.Int32 CompareTo(Game.Rendering.AnimatedSystem+ClipPriorityData other);
}
```


## Fields

- `public Game.Rendering.AnimatedSystem+ClipIndex m_ClipIndex`  

```csharp
public Game.Rendering.AnimatedSystem+ClipIndex m_ClipIndex;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Boolean m_IsLoading`  

```csharp
public System.Boolean m_IsLoading;
```

- `public System.Boolean m_IsLoaded`  

```csharp
public System.Boolean m_IsLoaded;
```


## Methods

- `public CompareTo(Game.Rendering.AnimatedSystem+ClipPriorityData other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Rendering.AnimatedSystem+ClipPriorityData other);
```


