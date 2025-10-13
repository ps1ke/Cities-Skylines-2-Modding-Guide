# Game.Vehicles.AircraftNavigation

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AircraftNavigation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_TargetPosition;
    public Unity.Mathematics.float3 m_TargetDirection;
    public System.Single m_MaxSpeed;
    public System.Single m_MinClimbAngle;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_TargetPosition`  

```csharp
public Unity.Mathematics.float3 m_TargetPosition;
```

- `public Unity.Mathematics.float3 m_TargetDirection`  

```csharp
public Unity.Mathematics.float3 m_TargetDirection;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_MinClimbAngle`  

```csharp
public System.Single m_MinClimbAngle;
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


