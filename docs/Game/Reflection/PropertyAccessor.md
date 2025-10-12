# Game.Reflection.PropertyAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Reflection.IValueAccessor`, `System.IEquatable<Game.Reflection.PropertyAccessor>`  

## Fields

- `private readonly Game.Reflection.IValueAccessor m_Parent`  
- `private readonly System.Reflection.MethodInfo m_Getter`  
- `private readonly System.Reflection.MethodInfo m_Setter`  

## Properties

- `public System.Type valueType { get }`  

## Constructors

- `public PropertyAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MethodInfo getter, System.Reflection.MethodInfo setter)`  

## Methods

- `public Equals(Game.Reflection.PropertyAccessor other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetValue() : System.Object`  
- `public SetValue(System.Object value) : System.Void`  

