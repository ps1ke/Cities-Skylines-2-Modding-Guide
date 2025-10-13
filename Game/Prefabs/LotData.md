# Game.Prefabs.LotData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LotData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_MaxRadius;
    public UnityEngine.Color32 m_RangeColor;
    public System.Boolean m_OnWater;
    public System.Boolean m_AllowOverlap;

    public LotData(System.Single maxRadius, UnityEngine.Color32 rangeColor, System.Boolean onWater, System.Boolean allowOverlap);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_MaxRadius`  

```csharp
public System.Single m_MaxRadius;
```

- `public UnityEngine.Color32 m_RangeColor`  

```csharp
public UnityEngine.Color32 m_RangeColor;
```

- `public System.Boolean m_OnWater`  

```csharp
public System.Boolean m_OnWater;
```

- `public System.Boolean m_AllowOverlap`  

```csharp
public System.Boolean m_AllowOverlap;
```


## Constructors

- `public LotData(System.Single maxRadius, UnityEngine.Color32 rangeColor, System.Boolean onWater, System.Boolean allowOverlap)`  

```csharp
public LotData(System.Single maxRadius, UnityEngine.Color32 rangeColor, System.Boolean onWater, System.Boolean allowOverlap);
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


