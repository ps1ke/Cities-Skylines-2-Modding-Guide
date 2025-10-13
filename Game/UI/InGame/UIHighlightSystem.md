# Game.UI.InGame.UIHighlightSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UIHighlightSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
    private System.Boolean m_SkipUpdate;
    private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle;

    public UIHighlightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void SkipUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
```

- `private System.Boolean m_SkipUpdate`  

```csharp
private System.Boolean m_SkipUpdate;
```

- `private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UIHighlightSystem()`  

```csharp
public UIHighlightSystem();
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public SkipUpdate() : System.Void`  

```csharp
public System.Void SkipUpdate();
```


## Nested types

- `Game.UI.InGame.UIHighlightSystem+HighlightJob`  
- `Game.UI.InGame.UIHighlightSystem+TypeHandle`  

