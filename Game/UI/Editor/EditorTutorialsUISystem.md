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
public EditorTutorialsUISystem();
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
private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual CompleteActiveTutorialPhase() : System.Void`  

```csharp
protected virtual System.Void CompleteActiveTutorialPhase();
```

- `private CompleteEditorIntro(System.Boolean value) : System.Void`  

```csharp
private System.Void CompleteEditorIntro(System.Boolean value);
```

- `private GetSortedCategories(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Collections.Allocator allocator);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ToggleTutorials() : System.Void`  

```csharp
private System.Void ToggleTutorials();
```


