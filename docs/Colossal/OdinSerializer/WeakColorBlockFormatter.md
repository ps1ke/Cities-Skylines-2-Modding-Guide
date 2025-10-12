# Colossal.OdinSerializer.WeakColorBlockFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly System.Reflection.PropertyInfo normalColor`  
- `private readonly System.Reflection.PropertyInfo highlightedColor`  
- `private readonly System.Reflection.PropertyInfo pressedColor`  
- `private readonly System.Reflection.PropertyInfo disabledColor`  
- `private readonly System.Reflection.PropertyInfo colorMultiplier`  
- `private readonly System.Reflection.PropertyInfo fadeDuration`  
- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  
- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer`  

## Constructors

- `public WeakColorBlockFormatter(System.Type colorBlockType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

