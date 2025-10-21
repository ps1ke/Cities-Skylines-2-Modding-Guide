# Game.Prefabs.RocketPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.HelicopterPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RocketPrefab : Game.Prefabs.HelicopterPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public RocketPrefab();

    protected virtual Game.Vehicles.HelicopterType GetHelicopterType();
}
```


## Constructors

- `public RocketPrefab()`  

```csharp
public RocketPrefab();
```


## Methods

- `protected virtual GetHelicopterType() : Game.Vehicles.HelicopterType`  

```csharp
protected virtual Game.Vehicles.HelicopterType GetHelicopterType();
```


