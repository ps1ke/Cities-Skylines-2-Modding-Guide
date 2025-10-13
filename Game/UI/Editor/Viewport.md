# Game.UI.Editor.EditorHierarchyUISystem+Viewport

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class Viewport : Colossal.UI.Binding.IJsonWritable
{
    public System.Int32 startIndex;
    public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+ViewportItem> items;

    public Viewport();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Int32 startIndex`  

```csharp
public System.Int32 startIndex;
```

- `public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+ViewportItem> items`  

```csharp
public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+ViewportItem> items;
```


## Constructors

- `public Viewport()`  

```csharp
public Viewport();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


