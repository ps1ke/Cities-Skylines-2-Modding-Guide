# Game.UI.Editor.AssetImportPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class AssetImportPanel : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private System.String m_SelectedProjectRoot;
    private System.String m_SelectedDirectory;
    private System.Boolean m_ProjectRootSelected;
    private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton;
    private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton;
    private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets;
    private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets;
    private Game.UI.Editor.FilePickerAdapter m_Adapter;
    private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList;
    private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter;
    private Game.Prefabs.PrefabBase m_SelectedTemplate;
    private Game.UI.Widgets.Button m_ImportButton;
    private System.Boolean m_Importing;

    private System.Boolean importing { private get; private set; }

    public AssetImportPanel();

    private Game.Prefabs.PrefabBase <OnStartRunning>b__16_0();
    private System.Void <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab);
    private System.Void CloseDirectoryBrowser();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem> GetAssets();
    private System.Void ImportAssets();
    public static System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory> ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log);
    private System.Boolean IsImportDisabled();
    private System.Boolean IsSelectedAssetFolderDisabled();
    private System.Void OnAssetSelected(Game.UI.Editor.FileItem item);
    private System.Void OnLoadAsset(System.Guid guid);
    private System.Void OnSelectDirectory(System.String directory);
    private System.Void OnSelectProjectRoot(System.String directory);
    protected virtual System.Void OnStartRunning();
    private System.Void OpenAssetSubDirectory();
    private System.Void OpenDirectory();
    private static System.Boolean ReportProgress(System.String title, System.String info, System.Single progress);
}
```


## Fields

- `private System.String m_SelectedProjectRoot`  

```csharp
private System.String m_SelectedProjectRoot;
```

- `private System.String m_SelectedDirectory`  

```csharp
private System.String m_SelectedDirectory;
```

- `private System.Boolean m_ProjectRootSelected`  

```csharp
private System.Boolean m_ProjectRootSelected;
```

- `private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton`  

```csharp
private Game.UI.Widgets.DirectoryPickerButton m_OpenProjectRootButton;
```

- `private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton`  

```csharp
private Game.UI.Widgets.DirectoryPickerButton m_OpenSelectedAssetPathButton;
```

- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_Assets;
```

- `private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.FileItem> m_CachedAssets;
```

- `private Game.UI.Editor.FilePickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.FilePickerAdapter m_Adapter;
```

- `private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList`  

```csharp
private Game.UI.Editor.ItemPicker<Game.UI.Editor.FileItem> m_AssetList;
```

- `private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter`  

```csharp
private Game.UI.Editor.ItemPickerFooter m_ItemPickerFooter;
```

- `private Game.Prefabs.PrefabBase m_SelectedTemplate`  

```csharp
private Game.Prefabs.PrefabBase m_SelectedTemplate;
```

- `private Game.UI.Widgets.Button m_ImportButton`  

```csharp
private Game.UI.Widgets.Button m_ImportButton;
```

- `private System.Boolean m_Importing`  

```csharp
private System.Boolean m_Importing;
```


## Properties

- `private System.Boolean importing { private get; private set }`  

```csharp
private System.Boolean importing { private get; private set; }
```


## Constructors

- `public AssetImportPanel()`  

```csharp
[Preserve]
	public AssetImportPanel()
	{
	}
```


## Methods

- `private <OnStartRunning>b__16_0() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnStartRunning>b__16_0();
```

- `private <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void <OnStartRunning>b__16_1(Game.Prefabs.PrefabBase prefab);
```

- `private CloseDirectoryBrowser() : System.Void`  

```csharp
private void CloseDirectoryBrowser()
	{
		CloseSubPanel();
	}
```

- `private GetAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.FileItem>`  

```csharp
private IEnumerable<FileItem> GetAssets()
	{
		if (m_SelectedDirectory == null)
		{
			yield break;
		}
		PostProcessorCache.CachePostProcessors();
		ImporterCache.CacheSupportedExtensions();
		Report report = new Report();
		IDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> dictionary = AssetImportPipeline.CollectDataToImport(m_SelectedProjectRoot, new string[1] { m_SelectedDirectory }, report);
		foreach (KeyValuePair<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> item in dictionary)
		{
			foreach (SourceAssetCollector.Asset item2 in item.Key)
			{
				yield return new FileItem
				{
					path = item2.path,
					displayName = item2.name,
					tooltip = item2.path
				};
			}
		}
	}
```

- `private ImportAssets() : System.Void`  

```csharp
public static async Task<PrefabFactory> ImportAssets(string selectedProjectRoot, string selectedDirectory, PrefabBase selectedTemplate, World world, ILog log)
	{
		PrefabFactory prefabFactory = null;
		try
		{
			EditorSettings editorSettings = SharedSettings.instance?.editor;
			if (selectedProjectRoot == null)
			{
				throw new Exception("The path must contains ProjectFiles to act as the root folder of the art assets");
			}
			if (AssetImportPipeline.IsArtRootPath(selectedProjectRoot, new string[1] { selectedDirectory }, out var artProjectPath, out var artProjectRelativePaths))
			{
				prefabFactory = new PrefabFactory();
				AssetImportPipeline.useParallelImport = editorSettings?.useParallelImport ?? true;
				AssetImportPipeline.targetDatabase = AssetDatabase.user;
				TextureImporter.overrideCompressionEffort = ((!(editorSettings?.lowQualityTextureCompression ?? true)) ? (-1) : 0);
				await AssetImportPipeline.ImportPath(artProjectPath, artProjectRelativePaths, ImportMode.All, convertToVT: false, ReportProgress, prefabFactory);
				PrefabSystem orCreateSystemManaged = world.GetOrCreateSystemManaged<PrefabSystem>();
				ToolSystem orCreateSystemManaged2 = world.GetOrCreateSystemManaged<ToolSystem>();
				foreach (var rootPrefab in prefabFactory.rootPrefabs)
				{
					log.InfoFormat("Root prefab: {0} ({1})", rootPrefab.prefab.name, rootPrefab.source);
					string fileName = Path.GetFileName(rootPrefab.source);
					string subPath = "StreamingData~/" + fileName;
					if (selectedTemplate != null)
					{
						PrefabBase prefabBase = selectedTemplate.Clone(fileName);
						if (prefabBase is ObjectGeometryPrefab objectGeometryPrefab)
						{
							objectGeometryPrefab.m_Meshes = new ObjectMeshInfo[1]
							{
								new ObjectMeshInfo
								{
									m_Mesh = (rootPrefab.prefab as RenderPrefabBase)
								}
							};
						}
						prefabBase.Remove<ObjectSubObjects>();
						prefabBase.Remove<ObjectSubAreas>();
						prefabBase.Remove<ObjectSubLanes>();
						prefabBase.Remove<ObjectSubNets>();
						prefabBase.Remove<NetSubObjects>();
						prefabBase.Remove<AreaSubObjects>();
						prefabBase.Remove<EffectSource>();
						prefabBase.Remove<ObsoleteIdentifiers>();
						AssetImportPipeline.targetDatabase.AddAsset(AssetDataPath.Create(subPath, prefabBase.name ?? ""), prefabBase).Save();
						orCreateSystemManaged.AddPrefab(prefabBase);
						orCreateSystemManaged2.ActivatePrefabTool(prefabBase);
					}
					else
					{
						if (rootPrefab.prefab.asset == null)
						{
							AssetImportPipeline.targetDatabase.AddAsset(AssetDataPath.Create(subPath, rootPrefab.prefab.name ?? ""), rootPrefab.prefab);
						}
						rootPrefab.prefab.asset.Save(force: true);
						orCreateSystemManaged.AddPrefab(rootPrefab.prefab);
					}
				}
			}
			else
			{
				log.Error("The path must contains ProjectFiles to act as the root folder of the art assets");
			}
		}
		catch (Exception exception)
		{
			log.Error(exception);
		}
		return prefabFactory;
	}
```

- `public static ImportAssets(System.String selectedProjectRoot, System.String selectedDirectory, Game.Prefabs.PrefabBase selectedTemplate, Unity.Entities.World world, Colossal.Logging.ILog log) : System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory>`  

```csharp
public static async Task<PrefabFactory> ImportAssets(string selectedProjectRoot, string selectedDirectory, PrefabBase selectedTemplate, World world, ILog log)
	{
		PrefabFactory prefabFactory = null;
		try
		{
			EditorSettings editorSettings = SharedSettings.instance?.editor;
			if (selectedProjectRoot == null)
			{
				throw new Exception("The path must contains ProjectFiles to act as the root folder of the art assets");
			}
			if (AssetImportPipeline.IsArtRootPath(selectedProjectRoot, new string[1] { selectedDirectory }, out var artProjectPath, out var artProjectRelativePaths))
			{
				prefabFactory = new PrefabFactory();
				AssetImportPipeline.useParallelImport = editorSettings?.useParallelImport ?? true;
				AssetImportPipeline.targetDatabase = AssetDatabase.user;
				TextureImporter.overrideCompressionEffort = ((!(editorSettings?.lowQualityTextureCompression ?? true)) ? (-1) : 0);
				await AssetImportPipeline.ImportPath(artProjectPath, artProjectRelativePaths, ImportMode.All, convertToVT: false, ReportProgress, prefabFactory);
				PrefabSystem orCreateSystemManaged = world.GetOrCreateSystemManaged<PrefabSystem>();
				ToolSystem orCreateSystemManaged2 = world.GetOrCreateSystemManaged<ToolSystem>();
				foreach (var rootPrefab in prefabFactory.rootPrefabs)
				{
					log.InfoFormat("Root prefab: {0} ({1})", rootPrefab.prefab.name, rootPrefab.source);
					string fileName = Path.GetFileName(rootPrefab.source);
					string subPath = "StreamingData~/" + fileName;
					if (selectedTemplate != null)
					{
						PrefabBase prefabBase = selectedTemplate.Clone(fileName);
						if (prefabBase is ObjectGeometryPrefab objectGeometryPrefab)
						{
							objectGeometryPrefab.m_Meshes = new ObjectMeshInfo[1]
							{
								new ObjectMeshInfo
								{
									m_Mesh = (rootPrefab.prefab as RenderPrefabBase)
								}
							};
						}
						prefabBase.Remove<ObjectSubObjects>();
						prefabBase.Remove<ObjectSubAreas>();
						prefabBase.Remove<ObjectSubLanes>();
						prefabBase.Remove<ObjectSubNets>();
						prefabBase.Remove<NetSubObjects>();
						prefabBase.Remove<AreaSubObjects>();
						prefabBase.Remove<EffectSource>();
						prefabBase.Remove<ObsoleteIdentifiers>();
						AssetImportPipeline.targetDatabase.AddAsset(AssetDataPath.Create(subPath, prefabBase.name ?? ""), prefabBase).Save();
						orCreateSystemManaged.AddPrefab(prefabBase);
						orCreateSystemManaged2.ActivatePrefabTool(prefabBase);
					}
					else
					{
						if (rootPrefab.prefab.asset == null)
						{
							AssetImportPipeline.targetDatabase.AddAsset(AssetDataPath.Create(subPath, rootPrefab.prefab.name ?? ""), rootPrefab.prefab);
						}
						rootPrefab.prefab.asset.Save(force: true);
						orCreateSystemManaged.AddPrefab(rootPrefab.prefab);
					}
				}
			}
			else
			{
				log.Error("The path must contains ProjectFiles to act as the root folder of the art assets");
			}
		}
		catch (Exception exception)
		{
			log.Error(exception);
		}
		return prefabFactory;
	}
```

- `private IsImportDisabled() : System.Boolean`  

```csharp
private bool IsImportDisabled()
	{
		if (!importing)
		{
			return !m_Assets.Any();
		}
		return true;
	}
```

- `private IsSelectedAssetFolderDisabled() : System.Boolean`  

```csharp
private bool IsSelectedAssetFolderDisabled()
	{
		if (!string.IsNullOrEmpty(m_SelectedProjectRoot))
		{
			return !m_ProjectRootSelected;
		}
		return true;
	}
```

- `private OnAssetSelected(Game.UI.Editor.FileItem item) : System.Void`  

```csharp
private void OnAssetSelected(FileItem item)
	{
		UnityEngine.Debug.Log("Asset selected " + item.displayName);
	}
```

- `private OnLoadAsset(System.Guid guid) : System.Void`  

```csharp
private void OnLoadAsset(Guid guid)
	{
		CloseSubPanel();
	}
```

- `private OnSelectDirectory(System.String directory) : System.Void`  

```csharp
private void OnSelectDirectory(string directory)
	{
		CloseSubPanel();
		string text = directory.Remove(directory.Length - 1);
		if (text.LastIndexOf('/') != -1)
		{
			m_OpenSelectedAssetPathButton.displayValue = ".." + text.Substring(text.LastIndexOf('/')) + "/";
		}
		else
		{
			m_OpenSelectedAssetPathButton.displayValue = text;
		}
		m_OpenSelectedAssetPathButton.tooltip = text;
		m_SelectedDirectory = text;
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings != null)
		{
			editorSettings.lastSelectedImportDirectory = m_SelectedDirectory;
			editorSettings.ApplyAndSave();
		}
		m_Assets = GetAssets().ToList();
		m_Adapter = new FilePickerAdapter(m_Assets);
		FilePickerAdapter adapter = m_Adapter;
		adapter.EventItemSelected = (Action<FileItem>)Delegate.Combine(adapter.EventItemSelected, new Action<FileItem>(OnAssetSelected));
		m_AssetList.adapter = m_Adapter;
		m_ItemPickerFooter.adapter = m_Adapter;
	}
```

- `private OnSelectProjectRoot(System.String directory) : System.Void`  

```csharp
private void OnSelectProjectRoot(string directory)
	{
		CloseSubPanel();
		string text = directory.Remove(directory.Length - 1);
		if (text != m_SelectedProjectRoot)
		{
			m_SelectedDirectory = null;
			m_OpenSelectedAssetPathButton.displayValue = "";
			m_OpenSelectedAssetPathButton.tooltip = "Select asset folder";
		}
		if (text.LastIndexOf('/') != -1)
		{
			m_OpenProjectRootButton.displayValue = ".." + text.Substring(text.LastIndexOf('/')) + "/";
		}
		else
		{
			m_OpenProjectRootButton.displayValue = text;
		}
		m_OpenProjectRootButton.tooltip = text;
		m_SelectedProjectRoot = text;
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings != null)
		{
			editorSettings.lastSelectedProjectRootDirectory = m_SelectedProjectRoot;
			editorSettings.ApplyAndSave();
		}
		m_Assets.Clear();
		m_Adapter = new FilePickerAdapter(m_Assets);
		FilePickerAdapter adapter = m_Adapter;
		adapter.EventItemSelected = (Action<FileItem>)Delegate.Combine(adapter.EventItemSelected, new Action<FileItem>(OnAssetSelected));
		m_AssetList.adapter = m_Adapter;
		m_ItemPickerFooter.adapter = m_Adapter;
		m_ProjectRootSelected = true;
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		base.activeSubPanel = null;
		m_Assets = GetAssets().ToList();
		m_Adapter = new FilePickerAdapter(m_Assets);
		FilePickerAdapter adapter = m_Adapter;
		adapter.EventItemSelected = (Action<FileItem>)Delegate.Combine(adapter.EventItemSelected, new Action<FileItem>(OnAssetSelected));
		m_OpenProjectRootButton = new DirectoryPickerButton
		{
			displayName = "Editor.PROJECT_ROOT",
			action = OpenDirectory,
			tooltip = "Editor.PROJECT_ROOT_TOOLTIP",
			uiTag = "UITagPrefab:SelectProjectRoot"
		};
		m_OpenSelectedAssetPathButton = new DirectoryPickerButton
		{
			displayName = "Editor.SELECTED_ASSETS",
			action = OpenAssetSubDirectory,
			disabled = IsSelectedAssetFolderDisabled,
			tooltip = "Editor.SELECTED_ASSETS_TOOLTIP",
			uiTag = "UITagPrefab:SelectAssets"
		};
		m_AssetList = new ItemPicker<FileItem>
		{
			adapter = m_Adapter
		};
		m_ItemPickerFooter = new ItemPickerFooter
		{
			adapter = m_Adapter
		};
		title = "Editor.TOOL[AssetImportTool]";
		IWidget[] obj = new IWidget[7]
		{
			m_OpenProjectRootButton,
			m_OpenSelectedAssetPathButton,
			m_AssetList,
			m_ItemPickerFooter,
			new PopupValueField<PrefabBase>
			{
				displayName = "Editor.SELECT_TEMPLATE",
				uiTag = "UITagPrefab:SelectTemplate",
				accessor = new DelegateAccessor<PrefabBase>(() => m_SelectedTemplate, delegate(PrefabBase prefab)
				{
					m_SelectedTemplate = prefab;
				}),
				disabled = IsImportDisabled,
				popup = new PrefabPickerPopup(typeof(ObjectGeometryPrefab))
				{
					nullable = true
				}
			},
			null,
			null
		};
		Button obj2 = new Button
		{
			displayName = "Editor.IMPORT",
			action = ImportAssets,
			disabled = IsImportDisabled,
			tooltip = "Import selected assets",
			uiTag = "UITagPrefab:ImportButton"
		};
		Button button = obj2;
		m_ImportButton = obj2;
		obj[5] = button;
		obj[6] = new ImageField
		{
			m_URI = "Media/Menu/InstaLOD-Logo-BW-WhiteOnBlack.svg",
			m_Label = "Editor.INSTALOD_LABEL"
		};
		children = obj;
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		m_SelectedProjectRoot = editorSettings?.lastSelectedProjectRootDirectory;
		m_SelectedDirectory = editorSettings?.lastSelectedImportDirectory;
		try
		{
			if (!string.IsNullOrEmpty(m_SelectedProjectRoot))
			{
				OnSelectProjectRoot(m_SelectedProjectRoot + "/");
				if (!string.IsNullOrEmpty(m_SelectedDirectory))
				{
					OnSelectDirectory(m_SelectedDirectory + "/");
				}
			}
		}
		catch (Exception exception)
		{
			base.log.Error(exception, "Exception occured while trying to select project root or import directory " + m_SelectedProjectRoot + ", " + m_SelectedDirectory);
			m_SelectedProjectRoot = string.Empty;
			m_SelectedDirectory = string.Empty;
			OnSelectProjectRoot(m_SelectedProjectRoot + "/");
			OnSelectDirectory(m_SelectedDirectory + "/");
		}
	}
```

- `private OpenAssetSubDirectory() : System.Void`  

```csharp
private void OpenAssetSubDirectory()
	{
		if (string.IsNullOrEmpty(m_SelectedDirectory) || !m_SelectedDirectory.StartsWith(m_SelectedProjectRoot))
		{
			m_SelectedDirectory = m_SelectedProjectRoot;
		}
		base.activeSubPanel = new DirectoryBrowserPanel(m_SelectedDirectory, m_SelectedProjectRoot, OnSelectDirectory, CloseDirectoryBrowser);
	}
```

- `private OpenDirectory() : System.Void`  

```csharp
private void OpenDirectory()
	{
		base.activeSubPanel = new DirectoryBrowserPanel(m_SelectedProjectRoot, null, OnSelectProjectRoot, CloseDirectoryBrowser);
	}
```

- `private static ReportProgress(System.String title, System.String info, System.Single progress) : System.Boolean`  

```csharp
private static bool ReportProgress(string title, string info, float progress)
	{
		if (progress == 1f)
		{
			UnityEngine.Debug.Log("Import completed");
		}
		return false;
	}
```


## Nested types

- `Game.UI.Editor.AssetImportPanel+PrefabFactory`  
- `Game.UI.Editor.AssetImportPanel+<GetAssets>d__24`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__29`  
- `Game.UI.Editor.AssetImportPanel+<ImportAssets>d__30`  

