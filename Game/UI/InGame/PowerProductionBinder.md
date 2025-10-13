# Game.UI.InGame.PrefabUISystem+PowerProductionBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+ElectricityPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class PowerProductionBinder : Game.UI.InGame.PrefabUISystem+ElectricityPropertyBinder, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public PowerProductionBinder();

    public static System.Void AddValues(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
    public virtual System.Void GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
    public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public PowerProductionBinder()`  

```csharp
public PowerProductionBinder();
```


## Methods

- `public static AddValues(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers) : System.Void`  

```csharp
public static System.Void AddValues(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
```

- `public virtual GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers) : System.Void`  

```csharp
public virtual System.Void GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers);
```

- `public virtual Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


