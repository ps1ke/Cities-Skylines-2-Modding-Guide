# Game.Reflection.GetterWithDepsAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.GetterWithDepsAccessor>`  

## Fields

- `private readonly Game.Reflection.IValueAccessor m_Parent`  
- `private readonly System.Reflection.MethodInfo m_Getter`  
- `private readonly System.Object[] m_Parameters`  
- `private readonly System.Int32 m_DepsIndex`  

## Properties

- `public System.Type valueType { get }`  

## Constructors

- `public GetterWithDepsAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Object[] parameters = null, System.Int32 depsIndex = -1)`  

## Methods

- `public Equals(Game.Reflection.GetterWithDepsAccessor other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetValue() : System.Object`  
- `public SetValue(System.Object value) : System.Void`  

