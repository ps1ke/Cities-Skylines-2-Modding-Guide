# Colossal.OdinSerializer.Utilities.TypeExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly System.Func<System.Single, System.Single, System.Boolean> FloatEqualityComparerFunc`  
- `private static readonly System.Func<System.Double, System.Double, System.Boolean> DoubleEqualityComparerFunc`  
- `private static readonly System.Func<UnityEngine.Quaternion, UnityEngine.Quaternion, System.Boolean> QuaternionEqualityComparerFunc`  
- `private static readonly System.Object GenericConstraintsSatisfaction_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionInferredParameters`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> GenericConstraintsSatisfactionResolvedMap`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionProcessedParams`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> GenericConstraintsSatisfactionTypesToCheck`  
- `private static readonly System.Collections.Generic.List<System.Type> GenericConstraintsSatisfactionTypesToCheck_ToAdd`  
- `private static readonly System.Type GenericListInterface`  
- `private static readonly System.Type GenericCollectionInterface`  
- `private static readonly System.Object WeaklyTypedTypeCastDelegates_LOCK`  
- `private static readonly System.Object StronglyTypedTypeCastDelegates_LOCK`  
- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Func<System.Object, System.Object>> WeaklyTypedTypeCastDelegates`  
- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, System.Type, System.Delegate> StronglyTypedTypeCastDelegates`  
- `private static readonly System.Type[] TwoLengthTypeArray_Cached`  
- `private static readonly System.Collections.Generic.Stack<System.Type> GenericArgumentsContainsTypes_ArgsToCheckCached`  
- `private static System.Collections.Generic.HashSet<System.String> ReservedCSharpKeywords`  
- `public static readonly System.Collections.Generic.Dictionary<System.String, System.String> TypeNameAlternatives`  
- `private static readonly System.Object CachedNiceNames_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> CachedNiceNames`  
- `private static readonly System.Type VoidPointerType`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.HashSet<System.Type>> PrimitiveImplicitCasts`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> ExplicitCastIntegrals`  

## Methods

- `public static AreGenericConstraintsSatisfiedBy(System.Type genericType, System.Type[] parameters) : System.Boolean`  
- `public static AreGenericConstraintsSatisfiedBy(System.Reflection.MethodBase genericMethod, System.Type[] parameters) : System.Boolean`  
- `public static AreGenericConstraintsSatisfiedBy(System.Type[] definitions, System.Type[] parameters) : System.Boolean`  
- `private static CreateNiceName(System.Type type) : System.String`  
- `private static DoubleEqualityComparer(System.Double a, System.Double b) : System.Boolean`  
- `private static FloatEqualityComparer(System.Single a, System.Single b) : System.Boolean`  
- `public static GenericArgumentsContainsTypes(System.Type type, System.Type[] types) : System.Boolean`  
- `public static GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType) : System.Boolean`  
- `private static GenericParameterIsFulfilledBy(System.Type genericParameterDefinition, System.Type parameterType, System.Collections.Generic.Dictionary<System.Type, System.Type> resolvedMap, System.Collections.Generic.HashSet<System.Type> processedParams = null) : System.Boolean`  
- `public static GetAllMembers(System.Type type, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  
- `public static GetAllMembers(System.Type type, System.String name, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  
- `public static GetAllMembers<T>(System.Type type, System.Reflection.BindingFlags flags = Default) : System.Collections.Generic.IEnumerable<T>`  
- `public static GetArgumentsOfInheritedOpenGenericClass(System.Type candidateType, System.Type openGenericType) : System.Type[]`  
- `public static GetArgumentsOfInheritedOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType) : System.Type[]`  
- `public static GetArgumentsOfInheritedOpenGenericType(System.Type candidateType, System.Type openGenericType) : System.Type[]`  
- `public static GetAttribute<T>(System.Type type, System.Boolean inherit) : T`  
- `public static GetBaseClasses(System.Type type, System.Boolean includeSelf = False) : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static GetBaseTypes(System.Type type, System.Boolean includeSelf = False) : System.Collections.Generic.IEnumerable<System.Type>`  
- `private static GetCachedNiceName(System.Type type) : System.String`  
- `public static GetCastMethod(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Reflection.MethodInfo`  
- `public static GetCastMethodDelegate(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Func<System.Object, System.Object>`  
- `public static GetCastMethodDelegate<TFrom, TTo>(System.Boolean requireImplicitCast = False) : System.Func<TFrom, TTo>`  
- `public static GetCompilableNiceFullName(System.Type type) : System.String`  
- `public static GetCompilableNiceName(System.Type type) : System.String`  
- `public static GetCustomAttribute<T>(System.Type type, System.Boolean inherit) : T`  
- `public static GetCustomAttribute<T>(System.Type type) : T`  
- `public static GetCustomAttributes<T>(System.Type type) : System.Collections.Generic.IEnumerable<T>`  
- `public static GetCustomAttributes<T>(System.Type type, System.Boolean inherit) : System.Collections.Generic.IEnumerable<T>`  
- `public static GetEnumBitmask(System.Object value, System.Type enumType) : System.UInt64`  
- `public static GetEqualityComparerDelegate<T>() : System.Func<T, T, System.Boolean>`  
- `public static GetGenericBaseType(System.Type type, System.Type baseType) : System.Type`  
- `public static GetGenericBaseType(System.Type type, System.Type baseType, System.Int32& depthCount) : System.Type`  
- `public static GetGenericConstraintsString(System.Type type, System.Boolean useFullTypeNames = False) : System.String`  
- `public static GetGenericParameterConstraintsString(System.Type type, System.Boolean useFullTypeNames = False) : System.String`  
- `public static GetInheritanceDistance(System.Type type, System.Type baseType) : System.Int32`  
- `public static GetMemberValue(System.Reflection.MemberInfo member, System.Object obj) : System.Object`  
- `public static GetNiceFullName(System.Type type) : System.String`  
- `public static GetNiceName(System.Type type) : System.String`  
- `public static GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op, System.Type leftOperand, System.Type rightOperand) : System.Reflection.MethodInfo`  
- `public static GetOperatorMethod(System.Type type, Colossal.OdinSerializer.Utilities.Operator op) : System.Reflection.MethodInfo`  
- `public static GetOperatorMethods(System.Type type, Colossal.OdinSerializer.Utilities.Operator op) : System.Reflection.MethodInfo[]`  
- `public static GetReturnType(System.Reflection.MemberInfo memberInfo) : System.Type`  
- `internal static HasCastDefined(System.Type from, System.Type to, System.Boolean requireImplicitCast) : System.Boolean`  
- `public static HasParamaters(System.Reflection.MethodInfo methodInfo, System.Collections.Generic.IList<System.Type> paramTypes, System.Boolean inherit = True) : System.Boolean`  
- `public static ImplementsOpenGenericClass(System.Type candidateType, System.Type openGenericType) : System.Boolean`  
- `public static ImplementsOpenGenericInterface(System.Type candidateType, System.Type openGenericInterfaceType) : System.Boolean`  
- `public static ImplementsOpenGenericType(System.Type candidateType, System.Type openGenericType) : System.Boolean`  
- `public static ImplementsOrInherits(System.Type type, System.Type to) : System.Boolean`  
- `public static InheritsFrom<TBase>(System.Type type) : System.Boolean`  
- `public static InheritsFrom(System.Type type, System.Type baseType) : System.Boolean`  
- `public static IsCastableTo(System.Type from, System.Type to, System.Boolean requireImplicitCast = False) : System.Boolean`  
- `public static IsDefined<T>(System.Type type) : System.Boolean`  
- `public static IsDefined<T>(System.Type type, System.Boolean inherit) : System.Boolean`  
- `public static IsFullyConstructedGenericType(System.Type type) : System.Boolean`  
- `public static IsNullableType(System.Type type) : System.Boolean`  
- `public static IsValidIdentifier(System.String identifier) : System.Boolean`  
- `private static IsValidIdentifierPartCharacter(System.Char c) : System.Boolean`  
- `private static IsValidIdentifierStartCharacter(System.Char c) : System.Boolean`  
- `private static QuaternionEqualityComparer(UnityEngine.Quaternion a, UnityEngine.Quaternion b) : System.Boolean`  
- `public static SafeGetCustomAttributes(System.Reflection.Assembly assembly, System.Type type, System.Boolean inherit) : System.Object[]`  
- `public static SafeGetTypes(System.Reflection.Assembly assembly) : System.Type[]`  
- `public static SafeIsDefined(System.Reflection.Assembly assembly, System.Type attribute, System.Boolean inherit) : System.Boolean`  
- `public static SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value) : System.Void`  
- `public static TryInferGenericParameters(System.Type genericTypeDefinition, System.Type[]& inferredParams, System.Type[] knownParameters) : System.Boolean`  
- `private static TypeNameGauntlet(System.Type type) : System.String`  

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

