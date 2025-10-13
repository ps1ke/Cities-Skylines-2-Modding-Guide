# Game.UI.InGame.IUniqueAssetTrackingSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IUniqueAssetTrackingSystem
{
    public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; }
    public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }

}
```


## Properties

- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get }`  

```csharp
public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; }
```

- `public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }
```


