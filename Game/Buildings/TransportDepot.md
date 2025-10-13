# Game.Buildings.TransportDepot

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportDepot : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Buildings.TransportDepotFlags m_Flags;
    public System.Byte m_AvailableVehicles;
    public System.Single m_MaintenanceRequirement;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Buildings.TransportDepotFlags m_Flags`  

```csharp
public Game.Buildings.TransportDepotFlags m_Flags;
```

- `public System.Byte m_AvailableVehicles`  

```csharp
public System.Byte m_AvailableVehicles;
```

- `public System.Single m_MaintenanceRequirement`  

```csharp
public System.Single m_MaintenanceRequirement;
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


