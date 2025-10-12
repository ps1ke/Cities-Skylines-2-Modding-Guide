# Colossal.Localization.LocalizationValidation

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Text.RegularExpressions.Regex kIdentifierPlain`  
- `private static readonly System.Text.RegularExpressions.Regex kIdentifierHashed`  
- `private static readonly System.Text.RegularExpressions.Regex kIdentifierIndexed`  
- `private static readonly System.Text.RegularExpressions.Regex kIdentifierHashedIndexed`  
- `private static readonly System.Text.RegularExpressions.Regex kSubstitutePlaceholder`  

## Methods

- `private static GetArgNames(System.String text) : System.Collections.Generic.List<System.String>`  
- `public static ParseEntries(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries, Colossal.Logging.ILog log) : System.Collections.Generic.List<Colossal.Localization.LocalizationEntry>`  
- `public static ParseEntry(System.Collections.Generic.KeyValuePair<System.String, System.String> entry) : Colossal.Localization.LocalizationEntry`  
- `private static ValidateArgNames(System.Collections.Generic.List<System.String> argNames, System.Collections.Generic.List<System.String> expected) : System.Boolean`  
- `public static ValidateEntries(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, Colossal.Logging.ILog log, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Void`  
- `private static ValidateEntry(System.String localeID, Colossal.Localization.LocalizationEntry entry, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> existingEntries, Colossal.Logging.ILog log) : System.Boolean`  
- `private static ValidateIndices(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> group, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, Colossal.Logging.ILog log) : System.Void`  
- `public static ValidateTranslation(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> referenceEntries, Colossal.Logging.ILog log) : System.Void`  

