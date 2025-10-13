# Game.UI.Editor.EditorTutorialsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.InGame.TutorialsUISystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorTutorialsUISystem : Game.UI.InGame.TutorialsUISystem
{
    private Unity.Entities.EntityQuery m_TutorialCategoryQuery;
    private System.Boolean m_EditorTutorialsDisabled;
    private static const System.String kEditorGroup;

    public EditorTutorialsUISystem();

    private System.Boolean <OnCreate>b__3_0();
    private System.Boolean <OnCreate>b__3_1();
    private System.Boolean <OnCreate>b__3_2();
    private System.Boolean <OnCreate>b__3_3();
    private System.Boolean <OnCreate>b__3_4();
    private Unity.Entities.Entity <OnCreate>b__3_5();
    private Unity.Entities.Entity <OnCreate>b__3_6();
    private System.Void <OnCreate>b__3_7(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__3_8(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void CompleteActiveTutorialPhase();
    private System.Void CompleteEditorIntro(System.Boolean value);
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Collections.Allocator allocator);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void ToggleTutorials();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TutorialCategoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialCategoryQuery;
```

- `private System.Boolean m_EditorTutorialsDisabled`  

```csharp
private System.Boolean m_EditorTutorialsDisabled;
```

- `private static const System.String kEditorGroup`  

```csharp
private static const System.String kEditorGroup;
```


## Constructors

- `public EditorTutorialsUISystem()`  

```csharp
[Preserve]
	public EditorTutorialsUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__3_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__3_0();
```

- `private <OnCreate>b__3_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__3_1();
```

- `private <OnCreate>b__3_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__3_2();
```

- `private <OnCreate>b__3_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__3_3();
```

- `private <OnCreate>b__3_4() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__3_4();
```

- `private <OnCreate>b__3_5() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__3_5();
```

- `private <OnCreate>b__3_6() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__3_6();
```

- `private <OnCreate>b__3_7(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__3_7(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__3_8(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__3_8(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindCategories(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedCategories = GetSortedCategories(Allocator.Temp);
		writer.ArrayBegin(sortedCategories.Length);
		for (int i = 0; i < sortedCategories.Length; i++)
		{
			UIObjectInfo uIObjectInfo = sortedCategories[i];
			UITutorialGroupPrefab prefab = m_PrefabSystem.GetPrefab<UITutorialGroupPrefab>(uIObjectInfo.entity);
			writer.TypeBegin(TypeNames.kAdvisorCategory);
			writer.PropertyName("entity");
			writer.Write(uIObjectInfo.entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("shown");
			writer.Write(base.EntityManager.HasComponent<TutorialShown>(uIObjectInfo.entity));
			writer.PropertyName("locked");
			writer.Write(value: false);
			writer.PropertyName("children");
			BindTutorialGroup(writer, uIObjectInfo.entity);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		sortedCategories.Dispose();
	}
```

- `protected virtual CompleteActiveTutorialPhase() : System.Void`  

```csharp
protected override void CompleteActiveTutorialPhase()
	{
		if (GameManager.instance.gameMode.IsEditor())
		{
			m_TutorialSystem.CompleteCurrentTutorialPhase();
		}
	}
```

- `private CompleteEditorIntro(System.Boolean value) : System.Void`  

```csharp
private void CompleteEditorIntro(bool value)
	{
		m_TutorialSystem.mode = TutorialMode.Default;
		m_TutorialSystem.tutorialEnabled = value;
	}
```

- `private GetSortedCategories(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private NativeList<UIObjectInfo> GetSortedCategories(Allocator allocator)
	{
		NativeArray<Entity> nativeArray = m_TutorialCategoryQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<UIObjectData> nativeArray2 = m_TutorialCategoryQuery.ToComponentDataArray<UIObjectData>(Allocator.TempJob);
		NativeList<UIObjectInfo> nativeList = new NativeList<UIObjectInfo>(allocator);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray2[i].m_Group == Entity.Null)
			{
				nativeList.Add(new UIObjectInfo(nativeArray[i], nativeArray2[i].m_Priority));
			}
		}
		nativeList.Sort();
		nativeArray.Dispose();
		nativeArray2.Dispose();
		return nativeList;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TutorialSystem = base.World.GetOrCreateSystemManaged<EditorTutorialSystem>();
		m_TutorialCategoryQuery = GetEntityQuery(ComponentType.ReadOnly<UIEditorTutorialGroupData>(), ComponentType.ReadOnly<UIObjectData>());
		m_UnlockQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>(), ComponentType.ReadOnly<EditorTutorial>());
		m_EditorTutorialsDisabled = true;
		AddUpdateBinding(new GetterValueBinding<bool>("editorTutorials", "tutorialsDisabled", () => m_EditorTutorialsDisabled));
		AddUpdateBinding(new GetterValueBinding<bool>("editorTutorials", "tutorialsEnabled", () => m_TutorialSystem.tutorialEnabled));
		AddUpdateBinding(new GetterValueBinding<bool>("editorTutorials", "introActive", () => m_TutorialSystem.mode == TutorialMode.Intro));
		AddUpdateBinding(new GetterValueBinding<bool>("editorTutorials", "listIntroActive", () => m_TutorialSystem.mode == TutorialMode.ListIntro));
		AddUpdateBinding(new GetterValueBinding<bool>("editorTutorials", "listOutroActive", () => m_TutorialSystem.mode == TutorialMode.ListOutro));
		AddUpdateBinding(new GetterValueBinding<Entity>("editorTutorials", "next", () => m_TutorialSystem.nextListTutorial));
		AddUpdateBinding(new GetterValueBinding<Entity>("editorTutorials", "advisorPanelVisible", () => m_TutorialSystem.nextListTutorial));
		AddBinding(m_TutorialCategoriesBinding = new RawValueBinding("editorTutorials", "categories", BindCategories));
		AddBinding(m_ActiveTutorialBinding = new RawValueBinding("editorTutorials", "activeTutorial", delegate(IJsonWriter writer)
		{
			BindTutorial(writer, m_TutorialSystem.activeTutorial);
		}));
		AddBinding(m_ActiveTutorialPhaseBinding = new RawValueBinding("editorTutorials", "activeTutorialPhase", delegate(IJsonWriter writer)
		{
			BindTutorialPhase(writer, m_TutorialSystem.activeTutorialPhase);
		}));
		AddBinding(m_ActiveTutorialListBinding = new RawValueBinding("editorTutorials", "activeList", base.BindActiveTutorialList));
		AddBinding(new TriggerBinding<bool>("editorTutorials", "completeListIntro", CompleteEditorIntro));
		AddBinding(new TriggerBinding("editorTutorials", "toggleTutorials", ToggleTutorials));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!GameManager.instance.gameMode.IsGame())
		{
			base.OnUpdate();
		}
	}
```

- `private ToggleTutorials() : System.Void`  

```csharp
private void ToggleTutorials()
	{
		m_TutorialSystem.tutorialEnabled = !m_TutorialSystem.tutorialEnabled;
		if (m_TutorialSystem.tutorialEnabled)
		{
			World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<EditorTutorialSystem>().OnResetTutorials();
		}
	}
```


