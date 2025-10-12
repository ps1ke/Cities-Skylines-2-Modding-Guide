# Colossal.OdinSerializer.Utilities.MemberAliasFieldInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.FieldInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Fields

- `private System.Reflection.FieldInfo aliasedField`  
- `private System.String mangledName`  
- `private static const System.String FAKE_NAME_SEPARATOR_STRING`  

## Properties

- `public System.Reflection.FieldInfo AliasedField { get }`  
- `public System.Reflection.Module Module { get }`  
- `public System.Int32 MetadataToken { get }`  
- `public System.String Name { get }`  
- `public System.Type DeclaringType { get }`  
- `public System.Type ReflectedType { get }`  
- `public System.Type FieldType { get }`  
- `public System.RuntimeFieldHandle FieldHandle { get }`  
- `public System.Reflection.FieldAttributes Attributes { get }`  

## Constructors

- `public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix)`  
- `public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix, System.String separatorString)`  

## Methods

- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  
- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  
- `public virtual GetValue(System.Object obj) : System.Object`  
- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  
- `public virtual SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Globalization.CultureInfo culture) : System.Void`  

