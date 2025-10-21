# Game.SceneFlow.GameManager+LocalTypeCache

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LocalTypeCache
{
    private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String, System.Reflection.BindingFlags>, System.Reflection.MethodInfo> m_MethodCache;
    private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.PropertyInfo> m_PropertyCache;
    private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.FieldInfo> m_FieldCache;

    public LocalTypeCache();

    public System.Reflection.FieldInfo GetField(System.Type type, System.String propertyName);
    public System.Reflection.MethodInfo GetMethod(System.Type type, System.String methodName, System.Reflection.BindingFlags bindingFlags);
    public System.Reflection.PropertyInfo GetProperty(System.Type type, System.String propertyName);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String, System.Reflection.BindingFlags>, System.Reflection.MethodInfo> m_MethodCache`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String, System.Reflection.BindingFlags>, System.Reflection.MethodInfo> m_MethodCache;
```

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.PropertyInfo> m_PropertyCache`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.PropertyInfo> m_PropertyCache;
```

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.FieldInfo> m_FieldCache`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.ValueTuple<System.Type, System.String>, System.Reflection.FieldInfo> m_FieldCache;
```


## Constructors

- `public LocalTypeCache()`  

```csharp
public LocalTypeCache();
```


## Methods

- `public GetField(System.Type type, System.String propertyName) : System.Reflection.FieldInfo`  

```csharp
public System.Reflection.FieldInfo GetField(System.Type type, System.String propertyName);
```

- `public GetMethod(System.Type type, System.String methodName, System.Reflection.BindingFlags bindingFlags) : System.Reflection.MethodInfo`  

```csharp
public System.Reflection.MethodInfo GetMethod(System.Type type, System.String methodName, System.Reflection.BindingFlags bindingFlags);
```

- `public GetProperty(System.Type type, System.String propertyName) : System.Reflection.PropertyInfo`  

```csharp
public System.Reflection.PropertyInfo GetProperty(System.Type type, System.String propertyName);
```


