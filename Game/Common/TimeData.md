# Game.Common.TimeData

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TimeData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt32 m_FirstFrame;
    public System.Int32 m_StartingYear;
    public System.Byte m_StartingMonth;
    public System.Byte m_StartingHour;
    public System.Byte m_StartingMinutes;

    public System.Single TimeOffset { get; set; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetDateOffset(System.Int32 daysPerYear);
    public static Game.Common.TimeData GetSingleton(Unity.Entities.EntityQuery query);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public System.UInt32 m_FirstFrame`  

```csharp
public System.UInt32 m_FirstFrame;
```

- `public System.Int32 m_StartingYear`  

```csharp
public System.Int32 m_StartingYear;
```

- `public System.Byte m_StartingMonth`  

```csharp
public System.Byte m_StartingMonth;
```

- `public System.Byte m_StartingHour`  

```csharp
public System.Byte m_StartingHour;
```

- `public System.Byte m_StartingMinutes`  

```csharp
public System.Byte m_StartingMinutes;
```


## Properties

- `public System.Single TimeOffset { get; set }`  

```csharp
public System.Single TimeOffset { get; set; }
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetDateOffset(System.Int32 daysPerYear) : System.Single`  

```csharp
public System.Single GetDateOffset(System.Int32 daysPerYear);
```

- `public static GetSingleton(Unity.Entities.EntityQuery query) : Game.Common.TimeData`  

```csharp
public static Game.Common.TimeData GetSingleton(Unity.Entities.EntityQuery query);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


