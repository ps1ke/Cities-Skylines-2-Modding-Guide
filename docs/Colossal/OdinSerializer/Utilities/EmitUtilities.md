# Colossal.OdinSerializer.Utilities.EmitUtilities

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Reflection.Assembly EngineAssembly`  

## Properties

- `public static System.Boolean CanEmit { get }`  

## Methods

- `public static CreateInstanceFieldGetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, FieldType>`  
- `public static CreateInstanceFieldSetter<InstanceType, FieldType>(System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, FieldType>`  
- `public static CreateInstanceMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo) : System.Action<InstanceType>`  
- `public static CreateInstanceMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo) : System.Action<InstanceType, Arg1>`  
- `public static CreateInstancePropertyGetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.ValueGetter<InstanceType, PropType>`  
- `public static CreateInstancePropertySetter<InstanceType, PropType>(System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.ValueSetter<InstanceType, PropType>`  
- `public static CreateInstanceRefMethodCaller<InstanceType>(System.Reflection.MethodInfo methodInfo) : Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType>`  
- `public static CreateInstanceRefMethodCaller<InstanceType, Arg1>(System.Reflection.MethodInfo methodInfo) : Colossal.OdinSerializer.Utilities.EmitUtilities+InstanceRefMethodCaller<InstanceType, Arg1>`  
- `public static CreateMethodReturner<InstanceType, ReturnType>(System.Reflection.MethodInfo methodInfo) : System.Func<InstanceType, ReturnType>`  
- `public static CreateStaticFieldGetter<FieldType>(System.Reflection.FieldInfo fieldInfo) : System.Func<FieldType>`  
- `public static CreateStaticFieldSetter<FieldType>(System.Reflection.FieldInfo fieldInfo) : System.Action<FieldType>`  
- `public static CreateStaticMethodCaller(System.Reflection.MethodInfo methodInfo) : System.Action`  
- `public static CreateStaticPropertyGetter<PropType>(System.Reflection.PropertyInfo propertyInfo) : System.Func<PropType>`  
- `public static CreateStaticPropertySetter<PropType>(System.Reflection.PropertyInfo propertyInfo) : System.Action<PropType>`  
- `public static CreateWeakInstanceFieldGetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter<FieldType>`  
- `public static CreateWeakInstanceFieldGetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  
- `public static CreateWeakInstanceFieldSetter<FieldType>(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter<FieldType>`  
- `public static CreateWeakInstanceFieldSetter(System.Type instanceType, System.Reflection.FieldInfo fieldInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  
- `public static CreateWeakInstanceMethodCaller<TArg1>(System.Reflection.MethodInfo methodInfo) : System.Action<System.Object, TArg1>`  
- `public static CreateWeakInstanceMethodCaller(System.Reflection.MethodInfo methodInfo) : System.Action<System.Object>`  
- `public static CreateWeakInstanceMethodCaller<TResult, TArg1>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TArg1, TResult>`  
- `public static CreateWeakInstanceMethodCallerFunc<TResult>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TResult>`  
- `public static CreateWeakInstanceMethodCallerFunc<TArg, TResult>(System.Reflection.MethodInfo methodInfo) : System.Func<System.Object, TArg, TResult>`  
- `public static CreateWeakInstancePropertyGetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  
- `public static CreateWeakInstancePropertySetter(System.Type instanceType, System.Reflection.PropertyInfo propertyInfo) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  
- `public static CreateWeakStaticFieldGetter(System.Reflection.FieldInfo fieldInfo) : System.Func<System.Object>`  
- `public static CreateWeakStaticFieldSetter(System.Reflection.FieldInfo fieldInfo) : System.Action<System.Object>`  
- `private static EmitIsIllegalForMember(System.Reflection.MemberInfo member) : System.Boolean`  

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

