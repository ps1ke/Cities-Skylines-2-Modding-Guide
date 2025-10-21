# Game.Notifications.Animation

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Animation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Timer;
    public System.Single m_Duration;
    public Game.Notifications.AnimationType m_Type;

    public Animation(Game.Notifications.AnimationType type, System.Single timer, System.Single duration);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Timer`  

```csharp
public System.Single m_Timer;
```

- `public System.Single m_Duration`  

```csharp
public System.Single m_Duration;
```

- `public Game.Notifications.AnimationType m_Type`  

```csharp
public Game.Notifications.AnimationType m_Type;
```


## Constructors

- `public Animation(Game.Notifications.AnimationType type, System.Single timer, System.Single duration)`  

```csharp
public Animation(Game.Notifications.AnimationType type, System.Single timer, System.Single duration);
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


