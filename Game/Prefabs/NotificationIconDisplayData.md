# Game.Prefabs.NotificationIconDisplayData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Unity.Entities.IEnableableComponent`, `Colossal.Serialization.Entities.ISerializable`, `Colossal.Serialization.Entities.ISerializeAsEnabled`  

## Code

```csharp
public sealed struct NotificationIconDisplayData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Unity.Entities.IEnableableComponent, Colossal.Serialization.Entities.ISerializable, Colossal.Serialization.Entities.ISerializeAsEnabled
{
    public Unity.Mathematics.float2 m_MinParams;
    public Unity.Mathematics.float2 m_MaxParams;
    public System.Int32 m_IconIndex;
    public System.UInt32 m_CategoryMask;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_MinParams`  

```csharp
public Unity.Mathematics.float2 m_MinParams;
```

- `public Unity.Mathematics.float2 m_MaxParams`  

```csharp
public Unity.Mathematics.float2 m_MaxParams;
```

- `public System.Int32 m_IconIndex`  

```csharp
public System.Int32 m_IconIndex;
```

- `public System.UInt32 m_CategoryMask`  

```csharp
public System.UInt32 m_CategoryMask;
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


