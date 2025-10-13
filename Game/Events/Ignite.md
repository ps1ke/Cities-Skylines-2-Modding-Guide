# Game.Events.Ignite

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Ignite : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_Target;
    public System.Single m_Intensity;
    public System.UInt32 m_RequestFrame;

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

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public System.UInt32 m_RequestFrame`  

```csharp
public System.UInt32 m_RequestFrame;
```


