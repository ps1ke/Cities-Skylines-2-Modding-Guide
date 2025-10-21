# Game.Debug.LightDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class LightDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_SpotOption;
    private Game.Debug.BaseDebugSystem+Option m_PositionOption;

    public LightDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LightEffectPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_SpotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SpotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PositionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PositionOption;
```


## Constructors

- `public LightDebugSystem()`  

```csharp
public LightDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.LightDebugSystem+LightGizmoJob`  

