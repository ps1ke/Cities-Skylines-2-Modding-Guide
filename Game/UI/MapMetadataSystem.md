# Game.UI.MapMetadataSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapMetadataSystem : Game.GameSystemBase
{
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Single m_Area;
    private System.Single m_BuildableLand;
    private System.Single m_SurfaceWaterAvailability;
    private System.Single m_GroundWaterAvailability;
    private Game.UI.MapMetadataSystem+Resources m_Resources;
    private Game.UI.MapMetadataSystem+Connections m_Connections;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private System.String <mapName>k__BackingField;
    private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle;

    public System.String mapName { get; set; }
    public System.String theme { get; }
    public Colossal.Mathematics.Bounds1 temperatureRange { get; }
    public System.Single cloudiness { get; }
    public System.Single precipitation { get; }
    public System.Single latitude { get; }
    public System.Single longitude { get; }
    public System.Single area { get; }
    public System.Single buildableLand { get; }
    public System.Single surfaceWaterAvailability { get; }
    public System.Single groundWaterAvailability { get; }
    public Game.UI.MapMetadataSystem+Resources resources { get; }
    public Game.UI.MapMetadataSystem+Connections connections { get; }

    public MapMetadataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateConnections();
    private System.Void UpdateResources();
}
```


## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Single m_Area`  

```csharp
private System.Single m_Area;
```

- `private System.Single m_BuildableLand`  

```csharp
private System.Single m_BuildableLand;
```

- `private System.Single m_SurfaceWaterAvailability`  

```csharp
private System.Single m_SurfaceWaterAvailability;
```

- `private System.Single m_GroundWaterAvailability`  

```csharp
private System.Single m_GroundWaterAvailability;
```

- `private Game.UI.MapMetadataSystem+Resources m_Resources`  

```csharp
private Game.UI.MapMetadataSystem+Resources m_Resources;
```

- `private Game.UI.MapMetadataSystem+Connections m_Connections`  

```csharp
private Game.UI.MapMetadataSystem+Connections m_Connections;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private System.String <mapName>k__BackingField`  

```csharp
private System.String <mapName>k__BackingField;
```

- `private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.String mapName { get; set }`  

```csharp
public System.String mapName { get; set; }
```

- `public System.String theme { get }`  

```csharp
public System.String theme { get; }
```

- `public Colossal.Mathematics.Bounds1 temperatureRange { get }`  

```csharp
public Colossal.Mathematics.Bounds1 temperatureRange { get; }
```

- `public System.Single cloudiness { get }`  

```csharp
public System.Single cloudiness { get; }
```

- `public System.Single precipitation { get }`  

```csharp
public System.Single precipitation { get; }
```

- `public System.Single latitude { get }`  

```csharp
public System.Single latitude { get; }
```

- `public System.Single longitude { get }`  

```csharp
public System.Single longitude { get; }
```

- `public System.Single area { get }`  

```csharp
public System.Single area { get; }
```

- `public System.Single buildableLand { get }`  

```csharp
public System.Single buildableLand { get; }
```

- `public System.Single surfaceWaterAvailability { get }`  

```csharp
public System.Single surfaceWaterAvailability { get; }
```

- `public System.Single groundWaterAvailability { get }`  

```csharp
public System.Single groundWaterAvailability { get; }
```

- `public Game.UI.MapMetadataSystem+Resources resources { get }`  

```csharp
public Game.UI.MapMetadataSystem+Resources resources { get; }
```

- `public Game.UI.MapMetadataSystem+Connections connections { get }`  

```csharp
public Game.UI.MapMetadataSystem+Connections connections { get; }
```


## Constructors

- `public MapMetadataSystem()`  

```csharp
public MapMetadataSystem();
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

- `private UpdateConnections() : System.Void`  

```csharp
private System.Void UpdateConnections();
```

- `private UpdateResources() : System.Void`  

```csharp
private System.Void UpdateResources();
```


## Nested types

- `Game.UI.MapMetadataSystem+Resources`  
- `Game.UI.MapMetadataSystem+Connections`  
- `Game.UI.MapMetadataSystem+TypeHandle`  

