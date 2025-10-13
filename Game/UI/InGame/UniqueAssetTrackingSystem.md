# Game.UI.InGame.UniqueAssetTrackingSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.InGame.IUniqueAssetTrackingSystem`  

## Code

```csharp
public class UniqueAssetTrackingSystem : Game.GameSystemBase, Game.UI.InGame.IUniqueAssetTrackingSystem
{
    private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery;
    private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery;
    private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery;
    private System.Boolean m_Loaded;
    private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField;
    private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField;

    public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set; }
    public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }

    public UniqueAssetTrackingSystem();

    private System.Boolean GetLoaded();
    public System.Boolean IsPlacedUniqueAsset(Unity.Entities.Entity entity);
    public System.Boolean IsUniqueAsset(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery;
```

- `private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField`  

```csharp
private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField;
```

- `private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField`  

```csharp
private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField;
```


## Properties

- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set }`  

```csharp
public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set; }
```

- `public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }
```


## Constructors

- `public UniqueAssetTrackingSystem()`  

```csharp
public UniqueAssetTrackingSystem();
```


## Methods

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public IsPlacedUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean IsPlacedUniqueAsset(Unity.Entities.Entity entity);
```

- `public IsUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean IsUniqueAsset(Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


