# Game.UI.Widgets.IListAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  


## Properties

- `public System.Int32 length { get }`  
- `public System.Boolean resizable { get }`  
- `public System.Boolean sortable { get }`  

## Methods

- `public abstract AddElement() : System.Int32`  
- `public abstract BuildElementsInRange() : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  
- `public abstract Clear() : System.Void`  
- `public abstract DeleteElement(System.Int32 index) : System.Void`  
- `public abstract DuplicateElement(System.Int32 index) : System.Int32`  
- `public abstract InsertElement(System.Int32 index) : System.Void`  
- `public abstract MoveElement(System.Int32 fromIndex, System.Int32 toIndex) : System.Void`  
- `public abstract UpdateRange(System.Int32 startIndex, System.Int32 endIndex) : System.Boolean`  

