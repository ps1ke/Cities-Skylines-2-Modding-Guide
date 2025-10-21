# Game.Tutorials.AreaTriggerData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct AreaTriggerData : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Game.Tutorials.AreaTriggerFlags m_Flags;

    public AreaTriggerData(Unity.Entities.Entity prefab, Game.Tutorials.AreaTriggerFlags flags);

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Game.Tutorials.AreaTriggerFlags m_Flags`  

```csharp
public Game.Tutorials.AreaTriggerFlags m_Flags;
```


## Constructors

- `public AreaTriggerData(Unity.Entities.Entity prefab, Game.Tutorials.AreaTriggerFlags flags)`  

```csharp
public AreaTriggerData(Unity.Entities.Entity prefab, Game.Tutorials.AreaTriggerFlags flags);
```


