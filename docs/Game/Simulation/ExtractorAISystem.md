# Game.Simulation.ExtractorAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ExtractorAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Mathematics.Random m_RandomSeed;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMinimumEmployee;

    public ExtractorAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
    private static System.Single GetArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
    public static System.Single GetResourcesInArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
    private static System.Single GetResourcesInArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Mathematics.Random m_RandomSeed`  

```csharp
private Unity.Mathematics.Random m_RandomSeed;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMinimumEmployee`  

```csharp
public static readonly System.Int32 kMinimumEmployee;
```


## Constructors

- `public ExtractorAISystem()`  

```csharp
public ExtractorAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries) : System.Single`  

```csharp
public static System.Single GetArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
```

- `private static GetArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries) : System.Single`  

```csharp
private static System.Single GetArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
```

- `public static GetResourcesInArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors) : System.Single`  

```csharp
public static System.Single GetResourcesInArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
```

- `private static GetResourcesInArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors) : System.Single`  

```csharp
private static System.Single GetResourcesInArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.ExtractorAISystem+ExtractorAITickJob`  
- `Game.Simulation.ExtractorAISystem+TypeHandle`  

