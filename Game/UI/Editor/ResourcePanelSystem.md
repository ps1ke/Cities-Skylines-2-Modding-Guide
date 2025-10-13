# Game.UI.Editor.ResourcePanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class ResourcePanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
    private Game.UI.Editor.EditorSection m_TextureImportButtons;
    private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
    private static readonly System.String kTextureImportFolder;

    public ResourcePanelSystem();

    private Game.Simulation.NaturalResourceCell ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private System.Void ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _);
    private Game.Simulation.NaturalResourceCell ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private Game.Simulation.NaturalResourceCell ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount);
    private System.Void ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback);
    private System.Void ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target);
    private System.Void ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback);
    private System.Void Clear(Game.Prefabs.TerraformingTarget target);
    private Game.Simulation.NaturalResourceCell ClearFertile(Game.Simulation.NaturalResourceCell cell);
    private Game.Simulation.GroundWater ClearGroundWater(Game.Simulation.GroundWater _);
    private System.Void ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback);
    private Game.Simulation.NaturalResourceCell ClearOil(Game.Simulation.NaturalResourceCell cell);
    private Game.Simulation.NaturalResourceCell ClearOre(Game.Simulation.NaturalResourceCell cell);
    private static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetTextures();
    private System.Void ImportTexture(Game.Prefabs.TerraformingTarget target);
    private static System.Boolean IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab);
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target);
    protected virtual System.Void OnStopRunning();
    private System.Int32 Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_ToolButtonGroup;
```

- `private Game.UI.Editor.EditorSection m_TextureImportButtons`  

```csharp
private Game.UI.Editor.EditorSection m_TextureImportButtons;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_ToolPrefabs;
```

- `private static readonly System.String kTextureImportFolder`  

```csharp
private static readonly System.String kTextureImportFolder;
```


## Constructors

- `public ResourcePanelSystem()`  

```csharp
[Preserve]
	public ResourcePanelSystem()
	{
	}
```


## Methods

- `private ApplyFertile(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ApplyFertile(NaturalResourceCell cell, ushort amount)
	{
		cell.m_Fertility = new NaturalResourceAmount
		{
			m_Base = amount
		};
		return cell;
	}
```

- `private ApplyGroundWater(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<Game.Simulation.GroundWater> data, System.Int32 x, System.Int32 y, System.Func<Game.Simulation.GroundWater, System.UInt16, Game.Simulation.GroundWater> _) : System.Void`  

```csharp
private void ApplyGroundWater(Texture2D texture, CellMapData<GroundWater> data, int x, int y, Func<GroundWater, ushort, GroundWater> _)
	{
		int index = y * data.m_TextureSize.x + x;
		short num = (short)Sample(texture, data, x, y, 10000);
		data.m_Buffer[index] = new GroundWater
		{
			m_Amount = num,
			m_Max = num
		};
	}
```

- `private ApplyOil(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ApplyOil(NaturalResourceCell cell, ushort amount)
	{
		cell.m_Oil = new NaturalResourceAmount
		{
			m_Base = amount
		};
		return cell;
	}
```

- `private ApplyOre(Game.Simulation.NaturalResourceCell cell, System.UInt16 amount) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ApplyOre(NaturalResourceCell cell, ushort amount)
	{
		cell.m_Ore = new NaturalResourceAmount
		{
			m_Base = amount
		};
		return cell;
	}
```

- `private ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback) : System.Void`  

```csharp
private System.Void ApplyResource<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Func<TCell, System.UInt16, TCell> applyCallback);
```

- `private ApplyTexture(UnityEngine.Texture2D texture, Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private void ApplyTexture(Texture2D texture, TerraformingTarget target)
	{
		switch (target)
		{
		case TerraformingTarget.GroundWater:
			ApplyTexture(texture, m_GroundWaterSystem, ApplyGroundWater, null);
			break;
		case TerraformingTarget.Ore:
			ApplyTexture(texture, m_NaturalResourceSystem, ApplyResource, ApplyOre);
			break;
		case TerraformingTarget.Oil:
			ApplyTexture(texture, m_NaturalResourceSystem, ApplyResource, ApplyOil);
			break;
		case TerraformingTarget.FertileLand:
			ApplyTexture(texture, m_NaturalResourceSystem, ApplyResource, ApplyFertile);
			break;
		}
	}
```

- `private ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback) : System.Void`  

```csharp
private System.Void ApplyTexture<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Action<UnityEngine.Texture2D, Game.Simulation.CellMapData<TCell>, System.Int32, System.Int32, System.Func<TCell, System.UInt16, TCell>> applyCallback, System.Func<TCell, System.UInt16, TCell> resourceCallback);
```

- `private Clear(Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private void Clear(TerraformingTarget target)
	{
		switch (target)
		{
		case TerraformingTarget.GroundWater:
			ClearMap(m_GroundWaterSystem, ClearGroundWater);
			break;
		case TerraformingTarget.Ore:
			ClearMap(m_NaturalResourceSystem, ClearOre);
			break;
		case TerraformingTarget.Oil:
			ClearMap(m_NaturalResourceSystem, ClearOil);
			break;
		case TerraformingTarget.FertileLand:
			ClearMap(m_NaturalResourceSystem, ClearFertile);
			break;
		}
	}
```

- `private ClearFertile(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ClearFertile(NaturalResourceCell cell)
	{
		cell.m_Fertility = default(NaturalResourceAmount);
		return cell;
	}
```

- `private ClearGroundWater(Game.Simulation.GroundWater _) : Game.Simulation.GroundWater`  

```csharp
private GroundWater ClearGroundWater(GroundWater _)
	{
		return default(GroundWater);
	}
```

- `private ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback) : System.Void`  

```csharp
private System.Void ClearMap<TCell>(Game.Simulation.CellMapSystem<TCell> cellMapSystem, System.Func<TCell, TCell> clearCallback);
```

- `private ClearOil(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ClearOil(NaturalResourceCell cell)
	{
		cell.m_Oil = default(NaturalResourceAmount);
		return cell;
	}
```

- `private ClearOre(Game.Simulation.NaturalResourceCell cell) : Game.Simulation.NaturalResourceCell`  

```csharp
private NaturalResourceCell ClearOre(NaturalResourceCell cell)
	{
		cell.m_Ore = default(NaturalResourceAmount);
		return cell;
	}
```

- `private static GetTextures() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private static IEnumerable<AssetItem> GetTextures()
	{
		foreach (ImageAsset asset in AssetDatabase.global.GetAssets(SearchFilter<ImageAsset>.ByCondition((ImageAsset a) => a.GetMeta().subPath?.StartsWith(kTextureImportFolder) ?? false)))
		{
			yield return new AssetItem
			{
				guid = asset.id,
				fileName = asset.name,
				displayName = asset.name,
				image = asset.ToUri()
			};
		}
	}
```

- `private ImportTexture(Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private void ImportTexture(TerraformingTarget target)
	{
		base.activeSubPanel = new LoadAssetPanel("Import " + target, GetTextures(), delegate(Colossal.Hash128 guid)
		{
			OnLoadTexture(guid, target);
		}, base.CloseSubPanel);
	}
```

- `private static IsResourceTerraformingPrefab(Game.Prefabs.TerraformingPrefab prefab) : System.Boolean`  

```csharp
private static bool IsResourceTerraformingPrefab(TerraformingPrefab prefab)
	{
		if (prefab.m_Target != TerraformingTarget.Height && prefab.m_Target != TerraformingTarget.Material)
		{
			return prefab.m_Target != TerraformingTarget.None;
		}
		return false;
	}
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected override bool OnCancel()
	{
		if (m_ToolPrefabs.Contains(m_ToolSystem.activePrefab))
		{
			m_ToolSystem.ActivatePrefabTool(null);
			return false;
		}
		return base.OnCancel();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_GroundWaterSystem = base.World.GetExistingSystemManaged<GroundWaterSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<TerraformingData>(),
				ComponentType.ReadOnly<UIObjectData>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		title = "Editor.RESOURCES";
		IWidget[] array = new IWidget[1];
		IWidget[] obj = new IWidget[2]
		{
			new EditorSection
			{
				displayName = "Editor.RESOURCE_TOOLS",
				tooltip = "Editor.RESOURCE_TOOLS_TOOLTIP",
				expanded = true,
				children = new IWidget[1] { m_ToolButtonGroup = new IconButtonGroup() }
			},
			null
		};
		EditorSection obj2 = new EditorSection
		{
			displayName = "Editor.RESOURCE_TEXTURE_LABEL",
			tooltip = "Editor.RESOURCE_TEXTURE_LABEL_TOOLTIP",
			expanded = true
		};
		EditorSection editorSection = obj2;
		m_TextureImportButtons = obj2;
		obj[1] = editorSection;
		array[0] = Scrollable.WithChildren(obj);
		children = array;
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_ToolPrefabs.Clear();
		List<IconButton> list = new List<IconButton>();
		List<IWidget> list2 = new List<IWidget>();
		using NativeList<UIObjectInfo> nativeList = UIObjectInfo.GetSortedObjects(m_PrefabQuery, Allocator.Temp);
		foreach (UIObjectInfo item in nativeList)
		{
			TerraformingPrefab prefab = m_PrefabSystem.GetPrefab<TerraformingPrefab>(item.prefabData);
			if (IsResourceTerraformingPrefab(prefab))
			{
				m_ToolPrefabs.Add(prefab);
				list.Add(new IconButton
				{
					icon = (ImageSystem.GetIcon(prefab) ?? "Media/Editor/Terrain.svg"),
					tooltip = LocalizedString.Id("Assets.NAME[" + prefab.name + "]"),
					action = delegate
					{
						m_ToolSystem.ActivatePrefabTool((m_ToolSystem.activePrefab != prefab) ? prefab : null);
					},
					selected = () => m_ToolSystem.activePrefab == prefab
				});
				list2.Add(new ButtonRow
				{
					children = new Button[2]
					{
						new Button
						{
							displayName = $"Editor.IMPORT_RESOURCE[{prefab.m_Target}]",
							tooltip = $"Editor.IMPORT_RESOURCE_TOOLTIP[{prefab.m_Target}]",
							action = delegate
							{
								ImportTexture(prefab.m_Target);
							}
						},
						new Button
						{
							displayName = $"Editor.CLEAR_RESOURCE[{prefab.m_Target}]",
							tooltip = $"Editor.CLEAR_RESOURCE_TOOLTIP[{prefab.m_Target}]",
							action = delegate
							{
								Clear(prefab.m_Target);
							}
						}
					}
				});
			}
		}
		m_ToolButtonGroup.children = list.ToArray();
		m_TextureImportButtons.children = list2;
	}
```

- `private OnLoadTexture(Colossal.Hash128 guid, Game.Prefabs.TerraformingTarget target) : System.Void`  

```csharp
private void OnLoadTexture(Colossal.Hash128 guid, TerraformingTarget target)
	{
		CloseSubPanel();
		if (AssetDatabase.global.TryGetAsset(guid, out ImageAsset asset))
		{
			using (asset)
			{
				Texture2D texture = asset.Load(srgb: true);
				ApplyTexture(texture, target);
			}
		}
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		if (m_ToolPrefabs.Contains(m_ToolSystem.activePrefab))
		{
			m_ToolSystem.ActivatePrefabTool(null);
		}
	}
```

- `private Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max) : System.Int32`  

```csharp
private System.Int32 Sample<TCell>(UnityEngine.Texture2D texture, Game.Simulation.CellMapData<TCell> data, System.Int32 x, System.Int32 y, System.Int32 max);
```


## Nested types

- `Game.UI.Editor.ResourcePanelSystem+<>c`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass10_0`  
- `Game.UI.Editor.ResourcePanelSystem+<>c__DisplayClass14_0`  
- `Game.UI.Editor.ResourcePanelSystem+<GetTextures>d__15`  

