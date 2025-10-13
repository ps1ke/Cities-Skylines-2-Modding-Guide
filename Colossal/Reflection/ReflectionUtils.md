# Colossal.Reflection.ReflectionUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Reflection`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ReflectionUtils
{
    private static System.Collections.Generic.IEnumerable<System.Type> s_TypeCache;
    private static const System.Reflection.BindingFlags kDefaultMethodBindingFlags;

    public static System.Reflection.Assembly FindAssembly(System.String name, System.Boolean ignoreCase);
    public static System.Void ForEachField(System.Type type, System.Reflection.BindingFlags flags, System.Action<System.Reflection.FieldInfo> action);
    public static System.Collections.Generic.IEnumerable<System.Reflection.Assembly> GetAllAssemblies(System.Boolean ignoreUnityAssemblies);
    public static System.Collections.Generic.IEnumerable<System.Type> GetAllAssemblyTypes(System.Boolean ignoreUnityAssemblies);
    public static System.Collections.Generic.IEnumerable<System.Type> GetAllConcreteTypesWithAttribute<T>(System.Boolean ignoreUnityAssemblies);
    public static System.Collections.Generic.IEnumerable<System.ValueTuple<System.Reflection.MethodInfo, T>> GetAllMethodsWithAttribute<T>(System.Type type, System.Boolean inherit, System.Reflection.BindingFlags bindingFlags);
    public static System.Collections.Generic.IEnumerable<System.Type> GetAllTypesDerivedFrom<T>(System.Boolean ignoreUnityAssemblies);
    public static System.Type[] GetAllTypesDerivedFromAsArray<T>(System.Boolean ignoreUnityAssemblies);
    public static T GetAttribute<T>(System.Object[] attribs);
    public static T GetAttributeOrDefault<T>(System.Object[] attribs);
    public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Object[] attribs);
    public static System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, T>> GetEnumNamesValues<T>();
    public static System.Reflection.FieldInfo GetFieldIncludingPrivateBase(System.Type t, System.String name);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttribute<TAttribute>(System.Type type);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttribute<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
    public static System.Reflection.PropertyInfo GetPropertyIncludingPrivateBase(System.Type t, System.String name);
    public static System.Reflection.MethodInfo GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
    public static System.Reflection.MethodInfo GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
    public static System.Type GetType(System.String name, System.Boolean ignoreSystemAssemblies, System.Boolean ignoreUnityAssemblies);
    public static System.Collections.Generic.IEnumerable<System.Type> GetTypesDerivedFrom<T>(System.Reflection.Assembly assembly);
    public static System.Boolean HasAttribute<T>(System.Type type, System.Boolean inherit);
    public static System.Boolean HasAttribute<T>(System.Reflection.MemberInfo member, System.Boolean inherit);
    public static System.Boolean HasMethodsWithAttribute<T>(System.Type type, System.Boolean inherit, System.Reflection.BindingFlags bindingFlags);
    public static System.Void InvalidateTypeCache();
    public static System.Void Invoke(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters);
    public static TResult Invoke<TTarget, TResult>(System.Reflection.MethodInfo methodInfo, TTarget target, System.Object[] parameters);
    public static System.Void Invoke(System.Reflection.MethodInfo methodInfo, System.Object[] parameters);
    public static TResult Invoke<TResult>(System.Reflection.MethodInfo methodInfo, System.Object[] parameters);
    public static System.Threading.Tasks.Task InvokeAsync(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters);
    public static System.Boolean IsAssignableFromGeneric(System.Type genericType, System.Type type);
    public static System.Boolean IsAsync(System.Reflection.MethodInfo method);
    public static System.Boolean IsOfGeneric(System.Type type, System.Type target, System.Type[]& genericTypes, System.Type& baseType);
    public static System.Boolean IsStatic(System.Type type);
    public static System.Boolean IsSubclassOfRawGeneric(System.Type toCheck, System.Type generic);
    public static System.String SimpleTypeName(System.Type type);
    public static System.Boolean TryGetAnyAttribute<T>(System.Type type, T& attribute, System.Boolean inherit);
    public static System.Boolean TryGetAnyAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit);
    public static System.Boolean TryGetAttribute<T>(System.Type type, T& attribute, System.Boolean inherit);
    public static System.Boolean TryGetAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit);
    public static System.Boolean TryGetAttribute<T>(System.Reflection.MethodInfo member, T& attribute, System.Boolean inherit);
    private static System.Boolean TryGetAttributeFromBaseInterfaces<T>(System.Type type, T& attribute, System.Boolean inherit);
    public static System.Boolean TryGetValueOfType<T>(System.Collections.Generic.Dictionary<System.Type, T> dictionary, System.Type type, System.Type& match, T& value);
    public static System.String TypeName(System.Type type, System.Boolean includeNamespace);
}
```


## Fields

- `private static System.Collections.Generic.IEnumerable<System.Type> s_TypeCache`  

```csharp
private static System.Collections.Generic.IEnumerable<System.Type> s_TypeCache;
```

- `private static const System.Reflection.BindingFlags kDefaultMethodBindingFlags`  

```csharp
private static const System.Reflection.BindingFlags kDefaultMethodBindingFlags;
```


## Methods

- `public static FindAssembly(System.String name, System.Boolean ignoreCase = False) : System.Reflection.Assembly`  

```csharp
public static System.Reflection.Assembly FindAssembly(System.String name, System.Boolean ignoreCase);
```

- `public static ForEachField(System.Type type, System.Reflection.BindingFlags flags, System.Action<System.Reflection.FieldInfo> action) : System.Void`  

```csharp
public static System.Void ForEachField(System.Type type, System.Reflection.BindingFlags flags, System.Action<System.Reflection.FieldInfo> action);
```

- `public static GetAllAssemblies(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Reflection.Assembly>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.Assembly> GetAllAssemblies(System.Boolean ignoreUnityAssemblies);
```

- `public static GetAllAssemblyTypes(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetAllAssemblyTypes(System.Boolean ignoreUnityAssemblies);
```

- `public static GetAllConcreteTypesWithAttribute<T>(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetAllConcreteTypesWithAttribute<T>(System.Boolean ignoreUnityAssemblies);
```

- `public static GetAllMethodsWithAttribute<T>(System.Type type, System.Boolean inherit = False, System.Reflection.BindingFlags bindingFlags = Instance, Static, Public, NonPublic) : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Reflection.MethodInfo, T>>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.ValueTuple<System.Reflection.MethodInfo, T>> GetAllMethodsWithAttribute<T>(System.Type type, System.Boolean inherit, System.Reflection.BindingFlags bindingFlags);
```

- `public static GetAllTypesDerivedFrom<T>(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetAllTypesDerivedFrom<T>(System.Boolean ignoreUnityAssemblies);
```

- `public static GetAllTypesDerivedFromAsArray<T>(System.Boolean ignoreUnityAssemblies = True) : System.Type[]`  

```csharp
public static System.Type[] GetAllTypesDerivedFromAsArray<T>(System.Boolean ignoreUnityAssemblies);
```

- `public static GetAttribute<T>(System.Object[] attribs) : T`  

```csharp
public static T GetAttribute<T>(System.Object[] attribs);
```

- `public static GetAttributeOrDefault<T>(System.Object[] attribs) : T`  

```csharp
public static T GetAttributeOrDefault<T>(System.Object[] attribs);
```

- `public static GetAttributes<T>(System.Object[] attribs) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Object[] attribs);
```

- `public static GetEnumNamesValues<T>() : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, T>>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, T>> GetEnumNamesValues<T>();
```

- `public static GetFieldIncludingPrivateBase(System.Type t, System.String name) : System.Reflection.FieldInfo`  

```csharp
public static System.Reflection.FieldInfo GetFieldIncludingPrivateBase(System.Type t, System.String name);
```

- `public static GetMethodsWithAttribute<TAttribute>(System.Type type) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttribute<TAttribute>(System.Type type);
```

- `public static GetMethodsWithAttribute<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttribute<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags);
```

- `public static GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
```

- `public static GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo> GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
```

- `public static GetPropertyIncludingPrivateBase(System.Type t, System.String name) : System.Reflection.PropertyInfo`  

```csharp
public static System.Reflection.PropertyInfo GetPropertyIncludingPrivateBase(System.Type t, System.String name);
```

- `public static GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
```

- `public static GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType, System.Type[] parameterTypes);
```

- `public static GetType(System.String name, System.Boolean ignoreSystemAssemblies = True, System.Boolean ignoreUnityAssemblies = True) : System.Type`  

```csharp
public static System.Type GetType(System.String name, System.Boolean ignoreSystemAssemblies, System.Boolean ignoreUnityAssemblies);
```

- `public static GetTypesDerivedFrom<T>(System.Reflection.Assembly assembly) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetTypesDerivedFrom<T>(System.Reflection.Assembly assembly);
```

- `public static HasAttribute<T>(System.Type type, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean HasAttribute<T>(System.Type type, System.Boolean inherit);
```

- `public static HasAttribute<T>(System.Reflection.MemberInfo member, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean HasAttribute<T>(System.Reflection.MemberInfo member, System.Boolean inherit);
```

- `public static HasMethodsWithAttribute<T>(System.Type type, System.Boolean inherit = False, System.Reflection.BindingFlags bindingFlags = Instance, Static, Public, NonPublic) : System.Boolean`  

```csharp
public static System.Boolean HasMethodsWithAttribute<T>(System.Type type, System.Boolean inherit, System.Reflection.BindingFlags bindingFlags);
```

- `public static InvalidateTypeCache() : System.Void`  

```csharp
public static System.Void InvalidateTypeCache();
```

- `public static Invoke(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters) : System.Void`  

```csharp
public static System.Void Invoke(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters);
```

- `public static Invoke<TTarget, TResult>(System.Reflection.MethodInfo methodInfo, TTarget target, System.Object[] parameters) : TResult`  

```csharp
public static TResult Invoke<TTarget, TResult>(System.Reflection.MethodInfo methodInfo, TTarget target, System.Object[] parameters);
```

- `public static Invoke(System.Reflection.MethodInfo methodInfo, System.Object[] parameters) : System.Void`  

```csharp
public static System.Void Invoke(System.Reflection.MethodInfo methodInfo, System.Object[] parameters);
```

- `public static Invoke<TResult>(System.Reflection.MethodInfo methodInfo, System.Object[] parameters) : TResult`  

```csharp
public static TResult Invoke<TResult>(System.Reflection.MethodInfo methodInfo, System.Object[] parameters);
```

- `public static InvokeAsync(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task InvokeAsync(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters);
```

- `public static IsAssignableFromGeneric(System.Type genericType, System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsAssignableFromGeneric(System.Type genericType, System.Type type);
```

- `public static IsAsync(System.Reflection.MethodInfo method) : System.Boolean`  

```csharp
public static System.Boolean IsAsync(System.Reflection.MethodInfo method);
```

- `public static IsOfGeneric(System.Type type, System.Type target, System.Type[]& genericTypes, System.Type& baseType) : System.Boolean`  

```csharp
public static System.Boolean IsOfGeneric(System.Type type, System.Type target, System.Type[]& genericTypes, System.Type& baseType);
```

- `public static IsStatic(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsStatic(System.Type type);
```

- `public static IsSubclassOfRawGeneric(System.Type toCheck, System.Type generic) : System.Boolean`  

```csharp
public static System.Boolean IsSubclassOfRawGeneric(System.Type toCheck, System.Type generic);
```

- `public static SimpleTypeName(System.Type type) : System.String`  

```csharp
public static System.String SimpleTypeName(System.Type type);
```

- `public static TryGetAnyAttribute<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetAnyAttribute<T>(System.Type type, T& attribute, System.Boolean inherit);
```

- `public static TryGetAnyAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetAnyAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit);
```

- `public static TryGetAttribute<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetAttribute<T>(System.Type type, T& attribute, System.Boolean inherit);
```

- `public static TryGetAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit);
```

- `public static TryGetAttribute<T>(System.Reflection.MethodInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
public static System.Boolean TryGetAttribute<T>(System.Reflection.MethodInfo member, T& attribute, System.Boolean inherit);
```

- `private static TryGetAttributeFromBaseInterfaces<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  

```csharp
private static System.Boolean TryGetAttributeFromBaseInterfaces<T>(System.Type type, T& attribute, System.Boolean inherit);
```

- `public static TryGetValueOfType<T>(System.Collections.Generic.Dictionary<System.Type, T> dictionary, System.Type type, System.Type& match, T& value) : System.Boolean`  

```csharp
public static System.Boolean TryGetValueOfType<T>(System.Collections.Generic.Dictionary<System.Type, T> dictionary, System.Type type, System.Type& match, T& value);
```

- `public static TypeName(System.Type type, System.Boolean includeNamespace = False) : System.String`  

```csharp
public static System.String TypeName(System.Type type, System.Boolean includeNamespace);
```


## Nested types

- `Colossal.Reflection.ReflectionUtils+<>c`  
- `Colossal.Reflection.ReflectionUtils+<>c__18<TAttribute>`  
- `Colossal.Reflection.ReflectionUtils+<>c__20<TAttribute>`  
- `Colossal.Reflection.ReflectionUtils+<>c__29<T>`  
- `Colossal.Reflection.ReflectionUtils+<>c__30<T>`  
- `Colossal.Reflection.ReflectionUtils+<>c__31<T>`  
- `Colossal.Reflection.ReflectionUtils+<>c__40<T>`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass20_0<TAttribute>`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass2_0`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass34_0<T>`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass41_0`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass42_0`  
- `Colossal.Reflection.ReflectionUtils+<>c__DisplayClass4_0`  
- `Colossal.Reflection.ReflectionUtils+<GetAttributes>d__14<T>`  
- `Colossal.Reflection.ReflectionUtils+<GetEnumNamesValues>d__26<T>`  

