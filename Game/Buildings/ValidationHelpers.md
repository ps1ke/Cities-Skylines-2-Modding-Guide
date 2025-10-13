# Game.Buildings.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    public static System.Void ValidateBuilding(Unity.Entities.Entity entity, Game.Buildings.Building building, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateUpgrade(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `public static ValidateBuilding(Unity.Entities.Entity entity, Game.Buildings.Building building, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateBuilding(Unity.Entities.Entity entity, Game.Buildings.Building building, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateUpgrade(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateUpgrade(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```


