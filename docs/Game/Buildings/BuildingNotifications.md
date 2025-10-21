# Game.Buildings.BuildingNotifications

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct BuildingNotifications : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Buildings.BuildingNotification m_Notifications;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean HasNotification(Game.Buildings.BuildingNotification notification);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Buildings.BuildingNotification m_Notifications`  

```csharp
public Game.Buildings.BuildingNotification m_Notifications;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public HasNotification(Game.Buildings.BuildingNotification notification) : System.Boolean`  

```csharp
public System.Boolean HasNotification(Game.Buildings.BuildingNotification notification);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


