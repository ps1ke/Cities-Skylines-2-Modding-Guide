# Game.UI.InGame.StatisticsUISystem+StatItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonReadable`, `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.StatisticsUISystem+StatItem>`  

## Code

```csharp
public sealed struct StatItem : Colossal.UI.Binding.IJsonReadable, Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.InGame.StatisticsUISystem+StatItem>
{
    public Unity.Entities.Entity category;
    public Unity.Entities.Entity group;
    public Unity.Entities.Entity entity;
    public System.Int32 statisticType;
    public System.Int32 unitType;
    public System.Int32 parameterIndex;
    public System.String key;
    public UnityEngine.Color color;
    public System.Boolean locked;
    public System.Boolean isGroup;
    public System.Boolean isSubgroup;
    public System.Boolean stacked;
    public System.Int32 priority;

    public StatItem(System.Int32 priority, Unity.Entities.Entity category, Unity.Entities.Entity group, Unity.Entities.Entity entity, System.Int32 statisticType, Game.City.StatisticUnitType unitType, System.Int32 parameterIndex, System.String key, UnityEngine.Color color, System.Boolean locked, System.Boolean isGroup, System.Boolean isSubgroup, System.Boolean stacked);

    public System.Int32 CompareTo(Game.UI.InGame.StatisticsUISystem+StatItem other);
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity category`  

```csharp
public Unity.Entities.Entity category;
```

- `public Unity.Entities.Entity group`  

```csharp
public Unity.Entities.Entity group;
```

- `public Unity.Entities.Entity entity`  

```csharp
public Unity.Entities.Entity entity;
```

- `public System.Int32 statisticType`  

```csharp
public System.Int32 statisticType;
```

- `public System.Int32 unitType`  

```csharp
public System.Int32 unitType;
```

- `public System.Int32 parameterIndex`  

```csharp
public System.Int32 parameterIndex;
```

- `public System.String key`  

```csharp
public System.String key;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
```

- `public System.Boolean locked`  

```csharp
public System.Boolean locked;
```

- `public System.Boolean isGroup`  

```csharp
public System.Boolean isGroup;
```

- `public System.Boolean isSubgroup`  

```csharp
public System.Boolean isSubgroup;
```

- `public System.Boolean stacked`  

```csharp
public System.Boolean stacked;
```

- `public System.Int32 priority`  

```csharp
public System.Int32 priority;
```


## Constructors

- `public StatItem(System.Int32 priority, Unity.Entities.Entity category, Unity.Entities.Entity group, Unity.Entities.Entity entity, System.Int32 statisticType, Game.City.StatisticUnitType unitType, System.Int32 parameterIndex, System.String key, UnityEngine.Color color, System.Boolean locked, System.Boolean isGroup = False, System.Boolean isSubgroup = False, System.Boolean stacked = True)`  

```csharp
public StatItem(System.Int32 priority, Unity.Entities.Entity category, Unity.Entities.Entity group, Unity.Entities.Entity entity, System.Int32 statisticType, Game.City.StatisticUnitType unitType, System.Int32 parameterIndex, System.String key, UnityEngine.Color color, System.Boolean locked, System.Boolean isGroup, System.Boolean isSubgroup, System.Boolean stacked);
```


## Methods

- `public CompareTo(Game.UI.InGame.StatisticsUISystem+StatItem other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.StatisticsUISystem+StatItem other);
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


