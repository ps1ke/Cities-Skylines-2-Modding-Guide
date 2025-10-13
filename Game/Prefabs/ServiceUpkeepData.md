# Game.Prefabs.ServiceUpkeepData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Game.Prefabs.ICombineBuffer<Game.Prefabs.ServiceUpkeepData>`  

## Code

```csharp
public sealed struct ServiceUpkeepData : Unity.Entities.IBufferElementData, Game.Prefabs.ICombineBuffer<Game.Prefabs.ServiceUpkeepData>
{
    public Game.Prefabs.ResourceStack m_Upkeep;
    public System.Boolean m_ScaleWithUsage;

    public Game.Prefabs.ServiceUpkeepData ApplyServiceUsage(System.Single scale);
    public System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> result);
}
```


## Fields

- `public Game.Prefabs.ResourceStack m_Upkeep`  

```csharp
public Game.Prefabs.ResourceStack m_Upkeep;
```

- `public System.Boolean m_ScaleWithUsage`  

```csharp
public System.Boolean m_ScaleWithUsage;
```


## Methods

- `public ApplyServiceUsage(System.Single scale) : Game.Prefabs.ServiceUpkeepData`  

```csharp
public Game.Prefabs.ServiceUpkeepData ApplyServiceUsage(System.Single scale);
```

- `public Combine(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> result) : System.Void`  

```csharp
public System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> result);
```


