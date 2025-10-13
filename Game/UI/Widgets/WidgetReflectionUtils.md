# Game.UI.Widgets.WidgetReflectionUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class WidgetReflectionUtils
{
    private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy;

    public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>();
    public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject);
    public static System.Reflection.MemberInfo GetListElementLabelMember(System.Type type);
    public static System.Type GetListElementType(System.Type memberType);
    private static System.Boolean IsGenericListInterface(System.Type type);
    public static System.Boolean IsListType(System.Type memberType);
    public static System.String NicifyVariableName(System.String name);
}
```


## Fields

- `private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy`  

```csharp
private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy;
```


## Methods

- `public static CreateFieldBuilder<T, U>() : Game.UI.Widgets.FieldBuilder`  

```csharp
public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>();
```

- `public static CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject);
```

- `public static GetListElementLabelMember(System.Type type) : System.Reflection.MemberInfo`  

```csharp
public static MemberInfo GetListElementLabelMember(Type type)
	{
		return FormatterUtilities.GetSerializableMembers(type, kListElementLabelPolicy).FirstOrDefault();
	}
```

- `public static GetListElementType(System.Type memberType) : System.Type`  

```csharp
[CanBeNull]
	public static Type GetListElementType(Type memberType)
	{
		if (memberType.IsArray)
		{
			return memberType.GetElementType();
		}
		Type type = memberType.GetInterfaces().FirstOrDefault(IsGenericListInterface);
		if (type != null)
		{
			return type.GenericTypeArguments[0];
		}
		return null;
	}
```

- `private static IsGenericListInterface(System.Type type) : System.Boolean`  

```csharp
private static bool IsGenericListInterface(Type type)
	{
		if (type.IsGenericType)
		{
			return type.GetGenericTypeDefinition() == typeof(IList<>);
		}
		return false;
	}
```

- `public static IsListType(System.Type memberType) : System.Boolean`  

```csharp
public static bool IsListType(Type memberType)
	{
		if (!memberType.IsArray)
		{
			if (typeof(IList).IsAssignableFrom(memberType))
			{
				return memberType.GetInterfaces().Any(IsGenericListInterface);
			}
			return false;
		}
		return true;
	}
```

- `public static NicifyVariableName(System.String name) : System.String`  

```csharp
public static string NicifyVariableName(string name)
	{
		if (name == null)
		{
			return string.Empty;
		}
		if (name.StartsWith("m_"))
		{
			name = name.Substring(2);
		}
		else if (name.StartsWith("Get"))
		{
			name = name.Substring(3);
		}
		name = Regex.Replace(name, "\\B([A-Z][a-z])", " $1");
		name = Regex.Replace(name, "([^A-Z\\s])([A-Z])", "$1 $2");
		name = Regex.Replace(name, "(?<![\\d\\s]|\\dx|\\d-)(\\d)", " $1");
		name = Regex.Replace(name, "^([a-z])", (Match match) => match.Value.ToUpperInvariant());
		return name;
	}
```


## Nested types

- `Game.UI.Widgets.WidgetReflectionUtils+<>c`  
- `Game.UI.Widgets.WidgetReflectionUtils+<>c__3<T, U>`  
- `Game.UI.Widgets.WidgetReflectionUtils+<>c__DisplayClass4_0<T, U>`  

