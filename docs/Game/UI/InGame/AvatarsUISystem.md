# Game.UI.InGame.AvatarsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvatarsUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_ColorsQuery;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding;
    private static const System.String kGroup;
    private static const System.Int32 kIconSize;

    public AvatarsUISystem();

    private System.Void BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private UnityEngine.Color32 GetColor(Unity.Entities.Entity entity);
    private System.String GetPicture(Unity.Entities.Entity entity);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_ColorsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ColorsQuery;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Int32 kIconSize`  

```csharp
private static const System.Int32 kIconSize;
```


## Constructors

- `public AvatarsUISystem()`  

```csharp
public AvatarsUISystem();
```


## Methods

- `private BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `private GetColor(Unity.Entities.Entity entity) : UnityEngine.Color32`  

```csharp
private UnityEngine.Color32 GetColor(Unity.Entities.Entity entity);
```

- `private GetPicture(Unity.Entities.Entity entity) : System.String`  

```csharp
private System.String GetPicture(Unity.Entities.Entity entity);
```

- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  

```csharp
private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


