# Game.SceneFlow.GameManager+LocalTypeCache

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String, System.Reflection.BindingFlags>, System.Reflection.MethodInfo> m_MethodCache`  
- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.PropertyInfo> m_PropertyCache`  
- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.FieldInfo> m_FieldCache`  

## Constructors

- `public LocalTypeCache()`  

## Methods

- `public GetField(System.Type type, System.String propertyName) : System.Reflection.FieldInfo`  
- `public GetMethod(System.Type type, System.String methodName, System.Reflection.BindingFlags bindingFlags) : System.Reflection.MethodInfo`  
- `public GetProperty(System.Type type, System.String propertyName) : System.Reflection.PropertyInfo`  

