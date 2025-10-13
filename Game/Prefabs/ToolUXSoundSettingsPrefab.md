# Game.Prefabs.ToolUXSoundSettingsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ToolUXSoundSettingsPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_PolygonToolSelectPointSound;
    public Game.Prefabs.PrefabBase m_PolygonToolDropPointSound;
    public Game.Prefabs.PrefabBase m_PolygonToolRemovePointSound;
    public Game.Prefabs.PrefabBase m_PolygonToolDeleteAreaSound;
    public Game.Prefabs.PrefabBase m_PolygonToolFinishAreaSound;
    public Game.Prefabs.PrefabBase m_BulldozeSound;
    public Game.Prefabs.PrefabBase m_PropPlantBulldozeSound;
    public Game.Prefabs.PrefabBase m_TerraformSound;
    public Game.Prefabs.PrefabBase m_PlaceBuildingSound;
    public Game.Prefabs.PrefabBase m_RelocateBuildingSound;
    public Game.Prefabs.PrefabBase m_PlaceUpgradeSound;
    public Game.Prefabs.PrefabBase m_PlacePropSound;
    public Game.Prefabs.PrefabBase m_PlaceBuildingFailSound;
    public Game.Prefabs.PrefabBase m_ZoningFillSound;
    public Game.Prefabs.PrefabBase m_ZoningRemoveFillSound;
    public Game.Prefabs.PrefabBase m_ZoningStartPaintSound;
    public Game.Prefabs.PrefabBase m_ZoningEndPaintSound;
    public Game.Prefabs.PrefabBase m_ZoningStartRemovePaintSound;
    public Game.Prefabs.PrefabBase m_ZoningEndRemovePaintSound;
    public Game.Prefabs.PrefabBase m_ZoningMarqueeStartSound;
    public Game.Prefabs.PrefabBase m_ZoningMarqueeEndSound;
    public Game.Prefabs.PrefabBase m_ZoningMarqueeClearStartSound;
    public Game.Prefabs.PrefabBase m_ZoningMarqueeClearEndSound;
    public Game.Prefabs.PrefabBase m_SelectEntitySound;
    public Game.Prefabs.PrefabBase m_SnapSound;
    public Game.Prefabs.PrefabBase m_NetExpandSound;
    public Game.Prefabs.PrefabBase m_NetStartSound;
    public Game.Prefabs.PrefabBase m_NetNodeSound;
    public Game.Prefabs.PrefabBase m_NetBuildSound;
    public Game.Prefabs.PrefabBase m_NetCancelSound;
    public Game.Prefabs.PrefabBase m_NetElevationUpSound;
    public Game.Prefabs.PrefabBase m_NetElevationDownSound;
    public Game.Prefabs.PrefabBase m_TransportLineCompleteSound;
    public Game.Prefabs.PrefabBase m_TransportLineStartSound;
    public Game.Prefabs.PrefabBase m_TransportLineBuildSound;
    public Game.Prefabs.PrefabBase m_TransportLineRemoveSound;
    public Game.Prefabs.PrefabBase m_AreaMarqueeStartSound;
    public Game.Prefabs.PrefabBase m_AreaMarqueeEndSound;
    public Game.Prefabs.PrefabBase m_AreaMarqueeClearStartSound;
    public Game.Prefabs.PrefabBase m_AreaMarqueeClearEndSound;
    public Game.Prefabs.PrefabBase m_TutorialStartedSound;
    public Game.Prefabs.PrefabBase m_TutorialCompletedSound;
    public Game.Prefabs.PrefabBase m_CameraZoomInSound;
    public Game.Prefabs.PrefabBase m_CameraZoomOutSound;
    public Game.Prefabs.PrefabBase m_DeletetEntitySound;

    public ToolUXSoundSettingsPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_PolygonToolSelectPointSound`  

```csharp
public Game.Prefabs.PrefabBase m_PolygonToolSelectPointSound;
```

- `public Game.Prefabs.PrefabBase m_PolygonToolDropPointSound`  

```csharp
public Game.Prefabs.PrefabBase m_PolygonToolDropPointSound;
```

- `public Game.Prefabs.PrefabBase m_PolygonToolRemovePointSound`  

```csharp
public Game.Prefabs.PrefabBase m_PolygonToolRemovePointSound;
```

- `public Game.Prefabs.PrefabBase m_PolygonToolDeleteAreaSound`  

```csharp
public Game.Prefabs.PrefabBase m_PolygonToolDeleteAreaSound;
```

- `public Game.Prefabs.PrefabBase m_PolygonToolFinishAreaSound`  

```csharp
public Game.Prefabs.PrefabBase m_PolygonToolFinishAreaSound;
```

- `public Game.Prefabs.PrefabBase m_BulldozeSound`  

```csharp
public Game.Prefabs.PrefabBase m_BulldozeSound;
```

- `public Game.Prefabs.PrefabBase m_PropPlantBulldozeSound`  

```csharp
public Game.Prefabs.PrefabBase m_PropPlantBulldozeSound;
```

- `public Game.Prefabs.PrefabBase m_TerraformSound`  

```csharp
public Game.Prefabs.PrefabBase m_TerraformSound;
```

- `public Game.Prefabs.PrefabBase m_PlaceBuildingSound`  

```csharp
public Game.Prefabs.PrefabBase m_PlaceBuildingSound;
```

- `public Game.Prefabs.PrefabBase m_RelocateBuildingSound`  

```csharp
public Game.Prefabs.PrefabBase m_RelocateBuildingSound;
```

- `public Game.Prefabs.PrefabBase m_PlaceUpgradeSound`  

```csharp
public Game.Prefabs.PrefabBase m_PlaceUpgradeSound;
```

- `public Game.Prefabs.PrefabBase m_PlacePropSound`  

```csharp
public Game.Prefabs.PrefabBase m_PlacePropSound;
```

- `public Game.Prefabs.PrefabBase m_PlaceBuildingFailSound`  

```csharp
public Game.Prefabs.PrefabBase m_PlaceBuildingFailSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningFillSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningFillSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningRemoveFillSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningRemoveFillSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningStartPaintSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningStartPaintSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningEndPaintSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningEndPaintSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningStartRemovePaintSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningStartRemovePaintSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningEndRemovePaintSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningEndRemovePaintSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningMarqueeStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningMarqueeStartSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningMarqueeEndSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningMarqueeEndSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningMarqueeClearStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningMarqueeClearStartSound;
```

- `public Game.Prefabs.PrefabBase m_ZoningMarqueeClearEndSound`  

```csharp
public Game.Prefabs.PrefabBase m_ZoningMarqueeClearEndSound;
```

- `public Game.Prefabs.PrefabBase m_SelectEntitySound`  

```csharp
public Game.Prefabs.PrefabBase m_SelectEntitySound;
```

- `public Game.Prefabs.PrefabBase m_SnapSound`  

```csharp
public Game.Prefabs.PrefabBase m_SnapSound;
```

- `public Game.Prefabs.PrefabBase m_NetExpandSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetExpandSound;
```

- `public Game.Prefabs.PrefabBase m_NetStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetStartSound;
```

- `public Game.Prefabs.PrefabBase m_NetNodeSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetNodeSound;
```

- `public Game.Prefabs.PrefabBase m_NetBuildSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetBuildSound;
```

- `public Game.Prefabs.PrefabBase m_NetCancelSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetCancelSound;
```

- `public Game.Prefabs.PrefabBase m_NetElevationUpSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetElevationUpSound;
```

- `public Game.Prefabs.PrefabBase m_NetElevationDownSound`  

```csharp
public Game.Prefabs.PrefabBase m_NetElevationDownSound;
```

- `public Game.Prefabs.PrefabBase m_TransportLineCompleteSound`  

```csharp
public Game.Prefabs.PrefabBase m_TransportLineCompleteSound;
```

- `public Game.Prefabs.PrefabBase m_TransportLineStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_TransportLineStartSound;
```

- `public Game.Prefabs.PrefabBase m_TransportLineBuildSound`  

```csharp
public Game.Prefabs.PrefabBase m_TransportLineBuildSound;
```

- `public Game.Prefabs.PrefabBase m_TransportLineRemoveSound`  

```csharp
public Game.Prefabs.PrefabBase m_TransportLineRemoveSound;
```

- `public Game.Prefabs.PrefabBase m_AreaMarqueeStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_AreaMarqueeStartSound;
```

- `public Game.Prefabs.PrefabBase m_AreaMarqueeEndSound`  

```csharp
public Game.Prefabs.PrefabBase m_AreaMarqueeEndSound;
```

- `public Game.Prefabs.PrefabBase m_AreaMarqueeClearStartSound`  

```csharp
public Game.Prefabs.PrefabBase m_AreaMarqueeClearStartSound;
```

- `public Game.Prefabs.PrefabBase m_AreaMarqueeClearEndSound`  

```csharp
public Game.Prefabs.PrefabBase m_AreaMarqueeClearEndSound;
```

- `public Game.Prefabs.PrefabBase m_TutorialStartedSound`  

```csharp
public Game.Prefabs.PrefabBase m_TutorialStartedSound;
```

- `public Game.Prefabs.PrefabBase m_TutorialCompletedSound`  

```csharp
public Game.Prefabs.PrefabBase m_TutorialCompletedSound;
```

- `public Game.Prefabs.PrefabBase m_CameraZoomInSound`  

```csharp
public Game.Prefabs.PrefabBase m_CameraZoomInSound;
```

- `public Game.Prefabs.PrefabBase m_CameraZoomOutSound`  

```csharp
public Game.Prefabs.PrefabBase m_CameraZoomOutSound;
```

- `public Game.Prefabs.PrefabBase m_DeletetEntitySound`  

```csharp
public Game.Prefabs.PrefabBase m_DeletetEntitySound;
```


## Constructors

- `public ToolUXSoundSettingsPrefab()`  

```csharp
public ToolUXSoundSettingsPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


