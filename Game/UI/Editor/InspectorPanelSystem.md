# Game.UI.Editor.InspectorPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InspectorPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectTool;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
    private Game.Input.ProxyAction m_MoveAction;
    private Game.Input.ProxyAction m_CloneAction;
    private Game.Input.ProxyAction m_AutoAlignAction;
    private Game.Input.ProxyAction m_AutoConnectAction;
    private Game.Input.ProxyAction m_AlignXAction;
    private Game.Input.ProxyAction m_AlignYAction;
    private Game.Input.ProxyAction m_AlignZAction;
    private Game.UI.Widgets.EditorGenerator m_EditorGenerator;
    private Game.UI.Widgets.Button[] m_MeshFooter;
    private Game.UI.Widgets.Button[] m_InstanceFooter;
    private Game.UI.Widgets.Button[] m_PrefabFooter;
    private Game.UI.Widgets.Button[] m_CustomAssetFooter;
    private Unity.Entities.Entity m_CurrentSelectedEntity;
    private System.Object m_SelectedObject;
    private System.Object m_ParentObject;
    private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject;
    private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject;
    private Game.UI.Localization.LocalizedString m_SelectedName;
    private Game.UI.Localization.LocalizedString m_ParentName;
    private System.Collections.Generic.List<System.Object> m_SectionObjects;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;

    private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get; }
    private System.Boolean canMoveSelected { private get; }
    private System.Boolean canCloneSelected { private get; }
    private System.Boolean canAlignSelected { private get; }

    public InspectorPanelSystem();

    private System.Void <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Boolean <OnCreate>b__32_1();
    private System.Boolean <OnCreate>b__32_2();
    private System.Boolean <OnCreate>b__32_3();
    private System.Void <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void AlignX();
    private System.Void AlignY();
    private System.Void AlignZ();
    private System.Void AutoAlign();
    private System.Void AutoConnect();
    private System.Void BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets);
    private System.Void CloneSelected();
    public static System.Void DisableAllFields(Game.UI.Widgets.IWidget widget);
    private System.Boolean DisableSection(System.Object obj, System.Object parent);
    private Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab);
    private System.Boolean FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info);
    private static Game.Reflection.ITypedValueAccessor<System.Boolean> GetActiveAccessor(Game.Prefabs.ComponentBase component);
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> GetComponentTypeItems();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetCustomAssets();
    private Game.UI.Localization.LocalizedString GetObjectName(System.Object obj);
    private System.Collections.Generic.IEnumerable<System.Object> GetSectionObjects();
    private System.Void HandleInput();
    private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key);
    private static System.Boolean IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset);
    private System.Boolean IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh);
    private System.Boolean IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh);
    private System.Void MoveSelected();
    private System.Void MoveSubObjects(Game.Prefabs.PrefabBase prefab);
    private System.Void OnAddComponent(System.Type type);
    private System.Void OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex);
    protected virtual System.Void OnCreate();
    private System.Void OnDuplicate();
    private System.Void OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
    private System.Void OnLocate();
    private System.Void OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
    private System.Void OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    private System.Void RefreshContent();
    private System.Void RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren);
    private System.Void RefreshSections();
    private System.Void RefreshTitle();
    private System.Void SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback);
    private System.Void SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name);
    private System.Void SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name);
    public System.Boolean SelectEntity(Unity.Entities.Entity entity);
    private System.Void SelectInUnityEditor(UnityEngine.Object obj);
    public System.Boolean SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex);
    private System.Boolean SelectObjectForEntity(Unity.Entities.Entity entity);
    public System.Void SelectPrefab(Game.Prefabs.PrefabBase prefab);
    private System.Void ShowAddComponentPicker();
    private System.Void ShowSaveAssetPanel();
    private System.Void ShowShareAssetPanel();
    public System.Void ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback);
    private System.Boolean TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item);
    private System.Void UpdateParent(System.Boolean moveSubObjects);
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

- `private Game.Tools.ObjectToolSystem m_ObjectTool`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectTool;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel`  

```csharp
private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
```

- `private Game.Input.ProxyAction m_MoveAction`  

```csharp
private Game.Input.ProxyAction m_MoveAction;
```

- `private Game.Input.ProxyAction m_CloneAction`  

```csharp
private Game.Input.ProxyAction m_CloneAction;
```

- `private Game.Input.ProxyAction m_AutoAlignAction`  

```csharp
private Game.Input.ProxyAction m_AutoAlignAction;
```

- `private Game.Input.ProxyAction m_AutoConnectAction`  

```csharp
private Game.Input.ProxyAction m_AutoConnectAction;
```

- `private Game.Input.ProxyAction m_AlignXAction`  

```csharp
private Game.Input.ProxyAction m_AlignXAction;
```

- `private Game.Input.ProxyAction m_AlignYAction`  

```csharp
private Game.Input.ProxyAction m_AlignYAction;
```

- `private Game.Input.ProxyAction m_AlignZAction`  

```csharp
private Game.Input.ProxyAction m_AlignZAction;
```

- `private Game.UI.Widgets.EditorGenerator m_EditorGenerator`  

```csharp
private Game.UI.Widgets.EditorGenerator m_EditorGenerator;
```

- `private Game.UI.Widgets.Button[] m_MeshFooter`  

```csharp
private Game.UI.Widgets.Button[] m_MeshFooter;
```

- `private Game.UI.Widgets.Button[] m_InstanceFooter`  

```csharp
private Game.UI.Widgets.Button[] m_InstanceFooter;
```

- `private Game.UI.Widgets.Button[] m_PrefabFooter`  

```csharp
private Game.UI.Widgets.Button[] m_PrefabFooter;
```

- `private Game.UI.Widgets.Button[] m_CustomAssetFooter`  

```csharp
private Game.UI.Widgets.Button[] m_CustomAssetFooter;
```

- `private Unity.Entities.Entity m_CurrentSelectedEntity`  

```csharp
private Unity.Entities.Entity m_CurrentSelectedEntity;
```

- `private System.Object m_SelectedObject`  

```csharp
private System.Object m_SelectedObject;
```

- `private System.Object m_ParentObject`  

```csharp
private System.Object m_ParentObject;
```

- `private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject`  

```csharp
private Game.Prefabs.ObjectSubObjectInfo m_LastSubObject;
```

- `private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject`  

```csharp
private Game.Prefabs.ObjectSubObjectInfo m_CurrentSubObject;
```

- `private Game.UI.Localization.LocalizedString m_SelectedName`  

```csharp
private Game.UI.Localization.LocalizedString m_SelectedName;
```

- `private Game.UI.Localization.LocalizedString m_ParentName`  

```csharp
private Game.UI.Localization.LocalizedString m_ParentName;
```

- `private System.Collections.Generic.List<System.Object> m_SectionObjects`  

```csharp
private System.Collections.Generic.List<System.Object> m_SectionObjects;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Game.UI.Editor.InspectorPanelSystem+LocalizationFields> m_WipLocalization;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;
```


## Properties

- `private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get }`  

```csharp
private Game.UI.Editor.InspectorPanelSystem+Mode mode { private get; }
```

- `private System.Boolean canMoveSelected { private get }`  

```csharp
private System.Boolean canMoveSelected { private get; }
```

- `private System.Boolean canCloneSelected { private get }`  

```csharp
private System.Boolean canCloneSelected { private get; }
```

- `private System.Boolean canAlignSelected { private get }`  

```csharp
private System.Boolean canAlignSelected { private get; }
```


## Constructors

- `public InspectorPanelSystem()`  

```csharp
[Preserve]
	public InspectorPanelSystem()
	{
	}
```


## Methods

- `private <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <OnCreate>b__32_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private <OnCreate>b__32_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_1();
```

- `private <OnCreate>b__32_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_2();
```

- `private <OnCreate>b__32_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_3();
```

- `private <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowSaveAssetPanel>b__75_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowShareAssetPanel>b__80_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private AlignX() : System.Void`  

```csharp
private void AlignX()
	{
		if (m_CurrentSubObject != null && m_LastSubObject != null)
		{
			m_CurrentSubObject.m_Position.x = m_LastSubObject.m_Position.x;
			UpdateParent(moveSubObjects: false);
		}
	}
```

- `private AlignY() : System.Void`  

```csharp
private void AlignY()
	{
		if (m_CurrentSubObject != null && m_LastSubObject != null)
		{
			m_CurrentSubObject.m_Position.y = m_LastSubObject.m_Position.y;
			UpdateParent(moveSubObjects: false);
		}
	}
```

- `private AlignZ() : System.Void`  

```csharp
private void AlignZ()
	{
		if (m_CurrentSubObject != null && m_LastSubObject != null)
		{
			m_CurrentSubObject.m_Position.z = m_LastSubObject.m_Position.z;
			UpdateParent(moveSubObjects: false);
		}
	}
```

- `private AutoAlign() : System.Void`  

```csharp
private void AutoAlign()
	{
		if (m_CurrentSubObject != null && m_LastSubObject != null)
		{
			float num = Mathf.Abs(m_CurrentSubObject.m_Position.x - m_LastSubObject.m_Position.x);
			float num2 = Mathf.Abs(m_CurrentSubObject.m_Position.y - m_LastSubObject.m_Position.y);
			float num3 = Mathf.Abs(m_CurrentSubObject.m_Position.z - m_LastSubObject.m_Position.z);
			if (num < num2 || num < num3)
			{
				m_CurrentSubObject.m_Position.x = m_LastSubObject.m_Position.x;
			}
			if (num2 < num || num2 < num3)
			{
				m_CurrentSubObject.m_Position.y = m_LastSubObject.m_Position.y;
			}
			if (num3 < num || num3 < num2)
			{
				m_CurrentSubObject.m_Position.z = m_LastSubObject.m_Position.z;
			}
			UpdateParent(moveSubObjects: false);
		}
	}
```

- `private AutoConnect() : System.Void`  

```csharp
private void AutoConnect()
	{
		if (m_CurrentSubObject == null || m_LastSubObject == null)
		{
			return;
		}
		Entity entity = m_PrefabSystem.GetEntity(m_LastSubObject.m_Object);
		Entity entity2 = m_PrefabSystem.GetEntity(m_CurrentSubObject.m_Object);
		if (base.EntityManager.TryGetComponent<ObjectGeometryData>(entity, out var component) && base.EntityManager.TryGetComponent<ObjectGeometryData>(entity2, out var component2))
		{
			float num = Mathf.Abs(m_CurrentSubObject.m_Position.x - m_LastSubObject.m_Position.x);
			float num2 = Mathf.Abs(m_CurrentSubObject.m_Position.y - m_LastSubObject.m_Position.y);
			float num3 = Mathf.Abs(m_CurrentSubObject.m_Position.z - m_LastSubObject.m_Position.z);
			Bounds3 bounds = MathUtils.Bounds(MathUtils.Box(component.m_Bounds, m_LastSubObject.m_Rotation, m_LastSubObject.m_Position));
			Bounds3 bounds2 = MathUtils.Bounds(MathUtils.Box(component2.m_Bounds, m_CurrentSubObject.m_Rotation, m_CurrentSubObject.m_Position));
			if (num > num2 && num > num3)
			{
				if (m_CurrentSubObject.m_Position.x > m_LastSubObject.m_Position.x)
				{
					m_CurrentSubObject.m_Position.x += bounds.max.x - bounds2.min.x;
				}
				else
				{
					m_CurrentSubObject.m_Position.x += bounds.min.x - bounds2.max.x;
				}
			}
			else if (num2 > num && num2 > num3)
			{
				if (m_CurrentSubObject.m_Position.y > m_LastSubObject.m_Position.y)
				{
					m_CurrentSubObject.m_Position.y += bounds.max.y - bounds2.min.y;
				}
				else
				{
					m_CurrentSubObject.m_Position.y += bounds.min.y - bounds2.max.y;
				}
			}
			else if (num3 > num && num3 > num2)
			{
				if (m_CurrentSubObject.m_Position.z > m_LastSubObject.m_Position.z)
				{
					m_CurrentSubObject.m_Position.z += bounds.max.z - bounds2.min.z;
				}
				else
				{
					m_CurrentSubObject.m_Position.z += bounds.min.z - bounds2.max.z;
				}
			}
		}
		UpdateParent(moveSubObjects: false);
	}
```

- `private BuildLocalizationFields(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.UI.Widgets.IWidget> widgets) : System.Void`  

```csharp
private void BuildLocalizationFields(PrefabBase prefab, List<IWidget> widgets)
	{
		if (!m_WipLocalization.TryGetValue(prefab, out var value))
		{
			value = new LocalizationFields
			{
				m_NameLocalization = new LocalizationField("Editor.ASSET_NAME"),
				m_DescriptionLocalization = new LocalizationField("Editor.ASSET_DESCRIPTION")
			};
			List<LocalizationField.LocalizationFieldEntry> entries = InitializeLocalization(prefab, "Assets.NAME[" + prefab.name + "]");
			value.m_NameLocalization.Initialize(entries);
			List<LocalizationField.LocalizationFieldEntry> entries2 = InitializeLocalization(prefab, "Assets.DESCRIPTION[" + prefab.name + "]");
			value.m_DescriptionLocalization.Initialize(entries2);
			m_WipLocalization[prefab] = value;
		}
		widgets.Add(new Game.UI.Widgets.Group
		{
			displayName = "Localized Name",
			children = new IWidget[1] { value.m_NameLocalization },
			tooltip = "Editor.LOCALIZED_NAME_TOOLTIP"
		});
		widgets.Add(new Game.UI.Widgets.Group
		{
			displayName = "Localized Description",
			children = new IWidget[1] { value.m_DescriptionLocalization },
			tooltip = "Editor.LOCALIZED_DESCRIPTION_TOOLTIP"
		});
	}
```

- `private CloneSelected() : System.Void`  

```csharp
private void CloneSelected()
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(m_CurrentSelectedEntity);
		ObjectPrefab prefab = m_PrefabSystem.GetPrefab<ObjectPrefab>(componentData);
		m_ObjectTool.mode = ObjectToolSystem.Mode.Create;
		m_ObjectTool.prefab = prefab;
		m_ToolSystem.activeTool = m_ObjectTool;
		if (m_CurrentSelectedEntity == m_ToolSystem.selected)
		{
			m_ToolSystem.selected = Entity.Null;
		}
	}
```

- `public static DisableAllFields(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public static void DisableAllFields(IWidget widget)
	{
		if (widget is IDisableCallback disableCallback)
		{
			disableCallback.disabled = () => true;
		}
		if (widget is IContainerWidget containerWidget)
		{
			{
				foreach (IWidget child in containerWidget.children)
				{
					DisableAllFields(child);
				}
				return;
			}
		}
		if (widget is ButtonRow { children: var array })
		{
			for (int num = 0; num < array.Length; num++)
			{
				DisableAllFields(array[num]);
			}
		}
	}
```

- `private DisableSection(System.Object obj, System.Object parent) : System.Boolean`  

```csharp
private bool DisableSection(object obj, object parent)
	{
		if (obj is ComponentBase componentBase && componentBase.prefab.builtin)
		{
			return true;
		}
		if ((obj is ObjectMeshInfo || obj is ObjectSubObjectInfo) && parent is ComponentBase componentBase2 && componentBase2.prefab.builtin)
		{
			return true;
		}
		return false;
	}
```

- `private DuplicatePrefab(Game.Prefabs.PrefabBase oldPrefab) : Game.Prefabs.PrefabBase`  

```csharp
private PrefabBase DuplicatePrefab(PrefabBase oldPrefab)
	{
		PrefabBase prefabBase = m_PrefabSystem.DuplicatePrefab(oldPrefab, oldPrefab.name);
		if (m_WipLocalization.TryGetValue(oldPrefab, out var value))
		{
			m_WipLocalization.Add(prefabBase, value.Clone());
		}
		prefabBase.asset = null;
		return prefabBase;
	}
```

- `private FindObjectMeshInfo(Game.Prefabs.ObjectGeometryPrefab prefab, Game.Prefabs.PrefabBase meshPrefab, Game.Prefabs.ObjectMeshInfo& info) : System.Boolean`  

```csharp
private bool FindObjectMeshInfo(ObjectGeometryPrefab prefab, PrefabBase meshPrefab, out ObjectMeshInfo info)
	{
		for (int i = 0; i < prefab.m_Meshes.Length; i++)
		{
			if (prefab.m_Meshes[i].m_Mesh == meshPrefab)
			{
				info = prefab.m_Meshes[i];
				return true;
			}
		}
		info = null;
		return false;
	}
```

- `private static GetActiveAccessor(Game.Prefabs.ComponentBase component) : Game.Reflection.ITypedValueAccessor<System.Boolean>`  

```csharp
private static ITypedValueAccessor<bool> GetActiveAccessor(ComponentBase component)
	{
		return new DelegateAccessor<bool>(() => component.active, delegate(bool value)
		{
			component.active = value;
		});
	}
```

- `private GetComponentTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  

```csharp
private IEnumerable<Item> GetComponentTypeItems()
	{
		object obj = m_SelectedObject;
		if (m_SelectedObject is ObjectMeshInfo objectMeshInfo)
		{
			obj = objectMeshInfo.m_Mesh;
		}
		if (!(obj is PrefabBase selectedPrefab))
		{
			yield break;
		}
		foreach (Type item in TypePickerPanel.GetAllConcreteTypesDerivedFrom<ComponentBase>())
		{
			if (item.IsSubclassOf(typeof(PrefabBase)) || selectedPrefab.Has(item))
			{
				continue;
			}
			Type prefabType = selectedPrefab.GetType();
			if (!(prefabType == item) && item.GetCustomAttribute<HideInEditorAttribute>() == null)
			{
				ComponentMenu customAttribute = item.GetCustomAttribute<ComponentMenu>();
				if (customAttribute?.requiredPrefab == null || customAttribute == null || customAttribute.requiredPrefab.Length == 0 || customAttribute.requiredPrefab.Any((Type t) => t.IsAssignableFrom(prefabType)))
				{
					yield return new Item
					{
						type = item,
						name = WidgetReflectionUtils.NicifyVariableName(item.Name),
						parentDir = customAttribute?.menu
					};
				}
			}
		}
	}
```

- `private GetCustomAssets() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private IEnumerable<AssetItem> GetCustomAssets()
	{
		if (m_SelectedObject is PrefabBase prefabBase && IsBuiltinAsset(prefabBase.asset) && TryGetAssetItem(prefabBase.asset, out var item))
		{
			yield return item;
		}
		foreach (PrefabAsset asset in AssetDatabase.user.GetAssets(default(SearchFilter<PrefabAsset>)))
		{
			if (TryGetAssetItem(asset, out var item2))
			{
				yield return item2;
			}
		}
	}
```

- `private GetObjectName(System.Object obj) : Game.UI.Localization.LocalizedString`  

```csharp
[CanBeNull]
	private LocalizedString GetObjectName([CanBeNull] object obj)
	{
		if (obj == null)
		{
			return null;
		}
		if (obj is PrefabBase prefab)
		{
			return EditorPrefabUtils.GetPrefabLabel(prefab);
		}
		return LocalizedString.Value(m_SelectedObject.GetType().Name);
	}
```

- `private GetSectionObjects() : System.Collections.Generic.IEnumerable<System.Object>`  

```csharp
private IEnumerable<object> GetSectionObjects()
	{
		if (m_SelectedObject == null)
		{
			yield break;
		}
		yield return m_SelectedObject;
		object obj = m_SelectedObject;
		if (obj is PrefabBase prefab)
		{
			for (int i = 0; i < prefab.components.Count; i++)
			{
				if (prefab.components[i].GetType().GetCustomAttribute<HideInEditorAttribute>() == null)
				{
					yield return prefab.components[i];
				}
			}
		}
		obj = m_SelectedObject;
		if (!(obj is ObjectMeshInfo meshInfo))
		{
			yield break;
		}
		yield return meshInfo.m_Mesh;
		for (int i = 0; i < meshInfo.m_Mesh.components.Count; i++)
		{
			if (meshInfo.m_Mesh.components[i].GetType().GetCustomAttribute<HideInEditorAttribute>() == null)
			{
				yield return meshInfo.m_Mesh.components[i];
			}
		}
	}
```

- `private HandleInput() : System.Void`  

```csharp
private void HandleInput()
	{
		m_MoveAction.enabled = canMoveSelected;
		if (m_MoveAction.WasPerformedThisFrame())
		{
			MoveSelected();
		}
		m_CloneAction.enabled = canCloneSelected;
		if (m_CloneAction.WasPerformedThisFrame())
		{
			CloneSelected();
		}
		m_AutoAlignAction.enabled = canAlignSelected;
		if (m_AutoAlignAction.WasPerformedThisFrame())
		{
			AutoAlign();
		}
		m_AutoConnectAction.enabled = canAlignSelected;
		if (m_AutoConnectAction.WasPerformedThisFrame())
		{
			AutoConnect();
		}
		m_AlignXAction.enabled = canAlignSelected;
		if (m_AlignXAction.WasPerformedThisFrame())
		{
			AlignX();
		}
		m_AlignYAction.enabled = canAlignSelected;
		if (m_AlignYAction.WasPerformedThisFrame())
		{
			AlignY();
		}
		m_AlignZAction.enabled = canAlignSelected;
		if (m_AlignZAction.WasPerformedThisFrame())
		{
			AlignZ();
		}
	}
```

- `private InitializeLocalization(Game.Prefabs.PrefabBase prefab, System.String key) : System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  

```csharp
private List<LocalizationField.LocalizationFieldEntry> InitializeLocalization(PrefabBase prefab, string key)
	{
		List<LocalizationField.LocalizationFieldEntry> list = new List<LocalizationField.LocalizationFieldEntry>();
		if (prefab.asset != null && prefab.asset.database == AssetDatabase.user)
		{
			foreach (LocaleAsset localeAsset in EditorPrefabUtils.GetLocaleAssets(prefab))
			{
				if (localeAsset.data.entries.TryGetValue(key, out var value))
				{
					list.Add(new LocalizationField.LocalizationFieldEntry
					{
						localeId = localeAsset.localeId,
						text = value
					});
				}
			}
		}
		else
		{
			foreach (LocaleAsset asset in AssetDatabase.global.GetAssets(default(SearchFilter<LocaleAsset>)))
			{
				if (asset.data.entries.TryGetValue(key, out var value2))
				{
					list.Add(new LocalizationField.LocalizationFieldEntry
					{
						localeId = asset.localeId,
						text = value2
					});
				}
			}
		}
		return list;
	}
```

- `private static IsBuiltinAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  

```csharp
private static bool IsBuiltinAsset(AssetData asset)
	{
		if (asset != null && asset.database != null)
		{
			return asset.database is AssetDatabase<Colossal.IO.AssetDatabase.Game>;
		}
		return false;
	}
```

- `private IsColorVariationField(Game.UI.Widgets.IWidget widget, System.Int32& variationSetIndex, System.Int32& colorIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  

```csharp
private bool IsColorVariationField(IWidget widget, out int variationSetIndex, out int colorIndex, out RenderPrefabBase mesh)
	{
		variationSetIndex = -1;
		colorIndex = -1;
		mesh = null;
		if (widget.path.m_Key == null || !(widget is ColorField) || !(m_SelectedObject is ObjectMeshInfo objectMeshInfo))
		{
			return false;
		}
		Match match = Regex.Match(widget.path.m_Key, "^ColorProperties.m_ColorVariations\\[(\\d+)\\].m_Colors\\[(\\d+)\\]$");
		if (match.Success && int.TryParse(match.Groups[1].Value, out variationSetIndex) && int.TryParse(match.Groups[2].Value, out colorIndex))
		{
			mesh = objectMeshInfo.m_Mesh;
			return true;
		}
		return false;
	}
```

- `private IsEmissiveField(Game.UI.Widgets.IWidget widget, System.Int32& singleLightIndex, System.Int32& multiLightIndex, Game.Prefabs.RenderPrefabBase& mesh) : System.Boolean`  

```csharp
private bool IsEmissiveField(IWidget widget, out int singleLightIndex, out int multiLightIndex, out RenderPrefabBase mesh)
	{
		singleLightIndex = -1;
		multiLightIndex = -1;
		mesh = null;
		if (widget.path.m_Key == null || !(m_SelectedObject is ObjectMeshInfo objectMeshInfo))
		{
			return false;
		}
		Match match = Regex.Match(widget.path.m_Key, "^EmissiveProperties.m_SingleLights\\[(\\d+)\\].");
		if (match.Success && int.TryParse(match.Groups[1].Value, out singleLightIndex))
		{
			mesh = objectMeshInfo.m_Mesh;
			return true;
		}
		match = Regex.Match(widget.path.m_Key, "^EmissiveProperties.m_MultiLights\\[(\\d+)\\].");
		if (match.Success && int.TryParse(match.Groups[1].Value, out multiLightIndex))
		{
			mesh = objectMeshInfo.m_Mesh;
			return true;
		}
		return false;
	}
```

- `private MoveSelected() : System.Void`  

```csharp
private void MoveSelected()
	{
		m_ObjectTool.StartMoving(m_CurrentSelectedEntity);
		m_ToolSystem.activeTool = m_ObjectTool;
	}
```

- `private MoveSubObjects(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void MoveSubObjects(PrefabBase prefab)
	{
		Entity entity = m_PrefabSystem.GetEntity(prefab);
		if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: false, out DynamicBuffer<SubMesh> buffer) || !(prefab is ObjectGeometryPrefab { m_Meshes: not null } objectGeometryPrefab))
		{
			return;
		}
		int num = math.min(buffer.Length, objectGeometryPrefab.m_Meshes.Length);
		for (int i = 0; i < num; i++)
		{
			SubMesh value = buffer[i];
			ObjectMeshInfo objectMeshInfo = objectGeometryPrefab.m_Meshes[i];
			if (value.m_SubMesh != m_PrefabSystem.GetEntity(objectMeshInfo.m_Mesh) || (value.m_Position.Equals(objectMeshInfo.m_Position) && value.m_Rotation.Equals(objectMeshInfo.m_Rotation)))
			{
				continue;
			}
			if (value.m_Rotation.Equals(objectMeshInfo.m_Rotation))
			{
				float3 @float = objectMeshInfo.m_Position - value.m_Position;
				if (prefab.TryGet<ObjectSubObjects>(out var component) && component.m_SubObjects != null)
				{
					for (int j = 0; j < component.m_SubObjects.Length; j++)
					{
						ObjectSubObjectInfo objectSubObjectInfo = component.m_SubObjects[j];
						if (objectSubObjectInfo.m_ParentMesh % 1000 == i)
						{
							objectSubObjectInfo.m_Position += @float;
						}
					}
				}
				if (prefab.TryGet<ObjectSubAreas>(out var component2) && component2.m_SubAreas != null)
				{
					for (int k = 0; k < component2.m_SubAreas.Length; k++)
					{
						ObjectSubAreaInfo objectSubAreaInfo = component2.m_SubAreas[k];
						if (objectSubAreaInfo.m_NodePositions == null || objectSubAreaInfo.m_ParentMeshes == null)
						{
							continue;
						}
						int num2 = math.min(objectSubAreaInfo.m_NodePositions.Length, objectSubAreaInfo.m_ParentMeshes.Length);
						for (int l = 0; l < num2; l++)
						{
							if (objectSubAreaInfo.m_ParentMeshes[l] == i)
							{
								objectSubAreaInfo.m_NodePositions[l] += @float;
							}
						}
					}
				}
				if (prefab.TryGet<ObjectSubLanes>(out var component3) && component3.m_SubLanes != null)
				{
					for (int m = 0; m < component3.m_SubLanes.Length; m++)
					{
						ObjectSubLaneInfo objectSubLaneInfo = component3.m_SubLanes[m];
						bool2 x = objectSubLaneInfo.m_ParentMesh == i;
						if (math.all(x))
						{
							objectSubLaneInfo.m_BezierCurve += @float;
						}
						else if (x.x)
						{
							objectSubLaneInfo.m_BezierCurve.a += @float;
							objectSubLaneInfo.m_BezierCurve.b += @float * (2f / 3f);
							objectSubLaneInfo.m_BezierCurve.c += @float * (1f / 3f);
						}
						else if (x.y)
						{
							objectSubLaneInfo.m_BezierCurve.d += @float;
							objectSubLaneInfo.m_BezierCurve.c += @float * (2f / 3f);
							objectSubLaneInfo.m_BezierCurve.b += @float * (1f / 3f);
						}
					}
				}
				if (prefab.TryGet<ObjectSubNets>(out var component4) && component4.m_SubNets != null)
				{
					for (int n = 0; n < component4.m_SubNets.Length; n++)
					{
						ObjectSubNetInfo objectSubNetInfo = component4.m_SubNets[n];
						bool2 x2 = objectSubNetInfo.m_ParentMesh == i;
						if (math.all(x2))
						{
							objectSubNetInfo.m_BezierCurve += @float;
						}
						else if (x2.x)
						{
							objectSubNetInfo.m_BezierCurve.a += @float;
							objectSubNetInfo.m_BezierCurve.b += @float * (2f / 3f);
							objectSubNetInfo.m_BezierCurve.c += @float * (1f / 3f);
						}
						else if (x2.y)
						{
							objectSubNetInfo.m_BezierCurve.d += @float;
							objectSubNetInfo.m_BezierCurve.c += @float * (2f / 3f);
							objectSubNetInfo.m_BezierCurve.b += @float * (1f / 3f);
						}
					}
				}
				if (prefab.TryGet<EffectSource>(out var component5) && component5.m_Effects != null)
				{
					for (int num3 = 0; num3 < component5.m_Effects.Count; num3++)
					{
						EffectSource.EffectSettings effectSettings = component5.m_Effects[num3];
						if (effectSettings.m_ParentMesh == i)
						{
							effectSettings.m_PositionOffset += @float;
						}
					}
				}
			}
			else
			{
				float4x4 m2 = float4x4.TRS(value.m_Position, value.m_Rotation, 1f);
				float4x4 a = math.mul(float4x4.TRS(objectMeshInfo.m_Position, objectMeshInfo.m_Rotation, 1f), math.inverse(m2));
				quaternion a2 = math.mul(objectMeshInfo.m_Rotation, math.inverse(value.m_Rotation));
				if (prefab.TryGet<ObjectSubObjects>(out var component6) && component6.m_SubObjects != null)
				{
					for (int num4 = 0; num4 < component6.m_SubObjects.Length; num4++)
					{
						ObjectSubObjectInfo objectSubObjectInfo2 = component6.m_SubObjects[num4];
						if (objectSubObjectInfo2.m_ParentMesh % 1000 == i)
						{
							objectSubObjectInfo2.m_Position = math.transform(a, objectSubObjectInfo2.m_Position);
							objectSubObjectInfo2.m_Rotation = math.normalize(math.mul(a2, objectSubObjectInfo2.m_Rotation));
						}
					}
				}
				if (prefab.TryGet<ObjectSubAreas>(out var component7) && component7.m_SubAreas != null)
				{
					for (int num5 = 0; num5 < component7.m_SubAreas.Length; num5++)
					{
						ObjectSubAreaInfo objectSubAreaInfo2 = component7.m_SubAreas[num5];
						if (objectSubAreaInfo2.m_NodePositions == null || objectSubAreaInfo2.m_ParentMeshes == null)
						{
							continue;
						}
						int num6 = math.min(objectSubAreaInfo2.m_NodePositions.Length, objectSubAreaInfo2.m_ParentMeshes.Length);
						for (int num7 = 0; num7 < num6; num7++)
						{
							if (objectSubAreaInfo2.m_ParentMeshes[num7] == i)
							{
								objectSubAreaInfo2.m_NodePositions[num7] = math.transform(a, objectSubAreaInfo2.m_NodePositions[num7]);
							}
						}
					}
				}
				if (prefab.TryGet<ObjectSubLanes>(out var component8) && component8.m_SubLanes != null)
				{
					for (int num8 = 0; num8 < component8.m_SubLanes.Length; num8++)
					{
						ObjectSubLaneInfo objectSubLaneInfo2 = component8.m_SubLanes[num8];
						bool2 x3 = objectSubLaneInfo2.m_ParentMesh == i;
						if (math.all(x3))
						{
							objectSubLaneInfo2.m_BezierCurve.a = math.transform(a, objectSubLaneInfo2.m_BezierCurve.a);
							objectSubLaneInfo2.m_BezierCurve.b = math.transform(a, objectSubLaneInfo2.m_BezierCurve.b);
							objectSubLaneInfo2.m_BezierCurve.c = math.transform(a, objectSubLaneInfo2.m_BezierCurve.c);
							objectSubLaneInfo2.m_BezierCurve.d = math.transform(a, objectSubLaneInfo2.m_BezierCurve.d);
						}
						else if (x3.x)
						{
							objectSubLaneInfo2.m_BezierCurve.a = math.transform(a, objectSubLaneInfo2.m_BezierCurve.a);
							objectSubLaneInfo2.m_BezierCurve.b = math.lerp(objectSubLaneInfo2.m_BezierCurve.b, math.transform(a, objectSubLaneInfo2.m_BezierCurve.b), 2f / 3f);
							objectSubLaneInfo2.m_BezierCurve.c = math.lerp(objectSubLaneInfo2.m_BezierCurve.c, math.transform(a, objectSubLaneInfo2.m_BezierCurve.c), 1f / 3f);
						}
						else if (x3.y)
						{
							objectSubLaneInfo2.m_BezierCurve.d = math.transform(a, objectSubLaneInfo2.m_BezierCurve.d);
							objectSubLaneInfo2.m_BezierCurve.c = math.lerp(objectSubLaneInfo2.m_BezierCurve.c, math.transform(a, objectSubLaneInfo2.m_BezierCurve.c), 2f / 3f);
							objectSubLaneInfo2.m_BezierCurve.b = math.lerp(objectSubLaneInfo2.m_BezierCurve.b, math.transform(a, objectSubLaneInfo2.m_BezierCurve.b), 1f / 3f);
						}
					}
				}
				if (prefab.TryGet<ObjectSubNets>(out var component9) && component9.m_SubNets != null)
				{
					for (int num9 = 0; num9 < component9.m_SubNets.Length; num9++)
					{
						ObjectSubNetInfo objectSubNetInfo2 = component9.m_SubNets[num9];
						bool2 x4 = objectSubNetInfo2.m_ParentMesh == i;
						if (math.all(x4))
						{
							objectSubNetInfo2.m_BezierCurve.a = math.transform(a, objectSubNetInfo2.m_BezierCurve.a);
							objectSubNetInfo2.m_BezierCurve.b = math.transform(a, objectSubNetInfo2.m_BezierCurve.b);
							objectSubNetInfo2.m_BezierCurve.c = math.transform(a, objectSubNetInfo2.m_BezierCurve.c);
							objectSubNetInfo2.m_BezierCurve.d = math.transform(a, objectSubNetInfo2.m_BezierCurve.d);
						}
						else if (x4.x)
						{
							objectSubNetInfo2.m_BezierCurve.a = math.transform(a, objectSubNetInfo2.m_BezierCurve.a);
							objectSubNetInfo2.m_BezierCurve.b = math.lerp(objectSubNetInfo2.m_BezierCurve.b, math.transform(a, objectSubNetInfo2.m_BezierCurve.b), 2f / 3f);
							objectSubNetInfo2.m_BezierCurve.c = math.lerp(objectSubNetInfo2.m_BezierCurve.c, math.transform(a, objectSubNetInfo2.m_BezierCurve.c), 1f / 3f);
						}
						else if (x4.y)
						{
							objectSubNetInfo2.m_BezierCurve.d = math.transform(a, objectSubNetInfo2.m_BezierCurve.d);
							objectSubNetInfo2.m_BezierCurve.c = math.lerp(objectSubNetInfo2.m_BezierCurve.c, math.transform(a, objectSubNetInfo2.m_BezierCurve.c), 2f / 3f);
							objectSubNetInfo2.m_BezierCurve.b = math.lerp(objectSubNetInfo2.m_BezierCurve.b, math.transform(a, objectSubNetInfo2.m_BezierCurve.b), 1f / 3f);
						}
					}
				}
				if (prefab.TryGet<EffectSource>(out var component10) && component10.m_Effects != null)
				{
					for (int num10 = 0; num10 < component10.m_Effects.Count; num10++)
					{
						EffectSource.EffectSettings effectSettings2 = component10.m_Effects[num10];
						if (effectSettings2.m_ParentMesh == i)
						{
							effectSettings2.m_PositionOffset = math.transform(a, effectSettings2.m_PositionOffset);
							effectSettings2.m_Rotation = math.normalize(math.mul(a2, effectSettings2.m_Rotation));
						}
					}
				}
			}
			value.m_Position = objectMeshInfo.m_Position;
			value.m_Rotation = objectMeshInfo.m_Rotation;
			buffer[i] = value;
		}
	}
```

- `private OnAddComponent(System.Type type) : System.Void`  

```csharp
private void OnAddComponent(Type type)
	{
		CloseSubPanel();
		PrefabBase prefabBase = null;
		if (m_SelectedObject is PrefabBase prefabBase2)
		{
			prefabBase = prefabBase2;
		}
		else if (m_SelectedObject is ObjectMeshInfo objectMeshInfo)
		{
			prefabBase = objectMeshInfo.m_Mesh;
		}
		if (prefabBase != null && !prefabBase.Has(type))
		{
			prefabBase.AddComponent(type);
		}
	}
```

- `private OnColorVariationChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 variationSetIndex, System.Int32 colorIndex) : System.Void`  

```csharp
private void OnColorVariationChanged(Entity entity, RenderPrefabBase mesh, int variationSetIndex, int colorIndex)
	{
		base.World.GetExistingSystemManaged<MeshColorSystem>()?.SetOverride(entity, mesh, variationSetIndex);
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
		m_ObjectTool = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_AssetUploadPanel = base.World.GetOrCreateSystemManaged<EditorAssetUploadPanel>();
		m_MoveAction = InputManager.instance.FindAction("Editor", "Move Selected");
		m_CloneAction = InputManager.instance.FindAction("Editor", "Clone");
		m_AutoAlignAction = InputManager.instance.FindAction("Editor", "Auto Align");
		m_AutoConnectAction = InputManager.instance.FindAction("Editor", "Auto Connect");
		m_AlignXAction = InputManager.instance.FindAction("Editor", "Align X");
		m_AlignYAction = InputManager.instance.FindAction("Editor", "Align Y");
		m_AlignZAction = InputManager.instance.FindAction("Editor", "Align Z");
		m_InstanceFooter = new Button[1]
		{
			new Button
			{
				displayName = "Editor.LOCATE",
				action = OnLocate
			}
		};
		m_PrefabFooter = new Button[2]
		{
			new Button
			{
				displayName = "Editor.DUPLICATE_TEMPLATE",
				action = OnDuplicate,
				tooltip = "Editor.DUPLICATE_TEMPLATE_TOOLTIP"
			},
			new Button
			{
				displayName = "Editor.ADD_COMPONENT",
				tooltip = "Editor.ADD_COMPONENT_TOOLTIP",
				action = ShowAddComponentPicker,
				disabled = () => DisableSection(m_SelectedObject, m_ParentObject)
			}
		};
		m_MeshFooter = new Button[1]
		{
			new Button
			{
				displayName = "Editor.ADD_COMPONENT",
				tooltip = "Editor.ADD_COMPONENT_TOOLTIP",
				action = ShowAddComponentPicker,
				disabled = () => DisableSection(m_SelectedObject, m_ParentObject)
			}
		};
		m_CustomAssetFooter = new Button[1]
		{
			new Button
			{
				displayName = "Editor.SAVE_ASSET",
				tooltip = "Editor.SAVE_ASSET_TOOLTIP",
				action = ShowSaveAssetPanel,
				disabled = () => DisableSection(m_SelectedObject, m_ParentObject)
			}
		};
		m_Platform = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		PlatformManager.instance.onPlatformRegistered += delegate(IPlatformServiceIntegration psi)
		{
			if (psi is PdxSdkPlatform platform)
			{
				m_Platform = platform;
			}
		};
	}
```

- `private OnDuplicate() : System.Void`  

```csharp
private void OnDuplicate()
	{
		if (m_SelectedObject is PrefabBase template)
		{
			PrefabBase prefab = m_PrefabSystem.DuplicatePrefab(template);
			if (mode == Mode.Instance)
			{
				m_ToolSystem.ActivatePrefabTool(prefab);
			}
			else
			{
				SelectPrefab(prefab);
			}
		}
	}
```

- `private OnEmissiveChanged(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase mesh, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  

```csharp
private void OnEmissiveChanged(Entity entity, RenderPrefabBase mesh, int singleLightIndex, int multiLightIndex)
	{
		base.World.GetExistingSystemManaged<ProceduralUploadSystem>()?.SetOverride(entity, mesh, singleLightIndex, multiLightIndex);
	}
```

- `private OnLocate() : System.Void`  

```csharp
private void OnLocate()
	{
		int elementIndex = -1;
		if (m_CurrentSelectedEntity != Entity.Null && SelectedInfoUISystem.TryGetPosition(m_CurrentSelectedEntity, base.EntityManager, ref elementIndex, out var _, out var position, out var _, out var _))
		{
			if (m_CameraUpdateSystem.activeCameraController == m_CameraUpdateSystem.cinematicCameraController)
			{
				Vector3 rotation2 = m_CameraUpdateSystem.cinematicCameraController.rotation;
				rotation2.x = Mathf.Clamp(rotation2.x, 0f, 90f);
				m_CameraUpdateSystem.cinematicCameraController.rotation = rotation2;
				position = (Vector3)position + Quaternion.Euler(rotation2) * new Vector3(0f, 0f, -1000f);
				m_CameraUpdateSystem.cinematicCameraController.position = position;
			}
			else
			{
				m_CameraUpdateSystem.activeCameraController.pivot = position;
			}
		}
	}
```

- `private OnSaveAsset(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  

```csharp
private void OnSaveAsset(string name, Colossal.Hash128? overwriteGuid, Action<PrefabAsset> callback = null)
	{
		CloseSubPanel();
		if (overwriteGuid.HasValue)
		{
			GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new ConfirmationDialog(null, "Common.DIALOG_MESSAGE[OverwriteAsset]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int ret)
			{
				if (ret == 0)
				{
					PrefabAsset asset = AssetDatabase.global.GetAsset<PrefabAsset>(overwriteGuid.Value);
					SaveAsset(name, asset, callback);
				}
			});
		}
		else
		{
			SaveAsset(name, null, callback);
		}
	}
```

- `private OnShareAsset(Colossal.IO.AssetDatabase.PrefabAsset asset) : System.Void`  

```csharp
private void OnShareAsset(PrefabAsset asset)
	{
		m_AssetUploadPanel.Show(asset);
		base.activeSubPanel = m_AssetUploadPanel;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.activeSubPanel = null;
		m_MoveAction.enabled = false;
		m_CloneAction.enabled = false;
		m_AutoAlignAction.enabled = false;
		m_AutoAlignAction.enabled = false;
		m_AutoConnectAction.enabled = false;
		m_AlignXAction.enabled = false;
		m_AlignYAction.enabled = false;
		m_AlignZAction.enabled = false;
		OnColorVariationChanged(Entity.Null, null, -1, -1);
		OnEmissiveChanged(Entity.Null, null, -1, -1);
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		RefreshContent();
		HandleInput();
	}
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected override void OnValueChanged(IWidget widget)
	{
		base.OnValueChanged(widget);
		if (IsColorVariationField(widget, out var variationSetIndex, out var colorIndex, out var mesh))
		{
			OnColorVariationChanged(m_ToolSystem.selected, mesh, variationSetIndex, colorIndex);
		}
		if (IsEmissiveField(widget, out var singleLightIndex, out var multiLightIndex, out mesh))
		{
			OnEmissiveChanged(m_ToolSystem.selected, mesh, singleLightIndex, multiLightIndex);
		}
		UpdateParent(moveSubObjects: true);
	}
```

- `private RefreshContent() : System.Void`  

```csharp
private void RefreshContent()
	{
		RefreshTitle();
		RefreshSections();
	}
```

- `private RefreshFooter(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> panelChildren) : System.Void`  

```csharp
private void RefreshFooter(IList<IWidget> panelChildren)
	{
		if (m_SelectedObject is ObjectMeshInfo)
		{
			panelChildren.Add(ButtonRow.WithChildren(m_MeshFooter));
			return;
		}
		List<Button> list = new List<Button>();
		if (mode == Mode.Instance)
		{
			list.AddRange(m_InstanceFooter);
		}
		list.AddRange(m_PrefabFooter);
		panelChildren.Add(ButtonRow.WithChildren(list.ToArray()));
		if (m_SelectedObject is PrefabBase { builtin: false })
		{
			panelChildren.Add(ButtonRow.WithChildren(m_CustomAssetFooter));
		}
	}
```

- `private RefreshSections() : System.Void`  

```csharp
private void RefreshSections()
	{
		if (m_SectionObjects.SequenceEqual(GetSectionObjects()))
		{
			return;
		}
		m_SectionObjects.Clear();
		m_SectionObjects.AddRange(GetSectionObjects());
		List<IWidget> list = new List<IWidget>(m_SectionObjects.Count);
		for (int i = 0; i < m_SectionObjects.Count; i++)
		{
			object obj = m_SectionObjects[i];
			string name = obj.GetType().Name;
			List<IWidget> widgets = new List<IWidget>(m_EditorGenerator.BuildMembers(new ObjectAccessor<object>(obj), 0, name).ToArray());
			PrefabBase prefabBase = obj as PrefabBase;
			if (prefabBase != null && !(prefabBase is RenderPrefabBase))
			{
				BuildLocalizationFields(prefabBase, widgets);
			}
			EditorSection editorSection = new EditorSection
			{
				path = new PathSegment(name),
				displayName = LocalizedString.Value(WidgetReflectionUtils.NicifyVariableName(name)),
				tooltip = name,
				expanded = true,
				children = widgets
			};
			if (DisableSection(obj, m_ParentObject))
			{
				DisableAllFields(editorSection);
			}
			if (prefabBase != null)
			{
				editorSection.primary = true;
				editorSection.color = EditorSection.kPrefabColor;
				editorSection.active = GetActiveAccessor(prefabBase);
			}
			else
			{
				ComponentBase component = obj as ComponentBase;
				if ((object)component != null)
				{
					editorSection.onDelete = delegate
					{
						ApplyPrefabsSystem.RemoveComponent(component.prefab, component.GetType());
					};
					editorSection.active = GetActiveAccessor(component);
				}
			}
			list.Add(editorSection);
		}
		List<IWidget> list2 = new List<IWidget>
		{
			Scrollable.WithChildren(list.ToArray()),
			new ModdingBetaBanner()
		};
		RefreshFooter(list2);
		children = list2.ToArray();
	}
```

- `private RefreshTitle() : System.Void`  

```csharp
private void RefreshTitle()
	{
		LocalizedString objectName = GetObjectName(m_SelectedObject);
		LocalizedString objectName2 = GetObjectName(m_ParentObject);
		if (!objectName.Equals(m_SelectedName) || !objectName2.Equals(m_ParentName))
		{
			m_SelectedName = objectName;
			m_ParentName = objectName2;
			if (m_ParentObject != m_SelectedObject)
			{
				title = objectName2.value + " > " + objectName.value;
			}
			else
			{
				title = objectName;
			}
		}
	}
```

- `private SaveAsset(System.String name, Colossal.IO.AssetDatabase.PrefabAsset existing = null, System.Action<Colossal.IO.AssetDatabase.PrefabAsset> callback = null) : System.Void`  

```csharp
private void SaveAsset(string name, PrefabAsset existing = null, Action<PrefabAsset> callback = null)
	{
		PrefabBase prefabBase = m_SelectedObject as PrefabBase;
		if (prefabBase.asset != null && (existing == null || existing != prefabBase.asset))
		{
			prefabBase = DuplicatePrefab(prefabBase);
			SelectPrefab(prefabBase);
		}
		PrefabAsset prefabAsset = existing;
		if (existing != null)
		{
			existing.SetData(prefabBase);
		}
		else
		{
			prefabAsset = AssetDatabase.user.AddAsset(AssetDataPath.Create("StreamingData~/" + name, name ?? ""), prefabBase);
		}
		SaveIcons(prefabBase, name);
		prefabAsset.Save();
		if (!IsBuiltinAsset(prefabAsset))
		{
			SaveLocalization(prefabBase, name);
		}
		PlatformManager.instance.UnlockAchievement(Game.Achievements.Achievements.IMadeThis);
		callback?.Invoke(prefabAsset);
	}
```

- `private SaveIcons(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  

```csharp
private void SaveIcons(PrefabBase prefab, string name)
	{
		Dictionary<ImageAsset, ImageAsset> dictionary = new Dictionary<ImageAsset, ImageAsset>();
		foreach (EditorPrefabUtils.IconInfo icon in EditorPrefabUtils.GetIcons(prefab))
		{
			if (!IsBuiltinAsset(icon.m_Asset))
			{
				if (!dictionary.ContainsKey(icon.m_Asset))
				{
					ImageAsset value = icon.m_Asset.Save(ImageAsset.FileFormat.PNG, AssetDataPath.Create(prefab.asset.subPath, icon.m_Asset.name ?? ""), prefab.asset.database);
					dictionary.Add(icon.m_Asset, value);
				}
				icon.m_Field.SetValue(icon.m_Component, dictionary[icon.m_Asset].ToGlobalUri());
			}
		}
	}
```

- `private SaveLocalization(Game.Prefabs.PrefabBase prefab, System.String name) : System.Void`  

```csharp
private void SaveLocalization(PrefabBase prefab, string name)
	{
		if (!m_WipLocalization.TryGetValue(prefab, out var value))
		{
			return;
		}
		List<LocaleAsset> list = new List<LocaleAsset>();
		list.AddRange(EditorPrefabUtils.GetLocaleAssets(prefab));
		foreach (LocaleAsset item in list)
		{
			AssetDatabase.user.DeleteAsset(item);
		}
		LocalizationManager localizationManager = GameManager.instance.localizationManager;
		Dictionary<string, LocaleData> dictionary = new Dictionary<string, LocaleData>();
		value.m_NameLocalization.BuildLocaleData("Assets.NAME[" + prefab.name + "]", dictionary, prefab.name);
		value.m_DescriptionLocalization.BuildLocaleData("Assets.DESCRIPTION[" + prefab.name + "]", dictionary);
		if (prefab is UIAssetMenuPrefab || prefab is ServicePrefab)
		{
			value.m_NameLocalization.BuildLocaleData("Services.NAME[" + prefab.name + "]", dictionary, prefab.name);
			value.m_DescriptionLocalization.BuildLocaleData("Services.DESCRIPTION[" + prefab.name + "]", dictionary);
		}
		if (prefab is UIAssetCategoryPrefab)
		{
			value.m_NameLocalization.BuildLocaleData("SubServices.NAME[" + prefab.name + "]", dictionary, prefab.name);
			value.m_DescriptionLocalization.BuildLocaleData("Assets.SUB_SERVICE_DESCRIPTION[" + prefab.name + "]", dictionary);
		}
		if (prefab.Has<ServiceUpgrade>())
		{
			value.m_NameLocalization.BuildLocaleData("Assets.UPGRADE_NAME[" + prefab.name + "]", dictionary, prefab.name);
			value.m_DescriptionLocalization.BuildLocaleData("Assets.UPGRADE_DESCRIPTION[" + prefab.name + "]", dictionary);
		}
		foreach (LocaleData value2 in dictionary.Values)
		{
			LocaleAsset localeAsset = prefab.asset.database.AddAsset<LocaleAsset>(AssetDataPath.Create(prefab.asset.subPath, name + "_" + value2.localeId));
			localeAsset.SetData(value2, localizationManager.LocaleIdToSystemLanguage(value2.localeId), GameManager.instance.localizationManager.GetLocalizedName(value2.localeId));
			localeAsset.Save();
		}
	}
```

- `public SelectEntity(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public bool SelectEntity(Entity entity)
	{
		if (entity == m_CurrentSelectedEntity)
		{
			return entity != Entity.Null;
		}
		object obj = m_SelectedObject;
		object obj2 = m_ParentObject;
		base.activeSubPanel = null;
		if (SelectObjectForEntity(entity))
		{
			m_CurrentSelectedEntity = entity;
			if (obj2 == m_ParentObject && obj is ObjectSubObjectInfo lastSubObject && m_SelectedObject is ObjectSubObjectInfo currentSubObject)
			{
				m_LastSubObject = lastSubObject;
				m_CurrentSubObject = currentSubObject;
			}
			else
			{
				m_LastSubObject = null;
				m_CurrentSubObject = null;
			}
			return true;
		}
		m_CurrentSelectedEntity = Entity.Null;
		m_LastSubObject = null;
		m_CurrentSubObject = null;
		return false;
	}
```

- `private SelectInUnityEditor(UnityEngine.Object obj) : System.Void`  

```csharp
private void SelectInUnityEditor(UnityEngine.Object obj)
	{
	}
```

- `public SelectMesh(Unity.Entities.Entity entity, System.Int32 meshIndex) : System.Boolean`  

```csharp
public bool SelectMesh(Entity entity, int meshIndex)
	{
		if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component.m_Prefab, out var prefab) && base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<SubMesh> buffer) && m_PrefabSystem.TryGetPrefab<PrefabBase>(buffer[meshIndex].m_SubMesh, out var prefab2))
		{
			base.activeSubPanel = null;
			m_SelectedObject = prefab2;
			m_ParentObject = prefab;
			m_CurrentSelectedEntity = Entity.Null;
			m_LastSubObject = null;
			m_CurrentSubObject = null;
			if (prefab is ObjectGeometryPrefab prefab3 && FindObjectMeshInfo(prefab3, prefab2, out var info))
			{
				m_SelectedObject = info;
			}
			return true;
		}
		return false;
	}
```

- `private SelectObjectForEntity(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
private bool SelectObjectForEntity(Entity entity)
	{
		if (entity == Entity.Null || !base.EntityManager.HasComponent<Game.Objects.Object>(entity) || base.EntityManager.HasComponent<Secondary>(entity) || !base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			m_SelectedObject = null;
			m_ParentObject = null;
			return false;
		}
		if (!m_PrefabSystem.TryGetPrefab<PrefabBase>(component, out var prefab))
		{
			m_SelectedObject = null;
			m_ParentObject = null;
			return false;
		}
		m_SelectedObject = prefab;
		m_ParentObject = prefab;
		Game.Tools.EditorContainer component9;
		if (base.EntityManager.TryGetComponent<Owner>(entity, out var component2) && base.EntityManager.TryGetComponent<PrefabRef>(component2.m_Owner, out var component3))
		{
			int num = -1;
			if (base.EntityManager.TryGetComponent<LocalTransformCache>(entity, out var component4))
			{
				num = component4.m_PrefabSubIndex;
			}
			if (num == -1)
			{
				return false;
			}
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(component3);
			ObjectSubObjects component8;
			if (base.EntityManager.TryGetComponent<Game.Tools.EditorContainer>(entity, out var component5))
			{
				Game.Prefabs.ActivityLocation component7;
				if (base.EntityManager.HasComponent<EffectData>(component5.m_Prefab) && prefab2.TryGet<EffectSource>(out var component6) && component6.m_Effects != null && component6.m_Effects.Count > num)
				{
					prefab = m_PrefabSystem.GetPrefab<PrefabBase>(component5.m_Prefab);
					EffectSource.EffectSettings effectSettings = component6.m_Effects[num];
					if (effectSettings != null && effectSettings.m_Effect == prefab)
					{
						m_SelectedObject = effectSettings;
						m_ParentObject = prefab2;
					}
				}
				else if (base.EntityManager.HasComponent<ActivityLocationData>(component5.m_Prefab) && prefab2.TryGet<Game.Prefabs.ActivityLocation>(out component7) && component7.m_Locations != null && component7.m_Locations.Length > num)
				{
					prefab = m_PrefabSystem.GetPrefab<PrefabBase>(component5.m_Prefab);
					Game.Prefabs.ActivityLocation.LocationInfo locationInfo = component7.m_Locations[num];
					if (locationInfo != null && locationInfo.m_Activity == prefab)
					{
						m_SelectedObject = locationInfo;
						m_ParentObject = prefab2;
					}
				}
			}
			else if (prefab2.TryGet<ObjectSubObjects>(out component8) && component8.m_SubObjects != null && component8.m_SubObjects.Length > num)
			{
				ObjectSubObjectInfo objectSubObjectInfo = component8.m_SubObjects[num];
				if (objectSubObjectInfo != null && objectSubObjectInfo.m_Object == prefab)
				{
					m_SelectedObject = objectSubObjectInfo;
					m_ParentObject = prefab2;
				}
			}
		}
		else if (base.EntityManager.TryGetComponent<Game.Tools.EditorContainer>(entity, out component9) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component9.m_Prefab, out prefab))
		{
			m_SelectedObject = prefab;
			m_ParentObject = prefab;
		}
		return true;
	}
```

- `public SelectPrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public void SelectPrefab(PrefabBase prefab)
	{
		m_CurrentSelectedEntity = Entity.Null;
		m_LastSubObject = null;
		m_CurrentSubObject = null;
		m_SelectedObject = prefab;
		m_ParentObject = prefab;
	}
```

- `private ShowAddComponentPicker() : System.Void`  

```csharp
private void ShowAddComponentPicker()
	{
		base.activeSubPanel = new TypePickerPanel(new LocalizedString("Editor.ADD_COMPONENT_NAMED", null, new Dictionary<string, ILocElement> { { "NAME", m_SelectedName } }), "Editor.COMPONENT_TYPES", GetComponentTypeItems().ToList(), OnAddComponent, base.CloseSubPanel);
	}
```

- `private ShowSaveAssetPanel() : System.Void`  

```csharp
private void ShowSaveAssetPanel()
	{
		Colossal.Hash128? initialSelected = ((!(m_SelectedObject is PrefabBase prefabBase)) ? ((Identifier?)null) : prefabBase.asset?.id);
		base.activeSubPanel = new SaveAssetPanel("Editor.SAVE_ASSET", GetCustomAssets(), initialSelected, delegate(string name, Colossal.Hash128? overwriteGuid)
		{
			OnSaveAsset(name, overwriteGuid);
		}, base.CloseSubPanel);
	}
```

- `private ShowShareAssetPanel() : System.Void`  

```csharp
private void ShowShareAssetPanel()
	{
		Colossal.Hash128? initialSelected = ((!(m_SelectedObject is PrefabBase prefabBase)) ? ((Identifier?)null) : prefabBase.asset?.id);
		base.activeSubPanel = new SaveAssetPanel("Editor.SAVE_SHARE", GetCustomAssets(), initialSelected, delegate(string name, Colossal.Hash128? overwriteGuid)
		{
			OnSaveAsset(name, overwriteGuid, OnShareAsset);
		}, base.CloseSubPanel, "Editor.SAVE_SHARE");
	}
```

- `public ShowThumbnailPicker(Game.UI.Editor.LoadAssetPanel+LoadCallback callback) : System.Void`  

```csharp
public void ShowThumbnailPicker(LoadAssetPanel.LoadCallback callback)
	{
		base.activeSubPanel = new LoadAssetPanel("Editor.THUMBNAIL", EditorPrefabUtils.GetUserImages(), delegate(Colossal.Hash128 hash)
		{
			callback(hash);
			CloseSubPanel();
		}, base.CloseSubPanel);
	}
```

- `private TryGetAssetItem(Colossal.IO.AssetDatabase.PrefabAsset asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  

```csharp
private bool TryGetAssetItem(PrefabAsset asset, out AssetItem item)
	{
		try
		{
			PrefabBase prefabBase = asset.Load() as PrefabBase;
			if (prefabBase is RenderPrefabBase)
			{
				item = null;
				return false;
			}
			SourceMeta meta = asset.GetMeta();
			item = new AssetItem
			{
				guid = asset.id,
				fileName = meta.fileName,
				displayName = meta.fileName,
				image = ((prefabBase != null) ? ImageSystem.GetThumbnail(prefabBase) : null),
				badge = meta.remoteStorageSourceName
			};
			return true;
		}
		catch (Exception exception)
		{
			base.log.Error(exception);
			item = null;
		}
		item = null;
		return false;
	}
```

- `private UpdateParent(System.Boolean moveSubObjects) : System.Void`  

```csharp
private void UpdateParent(bool moveSubObjects)
	{
		if (m_SelectedObject is ObjectMeshInfo { m_Mesh: var mesh })
		{
			m_PrefabSystem.UpdatePrefab(mesh);
			mesh.asset?.MarkDirty();
		}
		if (m_ParentObject is PrefabBase prefabBase)
		{
			if (moveSubObjects)
			{
				MoveSubObjects(prefabBase);
			}
			m_PrefabSystem.UpdatePrefab(prefabBase);
			prefabBase.asset?.MarkDirty();
		}
	}
```


## Nested types

- `Game.UI.Editor.InspectorPanelSystem+Mode`  
- `Game.UI.Editor.InspectorPanelSystem+LocalizationFields`  
- `Game.UI.Editor.InspectorPanelSystem+<>c`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass45_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass49_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass53_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass78_0`  
- `Game.UI.Editor.InspectorPanelSystem+<>c__DisplayClass83_0`  
- `Game.UI.Editor.InspectorPanelSystem+<GetComponentTypeItems>d__53`  
- `Game.UI.Editor.InspectorPanelSystem+<GetCustomAssets>d__76`  
- `Game.UI.Editor.InspectorPanelSystem+<GetSectionObjects>d__48`  

