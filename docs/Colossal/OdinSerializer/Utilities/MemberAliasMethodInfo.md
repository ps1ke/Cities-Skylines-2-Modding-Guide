# Colossal.OdinSerializer.Utilities.MemberAliasMethodInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.MethodInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Fields

- `private System.Reflection.MethodInfo aliasedMethod`  
- `private System.String mangledName`  
- `private static const System.String FAKE_NAME_SEPARATOR_STRING`  

## Properties

- `public System.Reflection.MethodInfo AliasedMethod { get }`  
- `public System.Reflection.ICustomAttributeProvider ReturnTypeCustomAttributes { get }`  
- `public System.RuntimeMethodHandle MethodHandle { get }`  
- `public System.Reflection.MethodAttributes Attributes { get }`  
- `public System.Type ReturnType { get }`  
- `public System.Type DeclaringType { get }`  
- `public System.String Name { get }`  
- `public System.Type ReflectedType { get }`  

## Constructors

- `public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix)`  
- `public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix, System.String separatorString)`  

## Methods

- `public virtual GetBaseDefinition() : System.Reflection.MethodInfo`  
- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  
- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  
- `public virtual GetMethodImplementationFlags() : System.Reflection.MethodImplAttributes`  
- `public virtual GetParameters() : System.Reflection.ParameterInfo[]`  
- `public virtual Invoke(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] parameters, System.Globalization.CultureInfo culture) : System.Object`  
- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  

