# Game.UI.Editor.Widgets.ItemPickerPopup`1+Item

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Editor.IItemPicker+Item`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class Item<T> : Game.UI.Editor.IItemPicker+Item, Colossal.UI.Binding.IJsonWritable
{
    public T m_Value;
    public System.String[] m_SearchTerms;

    public Item();

}
```


## Fields

- `public T m_Value`  

```csharp
public T m_Value;
```

- `public System.String[] m_SearchTerms`  

```csharp
public System.String[] m_SearchTerms;
```


## Constructors

- `public Item()`  

```csharp
public Item();
```


