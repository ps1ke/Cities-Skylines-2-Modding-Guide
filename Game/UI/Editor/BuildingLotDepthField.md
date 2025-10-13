# Game.UI.Editor.BuildingLotDepthField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.BuildingLotFieldBase`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class BuildingLotDepthField : Game.UI.Editor.BuildingLotFieldBase, Game.UI.Widgets.IFieldBuilderFactory
{
    public BuildingLotDepthField();

    public virtual Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public BuildingLotDepthField()`  

```csharp
public BuildingLotDepthField();
```


## Methods

- `public virtual TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public virtual Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


