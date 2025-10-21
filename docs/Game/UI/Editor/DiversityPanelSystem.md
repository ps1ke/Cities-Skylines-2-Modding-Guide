# Game.UI.Editor.DiversityPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DiversityPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.DiversitySystem m_DiversitySystem;
    private Unity.Entities.EntityQuery m_AtmosphereQuery;
    private Unity.Entities.EntityQuery m_BiomeQuery;
    private Game.Prefabs.AtmospherePrefab m_Atmosphere;
    private Game.Prefabs.BiomePrefab m_Biome;

    public DiversityPanelSystem();

    private Game.Prefabs.PrefabBase <OnCreate>b__6_0();
    private Game.Prefabs.PrefabBase <OnCreate>b__6_1();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStartRunning();
    private System.Void SetAtmosphere(Game.Prefabs.PrefabBase prefab);
    private System.Void SetBiome(Game.Prefabs.PrefabBase prefab);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.DiversitySystem m_DiversitySystem`  

```csharp
private Game.Simulation.DiversitySystem m_DiversitySystem;
```

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmosphereQuery;
```

- `private Unity.Entities.EntityQuery m_BiomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomeQuery;
```

- `private Game.Prefabs.AtmospherePrefab m_Atmosphere`  

```csharp
private Game.Prefabs.AtmospherePrefab m_Atmosphere;
```

- `private Game.Prefabs.BiomePrefab m_Biome`  

```csharp
private Game.Prefabs.BiomePrefab m_Biome;
```


## Constructors

- `public DiversityPanelSystem()`  

```csharp
public DiversityPanelSystem();
```


## Methods

- `private <OnCreate>b__6_0() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnCreate>b__6_0();
```

- `private <OnCreate>b__6_1() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnCreate>b__6_1();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `private SetAtmosphere(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void SetAtmosphere(Game.Prefabs.PrefabBase prefab);
```

- `private SetBiome(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void SetBiome(Game.Prefabs.PrefabBase prefab);
```


