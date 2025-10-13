# Colossal.OdinSerializer.Utilities.TypeExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class TypeExtensions
{
    private static readonly System.Func<System.Single, System.Single, System.Boolean> FloatEqualityComparerFunc;
    private static readonly System.Func<System.Double, System.Double, System.Boolean> DoubleEqualityComparerFunc;
    private static readonly System.Func<UnityEngine.Quaternion, UnityEngine.Quaternion, System.Boolean> QuaternionEqualityComparerFunc;
    private static readonly System.Object GenericConstraintsSatisfaction_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionInferredParameters;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionResolvedMap;
    private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionProcessedParams;
    private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionTypesToCheck;
    private static readonly System.Collections.Generic.List<System.Type> GenericConstraintsSatisfactionTypesToCheck_ToAdd;
    private static readonly System.Type GenericListInterface;
    private static readonly System.Type GenericCollectionInterface;
    private static readonly System.Object WeaklyTypedTypeCastDelegates_LOCK;
    private static readonly System.Object StronglyTypedTypeCastDelegates_LOCK;
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Func<System.Object, System.Object>> WeaklyTypedTypeCastDelegates;
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Delegate> StronglyTypedTypeCastDelegates;
    private static readonly System.Type[] TwoLengthTypeArray_Cached;
    private static readonly System.Collections.Generic.Stack<System.Type> GenericArgumentsContainsTypes_ArgsToCheckCached;
    private static System.Collections.Generic.HashSet<System.String> ReservedCSharpKeywords;
    public static readonly System.Collections.Generic.Dictionary<System.String, System.String> TypeNameAlternatives;
    private static readonly System.Object CachedNiceNames_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> CachedNiceNames;
    private static readonly System.Type VoidPointerType;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.HashSet<System.Type>> PrimitiveImplicitCasts;
    private static readonly System.Collections.Generic.HashSet<System.Type> ExplicitCastIntegrals;

    public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Type genericType, System.Type[] parameters);
    public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Reflection.MethodBase genericMethod, System.Type[] parameters);
    public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Type[] definitions, System.Type[] parameters);
    private static System.String CreateNiceName(System.Type type);
    private static System.Boolean DoubleEqualityComparer(System.Double a, System.Double b);
    private static System.Boolean FloatEqualityComparer(System.Single a, System.Single b);
    public static System.Boolean GenericArgumentsContainsTypes(System.Type type, System.Type[] types);
    public static System.Boolean GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType);
    private static System.Boolean GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType, System.Collections.Generic.Dictionary<System.Type, System.Type> resolvedMap, System.Collections.Generic.HashSet<System.Type> processedParams);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetAllMembers(System.Type type, System.Reflection.BindingFlags flags);
    public static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetAllMembers(System.Type type, System.String name, System.Reflection.BindingFlags flags);
    public static System.Collections.Generic.IEnumerable<T> GetAllMembers<T>(System.Type type, System.Reflection.BindingFlags flags);
    public static System.Type[] GetArgumentsOfInheritedOpenGenericClass(System.Type candidateType, System.Type openGenericType);
    public static System.Type[] GetArgumentsOfInheritedOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType);
    public static System.Type[] GetArgumentsOfInheritedOpenGenericType(System.Type candidateType, System.Type openGenericType);
    public static T GetAttribute<T>(System.Type type, System.Boolean inherit);
    public static System.Collections.Generic.IEnumerable<System.Type> GetBaseClasses(System.Type type, System.Boolean includeSelf);
    public static System.Collections.Generic.IEnumerable<System.Type> GetBaseTypes(System.Type type, System.Boolean includeSelf);
    private static System.String GetCachedNiceName(System.Type type);
    public static System.Reflection.MethodInfo GetCastMethod(System.Type from, System.Type to, System.Boolean requireImplicitCast);
    public static System.Func<System.Object, System.Object> GetCastMethodDelegate(System.Type from, System.Type to, System.Boolean requireImplicitCast);
    public static System.Func<TFrom, TTo> GetCastMethodDelegate<TFrom, TTo>(System.Boolean requireImplicitCast);
    public static System.String GetCompilableNiceFullName(System.Type type);
    public static System.String GetCompilableNiceName(System.Type type);
    public static T GetCustomAttribute<T>(System.Type type, System.Boolean inherit);
    public static T GetCustomAttribute<T>(System.Type type);
    public static System.Collections.Generic.IEnumerable<T> GetCustomAttributes<T>(System.Type type);
    public static System.Collections.Generic.IEnumerable<T> GetCustomAttributes<T>(System.Type type, System.Boolean inherit);
    public static System.UInt64 GetEnumBitmask(System.Object value, System.Type enumType);
    public static System.Func<T, T, System.Boolean> GetEqualityComparerDelegate<T>();
    public static System.Type GetGenericBaseType(System.Type type, System.Type baseType);
    public static System.Type GetGenericBaseType(System.Type type, System.Type baseType, System.Int32& depthCount);
    public static System.String GetGenericConstraintsString(System.Type type, System.Boolean useFullTypeNames);
    public static System.String GetGenericParameterConstraintsString(System.Type type, System.Boolean useFullTypeNames);
    public static System.Int32 GetInheritanceDistance(System.Type type, System.Type baseType);
    public static System.Object GetMemberValue(System.Reflection.MemberInfo member, System.Object obj);
    public static System.String GetNiceFullName(System.Type type);
    public static System.String GetNiceName(System.Type type);
    public static System.Reflection.MethodInfo GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op, System.Type leftOperand, System.Type rightOperand);
    public static System.Reflection.MethodInfo GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op);
    public static System.Reflection.MethodInfo[] GetOperatorMethods(System.Type type, Colossal.OdinSerializer.Utilities.Operator op);
    public static System.Type GetReturnType(System.Reflection.MemberInfo memberInfo);
    internal static System.Boolean HasCastDefined(System.Type from, System.Type to, System.Boolean requireImplicitCast);
    public static System.Boolean HasParamaters(System.Reflection.MethodInfo methodInfo, System.Collections.Generic.IList<System.Type> paramTypes, System.Boolean inherit);
    public static System.Boolean ImplementsOpenGenericClass(System.Type candidateType, System.Type openGenericType);
    public static System.Boolean ImplementsOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType);
    public static System.Boolean ImplementsOpenGenericType(System.Type candidateType, System.Type openGenericType);
    public static System.Boolean ImplementsOrInherits(System.Type type, System.Type to);
    public static System.Boolean InheritsFrom<TBase>(System.Type type);
    public static System.Boolean InheritsFrom(System.Type type, System.Type baseType);
    public static System.Boolean IsCastableTo(System.Type from, System.Type to, System.Boolean requireImplicitCast);
    public static System.Boolean IsDefined<T>(System.Type type);
    public static System.Boolean IsDefined<T>(System.Type type, System.Boolean inherit);
    public static System.Boolean IsFullyConstructedGenericType(System.Type type);
    public static System.Boolean IsNullableType(System.Type type);
    public static System.Boolean IsValidIdentifier(System.String identifier);
    private static System.Boolean IsValidIdentifierPartCharacter(System.Char c);
    private static System.Boolean IsValidIdentifierStartCharacter(System.Char c);
    private static System.Boolean QuaternionEqualityComparer(UnityEngine.Quaternion a, UnityEngine.Quaternion b);
    public static System.Object[] SafeGetCustomAttributes(System.Reflection.Assembly assembly, System.Type type, System.Boolean inherit);
    public static System.Type[] SafeGetTypes(System.Reflection.Assembly assembly);
    public static System.Boolean SafeIsDefined(System.Reflection.Assembly assembly, System.Type attribute, System.Boolean inherit);
    public static System.Void SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value);
    public static System.Boolean TryInferGenericParameters(System.Type genericTypeDefinition, System.Type[]& inferredParams, System.Type[] knownParameters);
    private static System.String TypeNameGauntlet(System.Type type);
}
```


## Fields

- `private static readonly System.Func<System.Single, System.Single, System.Boolean> FloatEqualityComparerFunc`  

```csharp
private static readonly System.Func<System.Single, System.Single, System.Boolean> FloatEqualityComparerFunc;
```

- `private static readonly System.Func<System.Double, System.Double, System.Boolean> DoubleEqualityComparerFunc`  

```csharp
private static readonly System.Func<System.Double, System.Double, System.Boolean> DoubleEqualityComparerFunc;
```

- `private static readonly System.Func<UnityEngine.Quaternion, UnityEngine.Quaternion, System.Boolean> QuaternionEqualityComparerFunc`  

```csharp
private static readonly System.Func<UnityEngine.Quaternion, UnityEngine.Quaternion, System.Boolean> QuaternionEqualityComparerFunc;
```

- `private static readonly System.Object GenericConstraintsSatisfaction_LOCK`  

```csharp
private static readonly System.Object GenericConstraintsSatisfaction_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionInferredParameters`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionInferredParameters;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionResolvedMap`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionResolvedMap;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionProcessedParams`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionProcessedParams;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionTypesToCheck`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionTypesToCheck;
```

- `private static readonly System.Collections.Generic.List<System.Type> GenericConstraintsSatisfactionTypesToCheck_ToAdd`  

```csharp
private static readonly System.Collections.Generic.List<System.Type> GenericConstraintsSatisfactionTypesToCheck_ToAdd;
```

- `private static readonly System.Type GenericListInterface`  

```csharp
private static readonly System.Type GenericListInterface;
```

- `private static readonly System.Type GenericCollectionInterface`  

```csharp
private static readonly System.Type GenericCollectionInterface;
```

- `private static readonly System.Object WeaklyTypedTypeCastDelegates_LOCK`  

```csharp
private static readonly System.Object WeaklyTypedTypeCastDelegates_LOCK;
```

- `private static readonly System.Object StronglyTypedTypeCastDelegates_LOCK`  

```csharp
private static readonly System.Object StronglyTypedTypeCastDelegates_LOCK;
```

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Func<System.Object, System.Object>> WeaklyTypedTypeCastDelegates`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Func<System.Object, System.Object>> WeaklyTypedTypeCastDelegates;
```

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Delegate> StronglyTypedTypeCastDelegates`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Delegate> StronglyTypedTypeCastDelegates;
```

- `private static readonly System.Type[] TwoLengthTypeArray_Cached`  

```csharp
private static readonly System.Type[] TwoLengthTypeArray_Cached;
```

- `private static readonly System.Collections.Generic.Stack<System.Type> GenericArgumentsContainsTypes_ArgsToCheckCached`  

```csharp
private static readonly System.Collections.Generic.Stack<System.Type> GenericArgumentsContainsTypes_ArgsToCheckCached;
```

- `private static System.Collections.Generic.HashSet<System.String> ReservedCSharpKeywords`  

```csharp
private static System.Collections.Generic.HashSet<System.String> ReservedCSharpKeywords;
```

- `public static readonly System.Collections.Generic.Dictionary<System.String, System.String> TypeNameAlternatives`  

```csharp
public static readonly System.Collections.Generic.Dictionary<System.String, System.String> TypeNameAlternatives;
```

- `private static readonly System.Object CachedNiceNames_LOCK`  

```csharp
private static readonly System.Object CachedNiceNames_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> CachedNiceNames`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> CachedNiceNames;
```

- `private static readonly System.Type VoidPointerType`  

```csharp
private static readonly System.Type VoidPointerType;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.HashSet<System.Type>> PrimitiveImplicitCasts`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.HashSet<System.Type>> PrimitiveImplicitCasts;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> ExplicitCastIntegrals`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> ExplicitCastIntegrals;
```


## Methods

- `public static AreGenericConstraintsSatisfiedBy(System.Type genericType, System.Type[] parameters) : System.Boolean`  

```csharp
public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Type genericType, System.Type[] parameters);
```

- `public static AreGenericConstraintsSatisfiedBy(System.Reflection.MethodBase genericMethod, System.Type[] parameters) : System.Boolean`  

```csharp
public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Reflection.MethodBase genericMethod, System.Type[] parameters);
```

- `public static AreGenericConstraintsSatisfiedBy(System.Type[] definitions, System.Type[] parameters) : System.Boolean`  

```csharp
public static System.Boolean AreGenericConstraintsSatisfiedBy(System.Type[] definitions, System.Type[] parameters);
```

- `private static CreateNiceName(System.Type type) : System.String`  

```csharp
private static System.String CreateNiceName(System.Type type);
```

- `private static DoubleEqualityComparer(System.Double a, System.Double b) : System.Boolean`  

```csharp
private static System.Boolean DoubleEqualityComparer(System.Double a, System.Double b);
```

- `private static FloatEqualityComparer(System.Single a, System.Single b) : System.Boolean`  

```csharp
private static System.Boolean FloatEqualityComparer(System.Single a, System.Single b);
```

- `public static GenericArgumentsContainsTypes(System.Type type, System.Type[] types) : System.Boolean`  

```csharp
public static System.Boolean GenericArgumentsContainsTypes(System.Type type, System.Type[] types);
```

- `public static GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType) : System.Boolean`  

```csharp
public static System.Boolean GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType);
```

- `private static GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType, System.Collections.Generic.Dictionary<System.Type, System.Type> resolvedMap, System.Collections.Generic.HashSet<System.Type> processedParams = null) : System.Boolean`  

```csharp
private static System.Boolean GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType, System.Collections.Generic.Dictionary<System.Type, System.Type> resolvedMap, System.Collections.Generic.HashSet<System.Type> processedParams);
```

- `public static GetAllMembers(System.Type type, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetAllMembers(System.Type type, System.Reflection.BindingFlags flags);
```

- `public static GetAllMembers(System.Type type, System.String name, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetAllMembers(System.Type type, System.String name, System.Reflection.BindingFlags flags);
```

- `public static GetAllMembers<T>(System.Type type, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetAllMembers<T>(System.Type type, System.Reflection.BindingFlags flags);
```

- `public static GetArgumentsOfInheritedOpenGenericClass(System.Type candidateType, System.Type openGenericType) : System.Type[]`  

```csharp
public static System.Type[] GetArgumentsOfInheritedOpenGenericClass(System.Type candidateType, System.Type openGenericType);
```

- `public static GetArgumentsOfInheritedOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType) : System.Type[]`  

```csharp
public static System.Type[] GetArgumentsOfInheritedOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType);
```

- `public static GetArgumentsOfInheritedOpenGenericType(System.Type candidateType, System.Type openGenericType) : System.Type[]`  

```csharp
public static System.Type[] GetArgumentsOfInheritedOpenGenericType(System.Type candidateType, System.Type openGenericType);
```

- `public static GetAttribute<T>(System.Type type, System.Boolean inherit) : T`  

```csharp
public static T GetAttribute<T>(System.Type type, System.Boolean inherit);
```

- `public static GetBaseClasses(System.Type type, System.Boolean includeSelf = False) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetBaseClasses(System.Type type, System.Boolean includeSelf);
```

- `public static GetBaseTypes(System.Type type, System.Boolean includeSelf = False) : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetBaseTypes(System.Type type, System.Boolean includeSelf);
```

- `private static GetCachedNiceName(System.Type type) : System.String`  

```csharp
private static System.String GetCachedNiceName(System.Type type);
```

- `public static GetCastMethod(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo GetCastMethod(System.Type from, System.Type to, System.Boolean requireImplicitCast);
```

- `public static GetCastMethodDelegate(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Func<System.Object, System.Object>`  

```csharp
public static System.Func<System.Object, System.Object> GetCastMethodDelegate(System.Type from, System.Type to, System.Boolean requireImplicitCast);
```

- `public static GetCastMethodDelegate<TFrom, TTo>(System.Boolean requireImplicitCast = False) : System.Func<TFrom, TTo>`  

```csharp
public static System.Func<TFrom, TTo> GetCastMethodDelegate<TFrom, TTo>(System.Boolean requireImplicitCast);
```

- `public static GetCompilableNiceFullName(System.Type type) : System.String`  

```csharp
public static System.String GetCompilableNiceFullName(System.Type type);
```

- `public static GetCompilableNiceName(System.Type type) : System.String`  

```csharp
public static System.String GetCompilableNiceName(System.Type type);
```

- `public static GetCustomAttribute<T>(System.Type type, System.Boolean inherit) : T`  

```csharp
public static T GetCustomAttribute<T>(System.Type type, System.Boolean inherit);
```

- `public static GetCustomAttribute<T>(System.Type type) : T`  

```csharp
public static T GetCustomAttribute<T>(System.Type type);
```

- `public static GetCustomAttributes<T>(System.Type type) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetCustomAttributes<T>(System.Type type);
```

- `public static GetCustomAttributes<T>(System.Type type, System.Boolean inherit) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetCustomAttributes<T>(System.Type type, System.Boolean inherit);
```

- `public static GetEnumBitmask(System.Object value, System.Type enumType) : System.UInt64`  

```csharp
public static System.UInt64 GetEnumBitmask(System.Object value, System.Type enumType);
```

- `public static GetEqualityComparerDelegate<T>() : System.Func<T, T, System.Boolean>`  

```csharp
public static System.Func<T, T, System.Boolean> GetEqualityComparerDelegate<T>();
```

- `public static GetGenericBaseType(System.Type type, System.Type baseType) : System.Type`  

```csharp
public static System.Type GetGenericBaseType(System.Type type, System.Type baseType);
```

- `public static GetGenericBaseType(System.Type type, System.Type baseType, System.Int32& depthCount) : System.Type`  

```csharp
public static System.Type GetGenericBaseType(System.Type type, System.Type baseType, System.Int32& depthCount);
```

- `public static GetGenericConstraintsString(System.Type type, System.Boolean useFullTypeNames = False) : System.String`  

```csharp
public static System.String GetGenericConstraintsString(System.Type type, System.Boolean useFullTypeNames);
```

- `public static GetGenericParameterConstraintsString(System.Type type, System.Boolean useFullTypeNames = False) : System.String`  

```csharp
public static System.String GetGenericParameterConstraintsString(System.Type type, System.Boolean useFullTypeNames);
```

- `public static GetInheritanceDistance(System.Type type, System.Type baseType) : System.Int32`  

```csharp
public static System.Int32 GetInheritanceDistance(System.Type type, System.Type baseType);
```

- `public static GetMemberValue(System.Reflection.MemberInfo member, System.Object obj) : System.Object`  

```csharp
public static System.Object GetMemberValue(System.Reflection.MemberInfo member, System.Object obj);
```

- `public static GetNiceFullName(System.Type type) : System.String`  

```csharp
public static System.String GetNiceFullName(System.Type type);
```

- `public static GetNiceName(System.Type type) : System.String`  

```csharp
public static System.String GetNiceName(System.Type type);
```

- `public static GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op, System.Type leftOperand, System.Type rightOperand) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op, System.Type leftOperand, System.Type rightOperand);
```

- `public static GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op);
```

- `public static GetOperatorMethods(System.Type type, Colossal.OdinSerializer.Utilities.Operator op) : System.Reflection.MethodInfo[]`  

```csharp
public static System.Reflection.MethodInfo[] GetOperatorMethods(System.Type type, Colossal.OdinSerializer.Utilities.Operator op);
```

- `public static GetReturnType(System.Reflection.MemberInfo memberInfo) : System.Type`  

```csharp
public static System.Type GetReturnType(System.Reflection.MemberInfo memberInfo);
```

- `internal static HasCastDefined(System.Type from, System.Type to, System.Boolean requireImplicitCast) : System.Boolean`  

```csharp
internal static System.Boolean HasCastDefined(System.Type from, System.Type to, System.Boolean requireImplicitCast);
```

- `public static HasParamaters(System.Reflection.MethodInfo methodInfo, System.Collections.Generic.IList<System.Type> paramTypes, System.Boolean inherit = True) : System.Boolean`  

```csharp
public static System.Boolean HasParamaters(System.Reflection.MethodInfo methodInfo, System.Collections.Generic.IList<System.Type> paramTypes, System.Boolean inherit);
```

- `public static ImplementsOpenGenericClass(System.Type candidateType, System.Type openGenericType) : System.Boolean`  

```csharp
public static System.Boolean ImplementsOpenGenericClass(System.Type candidateType, System.Type openGenericType);
```

- `public static ImplementsOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType) : System.Boolean`  

```csharp
public static System.Boolean ImplementsOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType);
```

- `public static ImplementsOpenGenericType(System.Type candidateType, System.Type openGenericType) : System.Boolean`  

```csharp
public static System.Boolean ImplementsOpenGenericType(System.Type candidateType, System.Type openGenericType);
```

- `public static ImplementsOrInherits(System.Type type, System.Type to) : System.Boolean`  

```csharp
public static System.Boolean ImplementsOrInherits(System.Type type, System.Type to);
```

- `public static InheritsFrom<TBase>(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean InheritsFrom<TBase>(System.Type type);
```

- `public static InheritsFrom(System.Type type, System.Type baseType) : System.Boolean`  

```csharp
public static System.Boolean InheritsFrom(System.Type type, System.Type baseType);
```

- `public static IsCastableTo(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Boolean`  

```csharp
public static System.Boolean IsCastableTo(System.Type from, System.Type to, System.Boolean requireImplicitCast);
```

- `public static IsDefined<T>(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsDefined<T>(System.Type type);
```

- `public static IsDefined<T>(System.Type type, System.Boolean inherit) : System.Boolean`  

```csharp
public static System.Boolean IsDefined<T>(System.Type type, System.Boolean inherit);
```

- `public static IsFullyConstructedGenericType(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsFullyConstructedGenericType(System.Type type);
```

- `public static IsNullableType(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsNullableType(System.Type type);
```

- `public static IsValidIdentifier(System.String identifier) : System.Boolean`  

```csharp
public static System.Boolean IsValidIdentifier(System.String identifier);
```

- `private static IsValidIdentifierPartCharacter(System.Char c) : System.Boolean`  

```csharp
private static System.Boolean IsValidIdentifierPartCharacter(System.Char c);
```

- `private static IsValidIdentifierStartCharacter(System.Char c) : System.Boolean`  

```csharp
private static System.Boolean IsValidIdentifierStartCharacter(System.Char c);
```

- `private static QuaternionEqualityComparer(UnityEngine.Quaternion a, UnityEngine.Quaternion b) : System.Boolean`  

```csharp
private static System.Boolean QuaternionEqualityComparer(UnityEngine.Quaternion a, UnityEngine.Quaternion b);
```

- `public static SafeGetCustomAttributes(System.Reflection.Assembly assembly, System.Type type, System.Boolean inherit) : System.Object[]`  

```csharp
public static System.Object[] SafeGetCustomAttributes(System.Reflection.Assembly assembly, System.Type type, System.Boolean inherit);
```

- `public static SafeGetTypes(System.Reflection.Assembly assembly) : System.Type[]`  

```csharp
public static System.Type[] SafeGetTypes(System.Reflection.Assembly assembly);
```

- `public static SafeIsDefined(System.Reflection.Assembly assembly, System.Type attribute, System.Boolean inherit) : System.Boolean`  

```csharp
public static System.Boolean SafeIsDefined(System.Reflection.Assembly assembly, System.Type attribute, System.Boolean inherit);
```

- `public static SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value) : System.Void`  

```csharp
public static System.Void SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value);
```

- `public static TryInferGenericParameters(System.Type genericTypeDefinition, System.Type[]& inferredParams, System.Type[] knownParameters) : System.Boolean`  

```csharp
public static System.Boolean TryInferGenericParameters(System.Type genericTypeDefinition, System.Type[]& inferredParams, System.Type[] knownParameters);
```

- `private static TypeNameGauntlet(System.Type type) : System.String`  

```csharp
private static System.String TypeNameGauntlet(System.Type type);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.TypeExtensions+<>c__37<T>`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<>c__DisplayClass31_0`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<>c__DisplayClass47_0`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<>c__DisplayClass48_0`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<GetAllMembers>d__49`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<GetAllMembers>d__50`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<GetAllMembers>d__51<T>`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<GetBaseClasses>d__55`  
- `Colossal.OdinSerializer.Utilities.TypeExtensions+<GetCustomAttributes>d__64<T>`  

