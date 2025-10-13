# Colossal.OdinSerializer.WeakUnityEventFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakReflectionFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class WeakUnityEventFormatter : Colossal.OdinSerializer.WeakReflectionFormatter, Colossal.OdinSerializer.IFormatter
{
    public WeakUnityEventFormatter(System.Type serializedType);

    protected virtual System.Object GetUninitializedObject();
}
```


## Constructors

- `public WeakUnityEventFormatter(System.Type serializedType)`  

```csharp
public WeakUnityEventFormatter(System.Type serializedType);
```


## Methods

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```


