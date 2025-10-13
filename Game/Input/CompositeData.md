# Game.Input.InputManager+CompositeData

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CompositeData
{
    public readonly System.String m_TypeName;
    public readonly Game.Input.ActionType m_ActionType;
    public readonly System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.InputManager+CompositeComponentData> m_Data;

    public CompositeData(System.String typeName, Game.Input.ActionType actionType, Game.Input.InputManager+CompositeComponentData[] data);

    public System.Boolean TryFindByBindingName(System.String bindingName, Game.Input.InputManager+CompositeComponentData& data);
    public System.Boolean TryGetData(Game.Input.ActionComponent component, Game.Input.InputManager+CompositeComponentData& data);
}
```


## Fields

- `public readonly System.String m_TypeName`  

```csharp
public readonly System.String m_TypeName;
```

- `public readonly Game.Input.ActionType m_ActionType`  

```csharp
public readonly Game.Input.ActionType m_ActionType;
```

- `public readonly System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.InputManager+CompositeComponentData> m_Data`  

```csharp
public readonly System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.InputManager+CompositeComponentData> m_Data;
```


## Constructors

- `public CompositeData(System.String typeName, Game.Input.ActionType actionType, Game.Input.InputManager+CompositeComponentData[] data)`  

```csharp
public CompositeData(System.String typeName, Game.Input.ActionType actionType, Game.Input.InputManager+CompositeComponentData[] data);
```


## Methods

- `public TryFindByBindingName(System.String bindingName, Game.Input.InputManager+CompositeComponentData& data) : System.Boolean`  

```csharp
public System.Boolean TryFindByBindingName(System.String bindingName, Game.Input.InputManager+CompositeComponentData& data);
```

- `public TryGetData(Game.Input.ActionComponent component, Game.Input.InputManager+CompositeComponentData& data) : System.Boolean`  

```csharp
public System.Boolean TryGetData(Game.Input.ActionComponent component, Game.Input.InputManager+CompositeComponentData& data);
```


## Nested types

- `Game.Input.InputManager+CompositeData+<>c`  

