# Game.Input.ProxyComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private readonly Game.Input.CompositeInstance m_Source`  
- `public readonly Game.Input.InputManager+DeviceType m_Device`  
- `public readonly Game.Input.ActionType m_Type`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction> m_LinkedActions`  
- `private readonly System.Collections.Generic.Dictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> m_Bindings`  

## Properties

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Input.ActionComponent, Game.Input.ProxyBinding> bindings { get }`  
- `public System.Boolean isSet { get }`  
- `public System.Boolean isBuiltIn { get }`  
- `internal System.Boolean isDummy { internal get }`  
- `internal System.Boolean isHidden { internal get }`  
- `public System.Boolean isRebindable { get }`  
- `public System.Boolean isModifiersRebindable { get }`  
- `public System.Boolean allowModifiers { get }`  
- `public System.Boolean canBeEmpty { get }`  
- `public System.Boolean developerOnly { get }`  
- `public Game.Input.Usages usage { get }`  

## Constructors

- `internal ProxyComposite(Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.CompositeInstance source, System.Collections.Generic.IList<Game.Input.ProxyBinding> bindings)`  

## Methods

- `public virtual ToString() : System.String`  
- `public TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  
- `public TryGetBinding(Game.Input.ActionComponent component, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

## Nested types

- `Game.Input.ProxyComposite+Info`  
- `Game.Input.ProxyComposite+<>c`  

