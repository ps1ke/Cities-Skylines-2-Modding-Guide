# Game.Simulation.DiversitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DiversitySystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_AtmosphereQuery;
    private Unity.Entities.EntityQuery m_AtmospherePrefabQuery;
    private Unity.Entities.EntityQuery m_BiomeQuery;
    private Unity.Entities.EntityQuery m_BiomePrefabQuery;
    private Unity.Entities.EntityQuery m_EditorContainerQuery;

    public DiversitySystem();

    public System.Void ApplyAtmospherePreset(Unity.Entities.Entity atmospherePrefab);
    public System.Void ApplyBiomePreset(Unity.Entities.Entity biomePrefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmosphereQuery;
```

- `private Unity.Entities.EntityQuery m_AtmospherePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmospherePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_BiomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomeQuery;
```

- `private Unity.Entities.EntityQuery m_BiomePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorContainerQuery;
```


## Constructors

- `public DiversitySystem()`  

```csharp
public DiversitySystem();
```


## Methods

- `public ApplyAtmospherePreset(Unity.Entities.Entity atmospherePrefab) : System.Void`  

```csharp
public System.Void ApplyAtmospherePreset(Unity.Entities.Entity atmospherePrefab);
```

- `public ApplyBiomePreset(Unity.Entities.Entity biomePrefab) : System.Void`  

```csharp
public System.Void ApplyBiomePreset(Unity.Entities.Entity biomePrefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


