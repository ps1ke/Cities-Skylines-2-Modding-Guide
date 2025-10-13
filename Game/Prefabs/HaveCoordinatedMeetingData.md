# Game.Prefabs.HaveCoordinatedMeetingData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct HaveCoordinatedMeetingData : Unity.Entities.IBufferElementData
{
    public Game.Citizens.TravelPurpose m_TravelPurpose;
    public Unity.Mathematics.uint2 m_Delay;
    public Unity.Entities.Entity m_Notification;

}
```


## Fields

- `public Game.Citizens.TravelPurpose m_TravelPurpose`  

```csharp
public Game.Citizens.TravelPurpose m_TravelPurpose;
```

- `public Unity.Mathematics.uint2 m_Delay`  

```csharp
public Unity.Mathematics.uint2 m_Delay;
```

- `public Unity.Entities.Entity m_Notification`  

```csharp
public Unity.Entities.Entity m_Notification;
```


