# Game.Debug.WatchersDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class WatchersDebugUI : System.IDisposable
{
    private Game.Debug.DebugWatchSystem m_WatchSystem;

    public WatchersDebugUI();

    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildWatchersDebugUI(Unity.Entities.World world);
    public System.Void Dispose();
    private System.Void Rebuild();
}
```


## Fields

- `private Game.Debug.DebugWatchSystem m_WatchSystem`  

```csharp
private Game.Debug.DebugWatchSystem m_WatchSystem;
```


## Constructors

- `public WatchersDebugUI()`  

```csharp
public WatchersDebugUI();
```


## Methods

- `private BuildWatchersDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildWatchersDebugUI(Unity.Entities.World world);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private Rebuild() : System.Void`  

```csharp
private System.Void Rebuild();
```


