# Game.UI.Editor.MapRequirementSystem+CheckWaterJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CheckWaterJob : Unity.Jobs.IJob
{
    public Game.Simulation.WaterSurfaceData m_SurfaceData;
    public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles;
    public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_GeometryData;
    public Colossal.Collections.NativeValue<System.Boolean> m_Result;

    public System.Void Execute();
    private System.Boolean HasWater(Colossal.Mathematics.Bounds3 bounds);
}
```


## Fields

- `public Game.Simulation.WaterSurfaceData m_SurfaceData`  

```csharp
public Game.Simulation.WaterSurfaceData m_SurfaceData;
```

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_GeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_GeometryData;
```

- `public Colossal.Collections.NativeValue<System.Boolean> m_Result`  

```csharp
public Colossal.Collections.NativeValue<System.Boolean> m_Result;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private HasWater(Colossal.Mathematics.Bounds3 bounds) : System.Boolean`  

```csharp
private System.Boolean HasWater(Colossal.Mathematics.Bounds3 bounds);
```


