# Game.Buildings.ServiceUpgradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceUpgradeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpgradeQuery;
    private Unity.Entities.EntityQuery m_UpgradePrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Buildings.ServiceUpgradeSystem+TypeHandle __TypeHandle;

    public ServiceUpgradeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void OwnerDeleted(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades);
    private System.Void UpgradeInstalled(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef);
    private System.Void UpgradeRemoved(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpgradeQuery;
```

- `private Unity.Entities.EntityQuery m_UpgradePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpgradePrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Buildings.ServiceUpgradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ServiceUpgradeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceUpgradeSystem()`  

```csharp
public ServiceUpgradeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private OwnerDeleted(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades) : System.Void`  

```csharp
private System.Void OwnerDeleted(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades);
```

- `private UpgradeInstalled(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef) : System.Void`  

```csharp
private System.Void UpgradeInstalled(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef);
```

- `private UpgradeRemoved(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef) : System.Void`  

```csharp
private System.Void UpgradeRemoved(Unity.Entities.EntityCommandBuffer commandBuffer, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef);
```


## Nested types

- `Game.Buildings.ServiceUpgradeSystem+TypeHandle`  

