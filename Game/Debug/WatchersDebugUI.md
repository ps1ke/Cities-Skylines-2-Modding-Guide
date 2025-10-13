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
private List<DebugUI.Widget> BuildWatchersDebugUI(World world)
	{
		m_WatchSystem = world.GetOrCreateSystemManaged<DebugWatchSystem>();
		m_WatchSystem.Enabled = true;
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		list.Add(new DebugUI.Button
		{
			displayName = "Refresh System List",
			action = Rebuild
		});
		list.Add(new DebugUI.Button
		{
			displayName = "Clear Watches",
			action = m_WatchSystem.ClearWatches
		});
		list.AddRange(m_WatchSystem.BuildSystemFoldouts());
		return list;
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_WatchSystem.Enabled = m_WatchSystem.watches.Count > 0;
	}
```

- `private Rebuild() : System.Void`  

```csharp
private void Rebuild()
	{
		DebugSystem.Rebuild(BuildWatchersDebugUI);
	}
```


