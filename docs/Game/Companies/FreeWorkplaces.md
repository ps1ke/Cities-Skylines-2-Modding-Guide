# Game.Companies.FreeWorkplaces

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FreeWorkplaces : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_Uneducated;
    public System.Byte m_PoorlyEducated;
    public System.Byte m_Educated;
    public System.Byte m_WellEducated;
    public System.Byte m_HighlyEducated;

    public System.Int32 Count { get; }

    public FreeWorkplaces(Game.Companies.Workplaces free);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetBestFor(System.Int32 level);
    public System.Byte GetFree(System.Int32 level);
    public System.Byte GetLowestFree();
    public System.Void Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level);
    public System.Void Serialize<TWriter>(TWriter writer);
    private System.Void SetFree(System.Int32 level, System.Byte amount);
}
```


## Fields

- `public System.Byte m_Uneducated`  

```csharp
public System.Byte m_Uneducated;
```

- `public System.Byte m_PoorlyEducated`  

```csharp
public System.Byte m_PoorlyEducated;
```

- `public System.Byte m_Educated`  

```csharp
public System.Byte m_Educated;
```

- `public System.Byte m_WellEducated`  

```csharp
public System.Byte m_WellEducated;
```

- `public System.Byte m_HighlyEducated`  

```csharp
public System.Byte m_HighlyEducated;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public FreeWorkplaces(Game.Companies.Workplaces free)`  

```csharp
public FreeWorkplaces(Game.Companies.Workplaces free);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetBestFor(System.Int32 level) : System.Int32`  

```csharp
public System.Int32 GetBestFor(System.Int32 level);
```

- `public GetFree(System.Int32 level) : System.Byte`  

```csharp
public System.Byte GetFree(System.Int32 level);
```

- `public GetLowestFree() : System.Byte`  

```csharp
public System.Byte GetLowestFree();
```

- `public Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level) : System.Void`  

```csharp
public System.Void Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `private SetFree(System.Int32 level, System.Byte amount) : System.Void`  

```csharp
private System.Void SetFree(System.Int32 level, System.Byte amount);
```


