# Game.Triggers.TriggerAction

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TriggerAction
{
    public Game.Triggers.TriggerType m_TriggerType;
    public Unity.Entities.Entity m_TriggerPrefab;
    public Unity.Entities.Entity m_PrimaryTarget;
    public Unity.Entities.Entity m_SecondaryTarget;
    public System.Single m_Value;

    public TriggerAction(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity primaryTarget, Unity.Entities.Entity secondaryTarget, System.Single value);
    public TriggerAction(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab, System.Single value);

}
```


## Fields

- `public Game.Triggers.TriggerType m_TriggerType`  

```csharp
public Game.Triggers.TriggerType m_TriggerType;
```

- `public Unity.Entities.Entity m_TriggerPrefab`  

```csharp
public Unity.Entities.Entity m_TriggerPrefab;
```

- `public Unity.Entities.Entity m_PrimaryTarget`  

```csharp
public Unity.Entities.Entity m_PrimaryTarget;
```

- `public Unity.Entities.Entity m_SecondaryTarget`  

```csharp
public Unity.Entities.Entity m_SecondaryTarget;
```

- `public System.Single m_Value`  

```csharp
public System.Single m_Value;
```


## Constructors

- `public TriggerAction(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity primaryTarget, Unity.Entities.Entity secondaryTarget, System.Single value = 0)`  

```csharp
public TriggerAction(TriggerType triggerType, Entity triggerPrefab, float value)
	{
		m_TriggerType = triggerType;
		m_TriggerPrefab = triggerPrefab;
		m_PrimaryTarget = Entity.Null;
		m_SecondaryTarget = Entity.Null;
		m_Value = value;
	}
```

- `public TriggerAction(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab, System.Single value)`  

```csharp
public TriggerAction(TriggerType triggerType, Entity triggerPrefab, float value)
	{
		m_TriggerType = triggerType;
		m_TriggerPrefab = triggerPrefab;
		m_PrimaryTarget = Entity.Null;
		m_SecondaryTarget = Entity.Null;
		m_Value = value;
	}
```


