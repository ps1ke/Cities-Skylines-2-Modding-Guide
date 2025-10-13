# Game.Rendering.WindTextureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class WindTextureSystem : Game.GameSystemBase
{
    private Game.Simulation.WindSystem m_WindSystem;
    private UnityEngine.Texture2D m_WindTexture;
    private Unity.Jobs.JobHandle m_UpdateHandle;
    private System.Boolean m_RequireUpdate;
    private System.Boolean m_RequireApply;

    public UnityEngine.Texture2D WindTexture { get; }

    public WindTextureSystem();

    public System.Void CompleteUpdate();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void RequireUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private UnityEngine.Texture2D m_WindTexture`  

```csharp
private UnityEngine.Texture2D m_WindTexture;
```

- `private Unity.Jobs.JobHandle m_UpdateHandle`  

```csharp
private Unity.Jobs.JobHandle m_UpdateHandle;
```

- `private System.Boolean m_RequireUpdate`  

```csharp
private System.Boolean m_RequireUpdate;
```

- `private System.Boolean m_RequireApply`  

```csharp
private System.Boolean m_RequireApply;
```


## Properties

- `public UnityEngine.Texture2D WindTexture { get }`  

```csharp
public UnityEngine.Texture2D WindTexture { get; }
```


## Constructors

- `public WindTextureSystem()`  

```csharp
public WindTextureSystem();
```


## Methods

- `public CompleteUpdate() : System.Void`  

```csharp
public System.Void CompleteUpdate();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RequireUpdate() : System.Void`  

```csharp
public System.Void RequireUpdate();
```


## Nested types

- `Game.Rendering.WindTextureSystem+WindTextureJob`  

