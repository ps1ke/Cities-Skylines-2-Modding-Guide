# Game.Objects.Attached

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Attached : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Parent;
    public Unity.Entities.Entity m_OldParent;
    public System.Single m_CurvePosition;

    public Attached(Unity.Entities.Entity parent, Unity.Entities.Entity oldParent, System.Single curvePosition);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Parent`  

```csharp
public Unity.Entities.Entity m_Parent;
```

- `public Unity.Entities.Entity m_OldParent`  

```csharp
public Unity.Entities.Entity m_OldParent;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```


## Constructors

- `public Attached(Unity.Entities.Entity parent, Unity.Entities.Entity oldParent, System.Single curvePosition)`  

```csharp
public Attached(Entity parent, Entity oldParent, float curvePosition)
	{
		m_Parent = parent;
		m_OldParent = oldParent;
		m_CurvePosition = curvePosition;
	}
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


