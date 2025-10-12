# Colossal.Reflection.ReflectionUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Reflection`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static System.Collections.Generic.IEnumerable<System.Type> s_TypeCache`  
- `private static const System.Reflection.BindingFlags kDefaultMethodBindingFlags`  

## Methods

- `public static FindAssembly(System.String name, System.Boolean ignoreCase = False) : System.Reflection.Assembly`  
- `public static ForEachField(System.Type type, System.Reflection.BindingFlags flags, System.Action<System.Reflection.FieldInfo> action) : System.Void`  
- `public static GetAllAssemblies(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Reflection.Assembly>`  
- `public static GetAllAssemblyTypes(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static GetAllConcreteTypesWithAttribute<T>(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static GetAllMethodsWithAttribute<T>(System.Type type, System.Boolean inherit = False, System.Reflection.BindingFlags bindingFlags = Instance, Static, Public, NonPublic) : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Reflection.MethodInfo, T>>`  
- `public static GetAllTypesDerivedFrom<T>(System.Boolean ignoreUnityAssemblies = True) : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static GetAllTypesDerivedFromAsArray<T>(System.Boolean ignoreUnityAssemblies = True) : System.Type[]`  
- `public static GetAttribute<T>(System.Object[] attribs) : T`  
- `public static GetAttributeOrDefault<T>(System.Object[] attribs) : T`  
- `public static GetAttributes<T>(System.Object[] attribs) : System.Collections.Generic.IEnumerable<T>`  
- `public static GetEnumNamesValues<T>() : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, T>>`  
- `public static GetFieldIncludingPrivateBase(System.Type t, System.String name) : System.Reflection.FieldInfo`  
- `public static GetMethodsWithAttribute<TAttribute>(System.Type type) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  
- `public static GetMethodsWithAttribute<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  
- `public static GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  
- `public static GetMethodsWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Collections.Generic.IEnumerable<System.Reflection.MethodInfo>`  
- `public static GetPropertyIncludingPrivateBase(System.Type t, System.String name) : System.Reflection.PropertyInfo`  
- `public static GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Reflection.MethodInfo`  
- `public static GetSingleMethodWithAttributeAndSignature<TAttribute>(System.Type type, System.Reflection.BindingFlags bindingFlags, System.Type returnType, System.Type alternativeAsyncReturnType = null, System.Type[] parameterTypes) : System.Reflection.MethodInfo`  
- `public static GetType(System.String name, System.Boolean ignoreSystemAssemblies = True, System.Boolean ignoreUnityAssemblies = True) : System.Type`  
- `public static GetTypesDerivedFrom<T>(System.Reflection.Assembly assembly) : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static HasAttribute<T>(System.Type type, System.Boolean inherit = False) : System.Boolean`  
- `public static HasAttribute<T>(System.Reflection.MemberInfo member, System.Boolean inherit = False) : System.Boolean`  
- `public static HasMethodsWithAttribute<T>(System.Type type, System.Boolean inherit = False, System.Reflection.BindingFlags bindingFlags = Instance, Static, Public, NonPublic) : System.Boolean`  
- `public static InvalidateTypeCache() : System.Void`  
- `public static Invoke(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters) : System.Void`  
- `public static Invoke<TTarget, TResult>(System.Reflection.MethodInfo methodInfo, TTarget target, System.Object[] parameters) : TResult`  
- `public static Invoke(System.Reflection.MethodInfo methodInfo, System.Object[] parameters) : System.Void`  
- `public static Invoke<TResult>(System.Reflection.MethodInfo methodInfo, System.Object[] parameters) : TResult`  
- `public static InvokeAsync(System.Reflection.MethodInfo methodInfo, System.Object target, System.Object[] parameters) : System.Threading.Tasks.Task`  
- `public static IsAssignableFromGeneric(System.Type genericType, System.Type type) : System.Boolean`  
- `public static IsAsync(System.Reflection.MethodInfo method) : System.Boolean`  
- `public static IsOfGeneric(System.Type type, System.Type target, System.Type[]& genericTypes, System.Type& baseType) : System.Boolean`  
- `public static IsStatic(System.Type type) : System.Boolean`  
- `public static IsSubclassOfRawGeneric(System.Type toCheck, System.Type generic) : System.Boolean`  
- `public static SimpleTypeName(System.Type type) : System.String`  
- `public static TryGetAnyAttribute<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `public static TryGetAnyAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `public static TryGetAttribute<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `public static TryGetAttribute<T>(System.Reflection.MemberInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `public static TryGetAttribute<T>(System.Reflection.MethodInfo member, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `private static TryGetAttributeFromBaseInterfaces<T>(System.Type type, T& attribute, System.Boolean inherit = False) : System.Boolean`  
- `public static TryGetValueOfType<T>(System.Collections.Generic.Dictionary<System.Type, T> dictionary, System.Type type, System.Type& match, T& value) : System.Boolean`  
- `public static TypeName(System.Type type, System.Boolean includeNamespace = False) : System.String`  

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

