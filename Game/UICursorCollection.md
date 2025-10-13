# Game.UICursorCollection

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UICursorCollection : UnityEngine.ScriptableObject
{
    public Game.UICursorCollection+CursorInfo m_Pointer;
    public Game.UICursorCollection+CursorInfo m_Text;
    public Game.UICursorCollection+CursorInfo m_Move;
    public Game.UICursorCollection+NamedCursorInfo[] m_NamedCursors;
    private System.Collections.Generic.Dictionary<System.String, Game.UICursorCollection+CursorInfo> m_NamedCursorsDict;

    public UICursorCollection();

    private System.Void OnEnable();
    private System.Void RefreshNamedCursorsDict();
    public static System.Void ResetCursor();
    public System.Void SetCursor(cohtml.Net.Cursors cursor);
    public System.Void SetCursor(System.String cursorName);
}
```


## Fields

- `public Game.UICursorCollection+CursorInfo m_Pointer`  

```csharp
public Game.UICursorCollection+CursorInfo m_Pointer;
```

- `public Game.UICursorCollection+CursorInfo m_Text`  

```csharp
public Game.UICursorCollection+CursorInfo m_Text;
```

- `public Game.UICursorCollection+CursorInfo m_Move`  

```csharp
public Game.UICursorCollection+CursorInfo m_Move;
```

- `public Game.UICursorCollection+NamedCursorInfo[] m_NamedCursors`  

```csharp
public Game.UICursorCollection+NamedCursorInfo[] m_NamedCursors;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UICursorCollection+CursorInfo> m_NamedCursorsDict`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UICursorCollection+CursorInfo> m_NamedCursorsDict;
```


## Constructors

- `public UICursorCollection()`  

```csharp
public UICursorCollection();
```


## Methods

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `private RefreshNamedCursorsDict() : System.Void`  

```csharp
private System.Void RefreshNamedCursorsDict();
```

- `public static ResetCursor() : System.Void`  

```csharp
public static System.Void ResetCursor();
```

- `public SetCursor(cohtml.Net.Cursors cursor) : System.Void`  

```csharp
public System.Void SetCursor(cohtml.Net.Cursors cursor);
```

- `public SetCursor(System.String cursorName) : System.Void`  

```csharp
public System.Void SetCursor(System.String cursorName);
```


## Nested types

- `Game.UICursorCollection+CursorInfo`  
- `Game.UICursorCollection+NamedCursorInfo`  

