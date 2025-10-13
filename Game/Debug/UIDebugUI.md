# Game.Debug.UIDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class UIDebugUI
{
    public UIDebugUI();

    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildUIBindingsDebugUI();
}
```


## Constructors

- `public UIDebugUI()`  

```csharp
public UIDebugUI();
```


## Methods

- `private static BuildUIBindingsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildUIBindingsDebugUI()
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout
		{
			displayName = "UI Manager"
		};
		foreach (Colossal.UI.UISystem uiSystem in UIManager.UISystems)
		{
			DebugUI.Foldout foldout2 = new DebugUI.Foldout
			{
				displayName = "UISystem #" + uiSystem.id
			};
			foldout.children.Add(new DebugUI.Value
			{
				displayName = "Static User Images",
				getter = () => uiSystem.userImagesManager.staticUserImageCount
			});
			foldout.children.Add(new DebugUI.Value
			{
				displayName = "Dynamic User Images",
				getter = () => uiSystem.userImagesManager.dynamicUserImageCount
			});
			foldout.children.Add(foldout2);
			foldout.children.Add(new DebugUI.Button
			{
				displayName = "Clear cached unused images",
				action = delegate
				{
					uiSystem.ClearCachedUnusedImages();
				}
			});
			foreach (UIView uiView in uiSystem.UIViews)
			{
				DebugUI.Container container = new DebugUI.Container();
				container.children.Add(new DebugUI.Value
				{
					displayName = "UIView #" + uiView.id,
					getter = () => string.Format("{0} #{1}", uiView.enabled ? "[x]" : "[ ]", uiView.id)
				});
				container.children.Add(new DebugUI.Value
				{
					displayName = "URL",
					getter = () => uiView.url
				});
				foldout2.children.Add(container);
			}
			DefaultResourceHandler defaultResourceHandler = uiSystem.resourceHandler as DefaultResourceHandler;
			if (defaultResourceHandler != null && defaultResourceHandler.HostLocationsMap.Count > 0)
			{
				DebugUI.Foldout foldout3 = new DebugUI.Foldout
				{
					displayName = "coui Hosts"
				};
				foreach (KeyValuePair<string, List<(string, int)>> item2 in defaultResourceHandler.HostLocationsMap)
				{
					DebugUI.Foldout foldout4 = new DebugUI.Foldout
					{
						displayName = item2.Key
					};
					foreach (var path in item2.Value)
					{
						ObservableList<DebugUI.Widget> children = foldout4.children;
						DebugUI.Value value = new DebugUI.Value();
						int item = path.Item2;
						value.displayName = item.ToString();
						value.getter = () => path.Item1;
						children.Add(value);
					}
					foldout3.children.Add(foldout4);
				}
				foldout2.children.Add(foldout3);
			}
			if (defaultResourceHandler == null || defaultResourceHandler.DatabaseHostLocationsMap.Count <= 0)
			{
				continue;
			}
			DebugUI.Foldout foldout5 = new DebugUI.Foldout
			{
				displayName = "assetdb Hosts"
			};
			foreach (KeyValuePair<string, List<(Uri, int)>> item3 in defaultResourceHandler.DatabaseHostLocationsMap)
			{
				DebugUI.Foldout foldout6 = new DebugUI.Foldout
				{
					displayName = item3.Key
				};
				foreach (var path2 in item3.Value)
				{
					ObservableList<DebugUI.Widget> children2 = foldout6.children;
					DebugUI.Value value2 = new DebugUI.Value();
					int item = path2.Item2;
					value2.displayName = item.ToString();
					value2.getter = () => path2.Item1;
					children2.Add(value2);
				}
				foldout5.children.Add(foldout6);
			}
			foldout2.children.Add(foldout5);
		}
		List<DebugUI.Widget> list = new List<DebugUI.Widget>
		{
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = delegate
				{
					DebugSystem.Rebuild(BuildUIBindingsDebugUI);
				}
			},
			foldout
		};
		if (UIManager.instance.enableMemoryTracking)
		{
			DebugUI.Foldout foldout7 = new DebugUI.Foldout
			{
				displayName = "UI Memory"
			};
			foldout7.children.Add(new DebugUI.Value
			{
				displayName = "Allocated memory",
				getter = () => FormatUtils.FormatBytes(UnityPlugin.Instance.GetAllocatedMemory())
			});
			foldout7.children.Add(new DebugUI.Value
			{
				displayName = "Time spent in allocations (ns)",
				getter = () => UnityPlugin.Instance.GetTimeSpentInAllocationsNs()
			});
			foldout7.children.Add(new DebugUI.Value
			{
				displayName = "Allocation count",
				getter = () => UnityPlugin.Instance.GetAllocationCount()
			});
			foldout7.children.Add(new DebugUI.Value
			{
				displayName = "Total allocations",
				getter = () => UnityPlugin.Instance.GetTotalAllocations()
			});
			DebugUI.Foldout foldout8 = new DebugUI.Foldout
			{
				displayName = "Mem tags"
			};
			MemTagsType[] array = (MemTagsType[])Enum.GetValues(typeof(MemTagsType));
			for (int num = 0; num < array.Length - 1; num++)
			{
				MemTagsType tag = array[num];
				DebugUI.Foldout foldout9 = new DebugUI.Foldout
				{
					displayName = tag.ToString(),
					opened = true
				};
				foldout9.children.Add(new DebugUI.Value
				{
					displayName = "Allocated",
					getter = () => FormatUtils.FormatBytes(UnityPlugin.Instance.GetCurrentBytesByType(tag))
				});
				foldout9.children.Add(new DebugUI.Value
				{
					displayName = "Count",
					getter = () => UnityPlugin.Instance.GetCurrentCountsByType(tag)
				});
				foldout9.children.Add(new DebugUI.Value
				{
					displayName = "Totals",
					getter = () => UnityPlugin.Instance.GetTotalsByType(tag)
				});
				foldout8.children.Add(foldout9);
			}
			foldout7.children.Add(foldout8);
			list.Insert(2, foldout7);
		}
		return list;
	}
```


## Nested types

- `Game.Debug.UIDebugUI+<>c`  
- `Game.Debug.UIDebugUI+<>c__DisplayClass0_0`  
- `Game.Debug.UIDebugUI+<>c__DisplayClass0_1`  
- `Game.Debug.UIDebugUI+<>c__DisplayClass0_2`  
- `Game.Debug.UIDebugUI+<>c__DisplayClass0_3`  
- `Game.Debug.UIDebugUI+<>c__DisplayClass0_4`  

