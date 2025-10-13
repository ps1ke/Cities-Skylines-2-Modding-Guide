# Game.UI.UIUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class UIUpdateSystem : Game.GameSystemBase
{
    private Game.UpdateSystem m_UpdateSystem;

    public UIUpdateSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```


## Constructors

- `public UIUpdateSystem()`  

```csharp
public UIUpdateSystem();
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


