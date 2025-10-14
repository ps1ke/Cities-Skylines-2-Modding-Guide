# Game.UICursorCollection

**Assembly:**  
**Namespace:** Game

**Type:** Class

**Base:** UnityEngine.ScriptableObject

**Summary:** UICursorCollection is a ScriptableObject that centralizes cursor textures and hotspot data for Cities: Skylines 2 UI. It provides built-in cursors (pointer, text, move) and supports arbitrary named cursors (with names exposed as assets). It includes methods to set the current OS cursor by enum or by name, reset it to default, and to initialize a lookup dictionary for fast name-based access. The asset is creatable from the Unity editor via the CreateAssetMenu attribute ("Colossal/UI/UICursorCollection").

---

## Fields

- `public UICursorCollection.CursorInfo m_Pointer`  
Holds the texture and hotspot for the default pointer cursor.

- `public UICursorCollection.CursorInfo m_Text`  
Holds the texture and hotspot for the text (I-beam) cursor.

- `public UICursorCollection.CursorInfo m_Move`  
Holds the texture and hotspot for the move cursor.

- `public UICursorCollection.NamedCursorInfo[] m_NamedCursors`  
Array of named cursors (each contains a name, texture and hotspot). Exposed in the inspector to add custom cursors.

- `private System.Collections.Generic.Dictionary<string, UICursorCollection.CursorInfo> m_NamedCursorsDict`  
Runtime dictionary mapping normalized cursor names (prefixed with "cursor://") to CursorInfo instances for quick lookup by string.

Additionally, the nested classes define these fields:

- CursorInfo.m_Texture (Texture2D) — texture used for the cursor.
- CursorInfo.m_Hotspot (Vector2) — hotspot offset for the texture.
- NamedCursorInfo.m_Name (string) — identifier for a named cursor.

## Properties

- None (this class exposes fields and methods; no C# properties are declared).

## Constructors

- `public UICursorCollection()`  
No explicit constructor is declared in source; the default parameterless constructor provided by Unity/Mono is used. Initialization of runtime structures is performed in OnEnable().

## Methods

- `private void OnEnable()`  
Called by Unity when the ScriptableObject is loaded (e.g., when entering play mode or loading the asset). Ensures the m_NamedCursors array is non-null, creates the runtime dictionary, and populates it via RefreshNamedCursorsDict().

```csharp
private void OnEnable()
{
    if (m_NamedCursors == null)
    {
        m_NamedCursors = new NamedCursorInfo[0];
    }
    m_NamedCursorsDict = new Dictionary<string, CursorInfo>();
    RefreshNamedCursorsDict();
}
```

- `public void SetCursor(Cursors cursor)`  
Switches the OS cursor based on a Cursors enum value. Built-in enum cases handled:
  - Cursors.Pointer → applies m_Pointer
  - Cursors.Text → applies m_Text
  - Cursors.Move → applies m_Move
  - default → calls ResetCursor()
Note: the Cursors enum is defined elsewhere in the codebase.

- `public void SetCursor(string cursorName)`  
Looks up a named cursor using the runtime dictionary and applies it if found. If not found, resets the cursor to default. Named entries use the key format "cursor://<name>" (see RefreshNamedCursorsDict()).

- `public static void ResetCursor()`  
Sets the system cursor back to default (null texture) using Cursor.SetCursor(null, Vector2.zero, CursorMode.Auto).

- `private void RefreshNamedCursorsDict()`  
Rebuilds the m_NamedCursorsDict from the m_NamedCursors array. Each entry is inserted with key "cursor://{m_Name}" so callers of SetCursor(string) should use that convention (or pass names already formatted that way).

- `public void Apply()` (in nested CursorInfo)  
Applies this CursorInfo's texture and hotspot to the system cursor using Cursor.SetCursor(m_Texture, m_Hotspot, CursorMode.Auto).

Notes and usage tips:
- Create an instance in the editor via Assets → Create → Colossal → UI → UICursorCollection (as defined by the CreateAssetMenu attribute).
- Populate m_Pointer/m_Text/m_Move for common cursors, and add entries to m_NamedCursors for any custom cursors you need to reference by string.
- When adding named cursors, use unique m_Name values — the lookup key is constructed as "cursor://<m_Name>" internally.
- Cursor textures should be imported as Texture Type: Cursor or have read/write enabled and an appropriate size; set hotspot pixels appropriately in m_Hotspot.