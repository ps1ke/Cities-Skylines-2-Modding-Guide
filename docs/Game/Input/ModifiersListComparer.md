# Game.Input.ProxyBinding+ModifiersListComparer

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEqualityComparer<System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier>>`  

## Fields

- `private readonly Game.Input.ProxyModifier+Comparer m_ModifierComparer`  
- `public static readonly Game.Input.ProxyBinding+ModifiersListComparer defaultComparer`  

## Constructors

- `public ModifiersListComparer(Game.Input.ProxyModifier+Comparer modifierComparer = null)`  

## Methods

- `public Equals(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> x, System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> y) : System.Boolean`  
- `public GetHashCode(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> list) : System.Int32`  

