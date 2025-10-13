# Game.Events.Impact

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Impact : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_Target;
    public Unity.Mathematics.float3 m_VelocityDelta;
    public Unity.Mathematics.float3 m_AngularVelocityDelta;
    public System.Single m_Severity;
    public System.Boolean m_CheckStoppedEvent;

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

- `public Unity.Mathematics.float3 m_VelocityDelta`  

```csharp
public Unity.Mathematics.float3 m_VelocityDelta;
```

- `public Unity.Mathematics.float3 m_AngularVelocityDelta`  

```csharp
public Unity.Mathematics.float3 m_AngularVelocityDelta;
```

- `public System.Single m_Severity`  

```csharp
public System.Single m_Severity;
```

- `public System.Boolean m_CheckStoppedEvent`  

```csharp
public System.Boolean m_CheckStoppedEvent;
```


