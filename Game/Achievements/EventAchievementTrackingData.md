# Game.Achievements.EventAchievementTrackingData

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct EventAchievementTrackingData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt32 m_StartFrame;
    public Colossal.PSI.Common.AchievementId m_ID;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt32 m_StartFrame`  

```csharp
public System.UInt32 m_StartFrame;
```

- `public Colossal.PSI.Common.AchievementId m_ID`  

```csharp
public Colossal.PSI.Common.AchievementId m_ID;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


