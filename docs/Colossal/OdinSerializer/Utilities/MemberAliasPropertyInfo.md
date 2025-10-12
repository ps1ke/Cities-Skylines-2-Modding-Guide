# Colossal.OdinSerializer.Utilities.MemberAliasPropertyInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.PropertyInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Fields

- `private System.Reflection.PropertyInfo aliasedProperty`  
- `private System.String mangledName`  
- `private static const System.String FakeNameSeparatorString`  

## Properties

- `public System.Reflection.PropertyInfo AliasedProperty { get }`  
- `public System.Reflection.Module Module { get }`  
- `public System.Int32 MetadataToken { get }`  
- `public System.String Name { get }`  
- `public System.Type DeclaringType { get }`  
- `public System.Type ReflectedType { get }`  
- `public System.Type PropertyType { get }`  
- `public System.Reflection.PropertyAttributes Attributes { get }`  
- `public System.Boolean CanRead { get }`  
- `public System.Boolean CanWrite { get }`  

## Constructors

- `public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix)`  
- `public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix, System.String separatorString)`  

## Methods

- `public virtual GetAccessors(System.Boolean nonPublic) : System.Reflection.MethodInfo[]`  
- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  
- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  
- `public virtual GetGetMethod(System.Boolean nonPublic) : System.Reflection.MethodInfo`  
- `public virtual GetIndexParameters() : System.Reflection.ParameterInfo[]`  
- `public virtual GetSetMethod(System.Boolean nonPublic) : System.Reflection.MethodInfo`  
- `public virtual GetValue(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture) : System.Object`  
- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  
- `public virtual SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture) : System.Void`  

