# Game.Prefabs.PostConfigurationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PostConfigurationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_PostServicePrefab;
    public System.Int32 m_MaxMailAccumulation;
    public System.Int32 m_MailAccumulationTolerance;
    public System.Int32 m_OutgoingMailPercentage;

}
```


## Fields

- `public Unity.Entities.Entity m_PostServicePrefab`  

```csharp
public Unity.Entities.Entity m_PostServicePrefab;
```

- `public System.Int32 m_MaxMailAccumulation`  

```csharp
public System.Int32 m_MaxMailAccumulation;
```

- `public System.Int32 m_MailAccumulationTolerance`  

```csharp
public System.Int32 m_MailAccumulationTolerance;
```

- `public System.Int32 m_OutgoingMailPercentage`  

```csharp
public System.Int32 m_OutgoingMailPercentage;
```


