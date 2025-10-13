# Game.Prefabs.AnimalData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct AnimalData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_MoveSpeed;
    public System.Single m_SwimSpeed;
    public System.Single m_FlySpeed;
    public System.Single m_Acceleration;
    public Colossal.Mathematics.Bounds1 m_SwimDepth;
    public Colossal.Mathematics.Bounds1 m_FlyHeight;

}
```


## Fields

- `public System.Single m_MoveSpeed`  

```csharp
public System.Single m_MoveSpeed;
```

- `public System.Single m_SwimSpeed`  

```csharp
public System.Single m_SwimSpeed;
```

- `public System.Single m_FlySpeed`  

```csharp
public System.Single m_FlySpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public Colossal.Mathematics.Bounds1 m_SwimDepth`  

```csharp
public Colossal.Mathematics.Bounds1 m_SwimDepth;
```

- `public Colossal.Mathematics.Bounds1 m_FlyHeight`  

```csharp
public Colossal.Mathematics.Bounds1 m_FlyHeight;
```


