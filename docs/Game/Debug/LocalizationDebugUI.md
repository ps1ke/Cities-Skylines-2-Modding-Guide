# Game.Debug.LocalizationDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class LocalizationDebugUI : System.IDisposable
{
    private System.Int32 m_SelectedContentId;
    private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings;

    public LocalizationDebugUI();

    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildLocalizationDebugUI(Unity.Entities.World world);
    public System.Void Dispose();
    private System.Void InitLocalization(System.Int32 contentId);
    private System.Void Rebuild();
}
```


## Fields

- `private System.Int32 m_SelectedContentId`  

```csharp
private System.Int32 m_SelectedContentId;
```

- `private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings`  

```csharp
private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings;
```


## Constructors

- `public LocalizationDebugUI()`  

```csharp
public LocalizationDebugUI();
```


## Methods

- `private BuildLocalizationDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildLocalizationDebugUI(Unity.Entities.World world);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private InitLocalization(System.Int32 contentId) : System.Void`  

```csharp
private System.Void InitLocalization(System.Int32 contentId);
```

- `private Rebuild() : System.Void`  

```csharp
private System.Void Rebuild();
```


## Nested types

- `Game.Debug.LocalizationDebugUI+<>c`  
- `Game.Debug.LocalizationDebugUI+<>c__DisplayClass6_0`  

