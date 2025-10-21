# Game.ArtPipeline.Preview.ColorPresetList

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ColorPresetList
{
    private System.String <ListId>k__BackingField;
    private System.Collections.Generic.List<UnityEngine.Color> <Colors>k__BackingField;
    private UnityEngine.Events.UnityAction<System.Collections.Generic.List<UnityEngine.Color>> OnColorsUpdated;

    public System.String ListId { get; private set; }
    public System.Collections.Generic.List<UnityEngine.Color> Colors { get; private set; }

    public ColorPresetList(System.String listId, System.Collections.Generic.List<UnityEngine.Color> colors);

    public System.Void AddColor(UnityEngine.Color color);
    public System.Void UpdateList(System.Collections.Generic.IEnumerable<UnityEngine.Color> colors);
}
```


## Fields

- `private System.String <ListId>k__BackingField`  

```csharp
private System.String <ListId>k__BackingField;
```

- `private System.Collections.Generic.List<UnityEngine.Color> <Colors>k__BackingField`  

```csharp
private System.Collections.Generic.List<UnityEngine.Color> <Colors>k__BackingField;
```

- `private UnityEngine.Events.UnityAction<System.Collections.Generic.List<UnityEngine.Color>> OnColorsUpdated`  

```csharp
private UnityEngine.Events.UnityAction<System.Collections.Generic.List<UnityEngine.Color>> OnColorsUpdated;
```


## Properties

- `public System.String ListId { get; private set }`  

```csharp
public System.String ListId { get; private set; }
```

- `public System.Collections.Generic.List<UnityEngine.Color> Colors { get; private set }`  

```csharp
public System.Collections.Generic.List<UnityEngine.Color> Colors { get; private set; }
```


## Constructors

- `public ColorPresetList(System.String listId, System.Collections.Generic.List<UnityEngine.Color> colors = null)`  

```csharp
public ColorPresetList(System.String listId, System.Collections.Generic.List<UnityEngine.Color> colors);
```


## Methods

- `public AddColor(UnityEngine.Color color) : System.Void`  

```csharp
public System.Void AddColor(UnityEngine.Color color);
```

- `public UpdateList(System.Collections.Generic.IEnumerable<UnityEngine.Color> colors) : System.Void`  

```csharp
public System.Void UpdateList(System.Collections.Generic.IEnumerable<UnityEngine.Color> colors);
```


## Events

- `OnColorsUpdated` : `UnityEngine.Events.UnityAction<System.Collections.Generic.List<UnityEngine.Color>>`  

```csharp
public event UnityEngine.Events.UnityAction<System.Collections.Generic.List<UnityEngine.Color>> OnColorsUpdated;
```


