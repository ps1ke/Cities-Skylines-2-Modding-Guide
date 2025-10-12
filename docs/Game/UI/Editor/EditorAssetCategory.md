# Game.UI.Editor.EditorAssetCategory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_SubCategories`  
- `private System.String <id>k__BackingField`  
- `private System.String <path>k__BackingField`  
- `private Unity.Entities.EntityQuery <entityQuery>k__BackingField`  
- `private Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter <filter>k__BackingField`  
- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> <exclude>k__BackingField`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> <include>k__BackingField`  
- `private System.String <icon>k__BackingField`  
- `private System.Boolean <includeChildCategories>k__BackingField`  
- `private System.Boolean <defaultSelection>k__BackingField`  
- `public static readonly System.String kNameFormat`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.EditorAssetCategory> subCategories { get }`  
- `public System.String id { get; set }`  
- `public System.String path { get; set }`  
- `public Unity.Entities.EntityQuery entityQuery { get; set }`  
- `public Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter filter { get; set }`  
- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> exclude { private get; private set }`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> include { private get; private set }`  
- `public System.String icon { get; set }`  
- `public System.Boolean includeChildCategories { get; set }`  
- `public System.Boolean defaultSelection { get; set }`  

## Constructors

- `public EditorAssetCategory()`  

## Methods

- `public AddEntity(Unity.Entities.Entity entity) : System.Void`  
- `public AddExclusion(Unity.Entities.Entity entity) : System.Void`  
- `public AddSubCategory(Game.UI.Editor.EditorAssetCategory category) : System.Void`  
- `private CheckFilters(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  
- `public GetEntities(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Collections.Generic.IEnumerable<Unity.Entities.Entity>`  
- `public GetLocalizationID() : System.String`  
- `public GetPrefabs(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase>`  
- `public IsEmpty(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Boolean`  
- `public ToHierarchyItem(System.Int32 level = 0) : Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>`  

## Nested types

- `Game.UI.Editor.EditorAssetCategory+<GetEntities>d__42`  

