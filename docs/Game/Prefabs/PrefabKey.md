# Game.Prefabs.TriggerPrefabData+PrefabKey

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.TriggerPrefabData+PrefabKey>`  

## Code

```csharp
public sealed struct PrefabKey : System.IEquatable<Game.Prefabs.TriggerPrefabData+PrefabKey>
{
    public Game.Triggers.TriggerType m_TriggerType;
    public Unity.Entities.Entity m_TriggerEntity;

    public System.Boolean Equals(Game.Prefabs.TriggerPrefabData+PrefabKey other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Game.Triggers.TriggerType m_TriggerType`  

```csharp
public Game.Triggers.TriggerType m_TriggerType;
```

- `public Unity.Entities.Entity m_TriggerEntity`  

```csharp
public Unity.Entities.Entity m_TriggerEntity;
```


## Methods

- `public Equals(Game.Prefabs.TriggerPrefabData+PrefabKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.TriggerPrefabData+PrefabKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


