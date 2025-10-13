# Colossal.OdinSerializer.Utilities.EmitUtilities

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EmitUtilities
{
    private static System.Reflection.Assembly EngineAssembly;

    public static System.Boolean CanEmit { get; }

    public static Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, FieldType> CreateInstanceFieldGetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo);
    public static Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, FieldType> CreateInstanceFieldSetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo);
    public static System.Action<InstanceType> CreateInstanceMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo);
    public static System.Action<InstanceType, Arg1> CreateInstanceMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo);
    public static Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, PropType> CreateInstancePropertyGetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo);
    public static Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, PropType> CreateInstancePropertySetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo);
    public static Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType> CreateInstanceRefMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo);
    public static Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType, Arg1> CreateInstanceRefMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo);
    public static System.Func<InstanceType, ReturnType> CreateMethodReturner<InstanceType, ReturnType>(System.Reflection.MethodInfo methodInfo);
    public static System.Func<FieldType> CreateStaticFieldGetter<FieldType>(System.Reflection.FieldInfo fieldInfo);
    public static System.Action<FieldType> CreateStaticFieldSetter<FieldType>(System.Reflection.FieldInfo fieldInfo);
    public static System.Action CreateStaticMethodCaller(System.Reflection.MethodInfo methodInfo);
    public static System.Func<PropType> CreateStaticPropertyGetter<PropType>(System.Reflection.PropertyInfo propertyInfo);
    public static System.Action<PropType> CreateStaticPropertySetter<PropType>(System.Reflection.PropertyInfo propertyInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueGetter<FieldType> CreateWeakInstanceFieldGetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueGetter CreateWeakInstanceFieldGetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueSetter<FieldType> CreateWeakInstanceFieldSetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueSetter CreateWeakInstanceFieldSetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
    public static System.Action<System.Object, TArg1> CreateWeakInstanceMethodCaller<TArg1>(System.Reflection.MethodInfo methodInfo);
    public static System.Action<System.Object> CreateWeakInstanceMethodCaller(System.Reflection.MethodInfo methodInfo);
    public static System.Func<System.Object, TArg1, TResult> CreateWeakInstanceMethodCaller<TResult, TArg1>(System.Reflection.MethodInfo methodInfo);
    public static System.Func<System.Object, TResult> CreateWeakInstanceMethodCallerFunc<TResult>(System.Reflection.MethodInfo methodInfo);
    public static System.Func<System.Object, TArg, TResult> CreateWeakInstanceMethodCallerFunc<TArg, TResult>(System.Reflection.MethodInfo methodInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueGetter CreateWeakInstancePropertyGetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo);
    public static Colossal.OdinSerializer.Utilities.WeakValueSetter CreateWeakInstancePropertySetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo);
    public static System.Func<System.Object> CreateWeakStaticFieldGetter(System.Reflection.FieldInfo fieldInfo);
    public static System.Action<System.Object> CreateWeakStaticFieldSetter(System.Reflection.FieldInfo fieldInfo);
    private static System.Boolean EmitIsIllegalForMember(System.Reflection.MemberInfo member);
}
```


## Fields

- `private static System.Reflection.Assembly EngineAssembly`  

```csharp
private static System.Reflection.Assembly EngineAssembly;
```


## Properties

- `public static System.Boolean CanEmit { get }`  

```csharp
public static System.Boolean CanEmit { get; }
```


## Methods

- `public static CreateInstanceFieldGetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, FieldType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, FieldType> CreateInstanceFieldGetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateInstanceFieldSetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, FieldType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, FieldType> CreateInstanceFieldSetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateInstanceMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo) : System.Action<InstanceType>`  

```csharp
public static System.Action<InstanceType> CreateInstanceMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateInstanceMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo) : System.Action<InstanceType, Arg1>`  

```csharp
public static System.Action<InstanceType, Arg1> CreateInstanceMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateInstancePropertyGetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, PropType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, PropType> CreateInstancePropertyGetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateInstancePropertySetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, PropType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, PropType> CreateInstancePropertySetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateInstanceRefMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo) : Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType> CreateInstanceRefMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateInstanceRefMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo) : Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType, Arg1>`  

```csharp
public static Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType, Arg1> CreateInstanceRefMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateMethodReturner<InstanceType, ReturnType>(System.Reflection.MethodInfo methodInfo) : System.Func<InstanceType, ReturnType>`  

```csharp
public static System.Func<InstanceType, ReturnType> CreateMethodReturner<InstanceType, ReturnType>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateStaticFieldGetter<FieldType>(System.Reflection.FieldInfo fieldInfo) : System.Func<FieldType>`  

```csharp
public static System.Func<FieldType> CreateStaticFieldGetter<FieldType>(System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateStaticFieldSetter<FieldType>(System.Reflection.FieldInfo fieldInfo) : System.Action<FieldType>`  

```csharp
public static System.Action<FieldType> CreateStaticFieldSetter<FieldType>(System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateStaticMethodCaller(System.Reflection.MethodInfo methodInfo) : System.Action`  

```csharp
public static System.Action CreateStaticMethodCaller(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateStaticPropertyGetter<PropType>(System.Reflection.PropertyInfo propertyInfo) : System.Func<PropType>`  

```csharp
public static System.Func<PropType> CreateStaticPropertyGetter<PropType>(System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateStaticPropertySetter<PropType>(System.Reflection.PropertyInfo propertyInfo) : System.Action<PropType>`  

```csharp
public static System.Action<PropType> CreateStaticPropertySetter<PropType>(System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateWeakInstanceFieldGetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter<FieldType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueGetter<FieldType> CreateWeakInstanceFieldGetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateWeakInstanceFieldGetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueGetter CreateWeakInstanceFieldGetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateWeakInstanceFieldSetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter<FieldType>`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueSetter<FieldType> CreateWeakInstanceFieldSetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateWeakInstanceFieldSetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueSetter CreateWeakInstanceFieldSetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateWeakInstanceMethodCaller<TArg1>(System.Reflection.MethodInfo methodInfo) : System.Action<System.Object, TArg1>`  

```csharp
public static System.Action<System.Object, TArg1> CreateWeakInstanceMethodCaller<TArg1>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateWeakInstanceMethodCaller(System.Reflection.MethodInfo methodInfo) : System.Action<System.Object>`  

```csharp
public static System.Action<System.Object> CreateWeakInstanceMethodCaller(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateWeakInstanceMethodCaller<TResult, TArg1>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TArg1, TResult>`  

```csharp
public static System.Func<System.Object, TArg1, TResult> CreateWeakInstanceMethodCaller<TResult, TArg1>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateWeakInstanceMethodCallerFunc<TResult>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TResult>`  

```csharp
public static System.Func<System.Object, TResult> CreateWeakInstanceMethodCallerFunc<TResult>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateWeakInstanceMethodCallerFunc<TArg, TResult>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TArg, TResult>`  

```csharp
public static System.Func<System.Object, TArg, TResult> CreateWeakInstanceMethodCallerFunc<TArg, TResult>(System.Reflection.MethodInfo methodInfo);
```

- `public static CreateWeakInstancePropertyGetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueGetter CreateWeakInstancePropertyGetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateWeakInstancePropertySetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  

```csharp
public static Colossal.OdinSerializer.Utilities.WeakValueSetter CreateWeakInstancePropertySetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo);
```

- `public static CreateWeakStaticFieldGetter(System.Reflection.FieldInfo fieldInfo) : System.Func<System.Object>`  

```csharp
public static System.Func<System.Object> CreateWeakStaticFieldGetter(System.Reflection.FieldInfo fieldInfo);
```

- `public static CreateWeakStaticFieldSetter(System.Reflection.FieldInfo fieldInfo) : System.Action<System.Object>`  

```csharp
public static System.Action<System.Object> CreateWeakStaticFieldSetter(System.Reflection.FieldInfo fieldInfo);
```

- `private static EmitIsIllegalForMember(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
private static System.Boolean EmitIsIllegalForMember(System.Reflection.MemberInfo member);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType, TArg1>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass10_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass11_0<InstanceType, FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass12_0<FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass13_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass14_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass15_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass16_0<PropType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass17_0<PropType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass18_0<InstanceType, PropType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass19_0<InstanceType, PropType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass22_0<TArg1>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass23_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass24_0<TResult, TArg1>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass25_0<TResult>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass26_0<TArg, TResult>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass31_0<InstanceType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass32_0<InstanceType, Arg1>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass4_0<FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass4_1<FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass5_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass6_0<FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass7_0`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass8_0<InstanceType, FieldType>`  
- `Colossal.OdinSerializer.Utilities.EmitUtilities+<>c__DisplayClass9_0<FieldType>`  

