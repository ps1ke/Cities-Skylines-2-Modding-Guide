# Colossal.OdinSerializer.WeakGenericCollectionFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter`  
- `private readonly System.Type ElementType`  
- `private readonly System.Reflection.PropertyInfo CountProperty`  
- `private readonly System.Reflection.MethodInfo AddMethod`  

## Constructors

- `public WeakGenericCollectionFormatter(System.Type collectionType, System.Type elementType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

