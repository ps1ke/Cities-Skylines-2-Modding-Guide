# Game.Events.Endanger

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Endanger : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_Target;
    public Game.Events.DangerFlags m_Flags;
    public System.UInt32 m_EndFrame;

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

- `public Game.Events.DangerFlags m_Flags`  

```csharp
public Game.Events.DangerFlags m_Flags;
```

- `public System.UInt32 m_EndFrame`  

```csharp
public System.UInt32 m_EndFrame;
```


