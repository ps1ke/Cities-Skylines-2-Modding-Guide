# Game.UI.InGame.CameraUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class CameraUISystem : Game.UI.UISystemBase
{
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding;
    private static const System.String kGroup;

    public CameraUISystem();

    private System.Void FocusEntity(Unity.Entities.Entity entity);
    private Unity.Entities.Entity GetFocusedEntity();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public CameraUISystem()`  

```csharp
public CameraUISystem();
```


## Methods

- `private FocusEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void FocusEntity(Unity.Entities.Entity entity);
```

- `private GetFocusedEntity() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFocusedEntity();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


