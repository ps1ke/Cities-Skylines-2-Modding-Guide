# Game.Zones.CellCheckHelpers+BlockOverlap

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Zones.CellCheckHelpers+BlockOverlap>`  

## Code

```csharp
public sealed struct BlockOverlap : System.IComparable<Game.Zones.CellCheckHelpers+BlockOverlap>
{
    public System.Int32 m_Group;
    public System.UInt32 m_Priority;
    public Unity.Entities.Entity m_Block;
    public Unity.Entities.Entity m_Other;
    public Unity.Entities.Entity m_Left;
    public Unity.Entities.Entity m_Right;

    public System.Int32 CompareTo(Game.Zones.CellCheckHelpers+BlockOverlap other);
}
```


## Fields

- `public System.Int32 m_Group`  

```csharp
public System.Int32 m_Group;
```

- `public System.UInt32 m_Priority`  

```csharp
public System.UInt32 m_Priority;
```

- `public Unity.Entities.Entity m_Block`  

```csharp
public Unity.Entities.Entity m_Block;
```

- `public Unity.Entities.Entity m_Other`  

```csharp
public Unity.Entities.Entity m_Other;
```

- `public Unity.Entities.Entity m_Left`  

```csharp
public Unity.Entities.Entity m_Left;
```

- `public Unity.Entities.Entity m_Right`  

```csharp
public Unity.Entities.Entity m_Right;
```


## Methods

- `public CompareTo(Game.Zones.CellCheckHelpers+BlockOverlap other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Zones.CellCheckHelpers+BlockOverlap other);
```


