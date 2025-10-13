# Game.Tools.Feedback

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Feedback : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Entities.Entity m_MainEntity;
    public Unity.Entities.Entity m_Prefab;
    public Unity.Entities.Entity m_MainPrefab;
    public System.Boolean m_IsDeleted;

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Entities.Entity m_MainEntity`  

```csharp
public Unity.Entities.Entity m_MainEntity;
```

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Entities.Entity m_MainPrefab`  

```csharp
public Unity.Entities.Entity m_MainPrefab;
```

- `public System.Boolean m_IsDeleted`  

```csharp
public System.Boolean m_IsDeleted;
```


