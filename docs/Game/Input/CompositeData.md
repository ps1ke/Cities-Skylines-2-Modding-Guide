# Game.Input.InputManager+CompositeData

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Fields

- `public readonly System.String m_TypeName`  
- `public readonly Game.Input.ActionType m_ActionType`  
- `public readonly System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.InputManager+CompositeComponentData> m_Data`  

## Constructors

- `public CompositeData(System.String typeName, Game.Input.ActionType actionType, Game.Input.InputManager+CompositeComponentData[] data)`  

## Methods

- `public TryFindByBindingName(System.String bindingName, Game.Input.InputManager+CompositeComponentData& data) : System.Boolean`  
- `public TryGetData(Game.Input.ActionComponent component, Game.Input.InputManager+CompositeComponentData& data) : System.Boolean`  

## Nested types

- `Game.Input.InputManager+CompositeData+<>c`  

