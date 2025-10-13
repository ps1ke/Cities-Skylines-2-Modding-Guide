# Game.Debug.AssetDatabaseDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class AssetDatabaseDebugUI : System.IDisposable
{
    public AssetDatabaseDebugUI();

    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildAssetDatabaseDebugUI();
    public System.Void Dispose();
    private System.Void Rebuild(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
}
```


## Constructors

- `public AssetDatabaseDebugUI()`  

```csharp
public AssetDatabaseDebugUI()
	{
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe(Rebuild, delegate(AssetChangedEventArgs args)
		{
			ChangeType change = args.change;
			return change == ChangeType.DatabaseRegistered || change == ChangeType.DatabaseUnregistered;
		});
	}
```


## Methods

- `private BuildAssetDatabaseDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildAssetDatabaseDebugUI()
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "Asset Database Changed Handlers"
		};
		ICollection<(EventDelegate<AssetChangedEventArgs> handler, Predicate<AssetChangedEventArgs> filter)> globalChangedHandlers = AssetDatabase.global.onAssetDatabaseChanged.Handlers;
		foldout.children.Add(new DebugUI.Value
		{
			displayName = "Active Count",
			getter = () => globalChangedHandlers.Count
		});
		foreach (var item2 in globalChangedHandlers)
		{
			foldout.children.Add(new DebugUI.Container
			{
				displayName = item2.handler.Method.DeclaringType.Name + "." + item2.handler.Method.Name
			});
		}
		DebugUI.Container container = new DebugUI.Container
		{
			children = { (DebugUI.Widget)new DebugUI.Foldout
			{
				displayName = "Global database",
				children = 
				{
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Global mipbias",
						getter = () => AssetDatabase.global.mipBias
					},
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Asset count",
						getter = () => AssetDatabase.global.count
					},
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Hostname",
						getter = () => AssetDatabase.global.hostname
					},
					(DebugUI.Widget)foldout
				}
			} }
		};
		foreach (IAssetDatabase database in AssetDatabase.global.databases)
		{
			DebugUI.Foldout item = new DebugUI.Foldout
			{
				displayName = database.name,
				children = 
				{
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Asset count",
						getter = () => database.count
					},
					(DebugUI.Widget)new DebugUI.Value
					{
						displayName = "Hostname",
						getter = () => database.hostname
					}
				}
			};
			DebugUI.Foldout foldout2 = new DebugUI.Foldout
			{
				displayName = "Asset Database Changed Handlers"
			};
			ICollection<(EventDelegate<AssetChangedEventArgs> handler, Predicate<AssetChangedEventArgs> filter)> changedHandlers = database.onAssetDatabaseChanged.Handlers;
			foldout2.children.Add(new DebugUI.Value
			{
				displayName = "Active Count",
				getter = () => changedHandlers.Count
			});
			foreach (var item3 in changedHandlers)
			{
				foldout2.children.Add(new DebugUI.Container
				{
					displayName = item3.handler.Method.DeclaringType.Name + "." + item3.handler.Method.Name
				});
			}
			container.children.Add(item);
		}
		return new List<DebugUI.Widget>
		{
			container,
			new DebugUI.Button
			{
				displayName = "Apply settings",
				action = delegate
				{
					GameManager.instance.settings.Apply();
				}
			},
			new DebugUI.Button
			{
				displayName = "Reset settings",
				action = delegate
				{
					GameManager.instance.settings.Reset();
				}
			},
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = delegate
				{
					Rebuild();
				}
			}
		};
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		AssetDatabase.global.onAssetDatabaseChanged.Unsubscribe(Rebuild);
	}
```

- `private Rebuild(Colossal.IO.AssetDatabase.AssetChangedEventArgs args = null) : System.Void`  

```csharp
private System.Void Rebuild(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```


## Nested types

- `Game.Debug.AssetDatabaseDebugUI+<>c`  
- `Game.Debug.AssetDatabaseDebugUI+<>c__DisplayClass3_0`  
- `Game.Debug.AssetDatabaseDebugUI+<>c__DisplayClass3_1`  
- `Game.Debug.AssetDatabaseDebugUI+<>c__DisplayClass3_2`  

