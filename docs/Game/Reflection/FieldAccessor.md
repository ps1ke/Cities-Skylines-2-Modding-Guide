# Game.Reflection.FieldAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.FieldAccessor>`  

## Fields

- `private readonly Game.Reflection.IValueAccessor m_Parent`  
- `private readonly System.Reflection.FieldInfo m_Field`  

## Properties

- `public System.Type valueType { get }`  
- `public Game.Reflection.IValueAccessor parent { get }`  

## Constructors

- `public FieldAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.FieldInfo field)`  

## Methods

- `public Equals(Game.Reflection.FieldAccessor other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetValue() : System.Object`  
- `public SetValue(System.Object value) : System.Void`  

