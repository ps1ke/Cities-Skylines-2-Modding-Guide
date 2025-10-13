# Game.City.CityConfigurationSystem

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityConfigurationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private System.String <cityName>k__BackingField;
    private System.String <overrideCityName>k__BackingField;
    private System.String m_LoadedCityName;
    private System.String <overrideThemeName>k__BackingField;
    private Unity.Entities.Entity <defaultTheme>k__BackingField;
    private Unity.Entities.Entity <loadedDefaultTheme>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_RequiredContent;
    private System.Boolean <leftHandTraffic>k__BackingField;
    private System.Boolean <overrideLeftHandTraffic>k__BackingField;
    private System.Boolean m_LoadedLeftHandTraffic;
    private System.Boolean <naturalDisasters>k__BackingField;
    private System.Boolean <overrideNaturalDisasters>k__BackingField;
    private System.Boolean m_LoadedNaturalDisasters;
    private System.Boolean <overrideUnlockAll>k__BackingField;
    private System.Boolean m_UnlockAll;
    private System.Boolean m_LoadedUnlockAll;
    private System.Boolean <overrideUnlimitedMoney>k__BackingField;
    private System.Boolean m_UnlimitedMoney;
    private System.Boolean m_LoadedUnlimitedMoney;
    private System.Boolean <overrideUnlockMapTiles>k__BackingField;
    private System.Boolean m_UnlockMapTiles;
    private System.Boolean m_LoadedUnlockMapTiles;
    private System.Boolean <overrideLoadedOptions>k__BackingField;
    private System.Collections.Generic.HashSet<System.String> <usedMods>k__BackingField;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem;
    private Game.Net.FlipTrafficHandednessSystem m_FlipTrafficHandednessSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_SubLaneQuery;
    public Unity.Mathematics.float3 m_CameraPivot;
    public Unity.Mathematics.float2 m_CameraAngle;
    public System.Single m_CameraZoom;
    public Unity.Entities.Entity m_CameraFollow;
    private static readonly Unity.Mathematics.float3 kDefaultCameraPivot;
    private static readonly Unity.Mathematics.float2 kDefaultCameraAngle;
    private static readonly System.Single kDefaultCameraZoom;
    private static readonly Unity.Entities.Entity kDefaultCameraFollow;

    public System.String cityName { get; set; }
    public System.String overrideCityName { get; set; }
    public System.String overrideThemeName { get; set; }
    public Unity.Entities.Entity defaultTheme { get; set; }
    public Unity.Entities.Entity loadedDefaultTheme { get; set; }
    public Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& requiredContent { get; }
    public System.Boolean leftHandTraffic { get; set; }
    public System.Boolean overrideLeftHandTraffic { get; set; }
    public System.Boolean naturalDisasters { get; set; }
    public System.Boolean overrideNaturalDisasters { get; set; }
    public System.Boolean unlockAll { get; set; }
    public System.Boolean overrideUnlockAll { get; set; }
    public System.Boolean unlimitedMoney { get; set; }
    public System.Boolean overrideUnlimitedMoney { get; set; }
    public System.Boolean unlockMapTiles { get; set; }
    public System.Boolean overrideUnlockMapTiles { get; set; }
    public System.Boolean overrideLoadedOptions { get; set; }
    public System.Collections.Generic.HashSet<System.String> usedMods { get; private set; }

    public CityConfigurationSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ResetCameraProperties();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private System.String <cityName>k__BackingField`  

```csharp
private System.String <cityName>k__BackingField;
```

- `private System.String <overrideCityName>k__BackingField`  

```csharp
private System.String <overrideCityName>k__BackingField;
```

- `private System.String m_LoadedCityName`  

```csharp
private System.String m_LoadedCityName;
```

- `private System.String <overrideThemeName>k__BackingField`  

```csharp
private System.String <overrideThemeName>k__BackingField;
```

- `private Unity.Entities.Entity <defaultTheme>k__BackingField`  

```csharp
private Unity.Entities.Entity <defaultTheme>k__BackingField;
```

- `private Unity.Entities.Entity <loadedDefaultTheme>k__BackingField`  

```csharp
private Unity.Entities.Entity <loadedDefaultTheme>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_RequiredContent`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_RequiredContent;
```

- `private System.Boolean <leftHandTraffic>k__BackingField`  

```csharp
private System.Boolean <leftHandTraffic>k__BackingField;
```

- `private System.Boolean <overrideLeftHandTraffic>k__BackingField`  

```csharp
private System.Boolean <overrideLeftHandTraffic>k__BackingField;
```

- `private System.Boolean m_LoadedLeftHandTraffic`  

```csharp
private System.Boolean m_LoadedLeftHandTraffic;
```

- `private System.Boolean <naturalDisasters>k__BackingField`  

```csharp
private System.Boolean <naturalDisasters>k__BackingField;
```

- `private System.Boolean <overrideNaturalDisasters>k__BackingField`  

```csharp
private System.Boolean <overrideNaturalDisasters>k__BackingField;
```

- `private System.Boolean m_LoadedNaturalDisasters`  

```csharp
private System.Boolean m_LoadedNaturalDisasters;
```

- `private System.Boolean <overrideUnlockAll>k__BackingField`  

```csharp
private System.Boolean <overrideUnlockAll>k__BackingField;
```

- `private System.Boolean m_UnlockAll`  

```csharp
private System.Boolean m_UnlockAll;
```

- `private System.Boolean m_LoadedUnlockAll`  

```csharp
private System.Boolean m_LoadedUnlockAll;
```

- `private System.Boolean <overrideUnlimitedMoney>k__BackingField`  

```csharp
private System.Boolean <overrideUnlimitedMoney>k__BackingField;
```

- `private System.Boolean m_UnlimitedMoney`  

```csharp
private System.Boolean m_UnlimitedMoney;
```

- `private System.Boolean m_LoadedUnlimitedMoney`  

```csharp
private System.Boolean m_LoadedUnlimitedMoney;
```

- `private System.Boolean <overrideUnlockMapTiles>k__BackingField`  

```csharp
private System.Boolean <overrideUnlockMapTiles>k__BackingField;
```

- `private System.Boolean m_UnlockMapTiles`  

```csharp
private System.Boolean m_UnlockMapTiles;
```

- `private System.Boolean m_LoadedUnlockMapTiles`  

```csharp
private System.Boolean m_LoadedUnlockMapTiles;
```

- `private System.Boolean <overrideLoadedOptions>k__BackingField`  

```csharp
private System.Boolean <overrideLoadedOptions>k__BackingField;
```

- `private System.Collections.Generic.HashSet<System.String> <usedMods>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<System.String> <usedMods>k__BackingField;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem`  

```csharp
private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem;
```

- `private Game.Net.FlipTrafficHandednessSystem m_FlipTrafficHandednessSystem`  

```csharp
private Game.Net.FlipTrafficHandednessSystem m_FlipTrafficHandednessSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_SubLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubLaneQuery;
```

- `public Unity.Mathematics.float3 m_CameraPivot`  

```csharp
public Unity.Mathematics.float3 m_CameraPivot;
```

- `public Unity.Mathematics.float2 m_CameraAngle`  

```csharp
public Unity.Mathematics.float2 m_CameraAngle;
```

- `public System.Single m_CameraZoom`  

```csharp
public System.Single m_CameraZoom;
```

- `public Unity.Entities.Entity m_CameraFollow`  

```csharp
public Unity.Entities.Entity m_CameraFollow;
```

- `private static readonly Unity.Mathematics.float3 kDefaultCameraPivot`  

```csharp
private static readonly Unity.Mathematics.float3 kDefaultCameraPivot;
```

- `private static readonly Unity.Mathematics.float2 kDefaultCameraAngle`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultCameraAngle;
```

- `private static readonly System.Single kDefaultCameraZoom`  

```csharp
private static readonly System.Single kDefaultCameraZoom;
```

- `private static readonly Unity.Entities.Entity kDefaultCameraFollow`  

```csharp
private static readonly Unity.Entities.Entity kDefaultCameraFollow;
```


## Properties

- `public System.String cityName { get; set }`  

```csharp
public System.String cityName { get; set; }
```

- `public System.String overrideCityName { get; set }`  

```csharp
public System.String overrideCityName { get; set; }
```

- `public System.String overrideThemeName { get; set }`  

```csharp
public System.String overrideThemeName { get; set; }
```

- `public Unity.Entities.Entity defaultTheme { get; set }`  

```csharp
public Unity.Entities.Entity defaultTheme { get; set; }
```

- `public Unity.Entities.Entity loadedDefaultTheme { get; set }`  

```csharp
public Unity.Entities.Entity loadedDefaultTheme { get; set; }
```

- `public Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& requiredContent { get }`  

```csharp
public Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& requiredContent { get; }
```

- `public System.Boolean leftHandTraffic { get; set }`  

```csharp
public System.Boolean leftHandTraffic { get; set; }
```

- `public System.Boolean overrideLeftHandTraffic { get; set }`  

```csharp
public System.Boolean overrideLeftHandTraffic { get; set; }
```

- `public System.Boolean naturalDisasters { get; set }`  

```csharp
public System.Boolean naturalDisasters { get; set; }
```

- `public System.Boolean overrideNaturalDisasters { get; set }`  

```csharp
public System.Boolean overrideNaturalDisasters { get; set; }
```

- `public System.Boolean unlockAll { get; set }`  

```csharp
public System.Boolean unlockAll { get; set; }
```

- `public System.Boolean overrideUnlockAll { get; set }`  

```csharp
public System.Boolean overrideUnlockAll { get; set; }
```

- `public System.Boolean unlimitedMoney { get; set }`  

```csharp
public System.Boolean unlimitedMoney { get; set; }
```

- `public System.Boolean overrideUnlimitedMoney { get; set }`  

```csharp
public System.Boolean overrideUnlimitedMoney { get; set; }
```

- `public System.Boolean unlockMapTiles { get; set }`  

```csharp
public System.Boolean unlockMapTiles { get; set; }
```

- `public System.Boolean overrideUnlockMapTiles { get; set }`  

```csharp
public System.Boolean overrideUnlockMapTiles { get; set; }
```

- `public System.Boolean overrideLoadedOptions { get; set }`  

```csharp
public System.Boolean overrideLoadedOptions { get; set; }
```

- `public System.Collections.Generic.HashSet<System.String> usedMods { get; private set }`  

```csharp
public System.Collections.Generic.HashSet<System.String> usedMods { get; private set; }
```


## Constructors

- `public CityConfigurationSystem()`  

```csharp
public CityConfigurationSystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  

```csharp
public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private ResetCameraProperties() : System.Void`  

```csharp
private System.Void ResetCameraProperties();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


