# Game.UI.InGame.FeatureUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class FeatureUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Unity.Entities.EntityQuery m_UnlockedFeatureQuery;
    private Unity.Entities.EntityQuery m_UnlocksQuery;
    private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding;
    private static const System.String kGroup;

    public FeatureUISystem();

    private System.Void BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Unity.Entities.EntityQuery m_UnlockedFeatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedFeatureQuery;
```

- `private Unity.Entities.EntityQuery m_UnlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlocksQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public FeatureUISystem()`  

```csharp
public FeatureUISystem();
```


## Methods

- `private BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


