# Game.Triggers.RadioTag

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Triggers.RadioTag>`  

## Code

```csharp
public sealed struct RadioTag : System.IEquatable<Game.Triggers.RadioTag>
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_Target;
    public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
    public System.Int32 m_EmergencyFrameDelay;

    public System.Boolean Equals(Game.Triggers.RadioTag other);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Game.Audio.Radio.Radio+SegmentType m_SegmentType`  

```csharp
public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
```

- `public System.Int32 m_EmergencyFrameDelay`  

```csharp
public System.Int32 m_EmergencyFrameDelay;
```


## Methods

- `public Equals(Game.Triggers.RadioTag other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Triggers.RadioTag other);
```


