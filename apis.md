# API Documentation

***

## Models

### User
<pre>
	@User{
		id: @string,
		username: @string,
		password: @string,
		email: @string
	}
</pre>

### Project

<pre>
	@Project{
		id: @string,
		userIds: array(@string),
		primary: @string,
		name: @string,
		image: @string,
		description: @string,
		db_name: @string
	}
</pre>

### Layout

<pre>
	@Layout{
		w : @int,
		h : @int,
		x : @int,
		y : @int,
		i : @string,
		minW : @int,
		minH : @int,
		moved : boolean,
		static : boolean
	}
</pre>

### Collection

<pre>
	@Collection{
		refId : @string
		viewId: @string,
		altsid : array(@string),
		collectionName : @string,
		text : @string,
		tags : array(@string),
		viewType : Enum{1:"file view", 2:"parallel view", 3:"list view"},
		isSinked: @boolean,
		err : @boolean,
		status : Enum{"ACTIVE":"alt exists", "DELETED":"alt was removed"}
		collectionNameView: @string
	}
</pre>

<pre>
	@CollectionWithLayout{
		refId : @string
		viewId: @string,
		altsid : array(@string),
		collectionName : @string,
		text : @string,
		tags : array(@string),
		viewType : Enum{1:"file view", 2:"parallel view", 3:"list view"},
		isSinked: @boolean,
		err : @boolean,
		status : Enum{"ACTIVE":"alt exists", "DELETED":"alt was removed"}
		collectionNameView: @string,
		layout: <a href="#/apis?id=layout">@Layout</a>
	}
</pre>

<pre>
	@CollectionWithKeySets{
		refId : @string
		viewId: @string,
		altsid : array(@string),
		collectionName : @string,
		text : @string,
		tags : array(@string),
		viewType : Enum{1:"file view", 2:"parallel view", 3:"list view"},
		isSinked: @boolean,
		err : @boolean,
		status : Enum{"ACTIVE":"alt exists", "DELETED":"alt was removed"}
		collectionNameView: @string,
		keySets:array(@string),
		isInput:array(@boolean)
	}
</pre>

### Attribute

<pre>
	@Attribute{
		key: @string,
	    value: @int,
		typeName : Enum{},
	    isInput: @boolean,
	    ordered : @boolean,
		max : @int,
		min : @int,
		step : @int
	}
</pre>

### Alternative

<pre>
	@Alternative{
		_id : @string,
		refId : @string,
		viewId: @string,
		collectionViewId: @string,
		collectionRefId: @string,
		image: @string,
		xml: @string,
		gltf: @string,
		geometry: @string,
		collectionName: @string,
		RhinoFile: @string,
		tags: array(@string),
		attributes: array(<a href="#/apis?id=attributes">@Attributes</a>),
		history: array(@string),
		parents: array(@string),
		status : Enum{"ACTIVE":"alt exists", "DELETED":"alt was removed"}
	}
</pre>

<pre>
	AlternativeDetailed{
		_id : @string,
		refId : @string,
		viewId: @string,
		collectionViewId: @string,
		collectionRefId: @string,
		image: @string,
		xml: @string,
		gltf: @string,
		geometry: @string,
		collectionName: @string,
		RhinoFile: @string,
		tags: array(@string),
		params: @Dictionary(input:value),
		outputs: @Dictionary(output:value),
	}
</pre>

<pre>
	@AlternativeShort{
		refId : @string,
		viewId: @string,
		image: @string
	}
</pre>

### File
<pre>
	@File{
		id : @string,
		refId : @string,
		filename : @string,
		data : @string,
		type : @string,
		err : @boolean
	}
</pre>

## APIs

### Users

#### Login
<pre>
	<b>Url</b>: /user/login
	<b>Method</b>: POST	
	<b>Description</b>: it logs in to an existing account
	<b>Headers</b>:{
	}
	<b>Body</b>:{
		username:@string,
		password:@string
	}
	<b>Response</b>:{
		success:@boolean,		
		user:<a href="#/apis?id=users">@User</a>
	}
</pre>
	

#### Registere
<pre>
	<b>Url</b>: /user/register
	<b>Method</b>: POST	
	<b>Description</b>: it creates a new account
	<b>Headers</b>:{
	}
	<b>Body</b>:{
		username:@string,
		password:@string
	}
	<b>Response</b>:{
		success:@boolean,		
		user:<a href="#/apis?id=users">@User</a>
	}
</pre>

### Projects

#### Fetch
<pre>
	<b>Url</b>: /project
	<b>Method</b>: GET	
	<b>Description</b>: it fethes all the projects
	<b>Headers</b>:{
		userid:@string
	}
	<b>Body</b>:{
	}
	<b>Response</b>:{
		success:@boolean,		
		projects:array(<a href="#/apis?id=projects">@Project</a>),
		db_loaded:@boolean
	}
</pre>

#### Create
<pre>
	<b>Url</b>: /project
	<b>Method</b>: POST	
	<b>Description</b>: it creates a new projecct
	<b>Headers</b>:{
		userid:@string
	}
	<b>Body</b>:{
		name:@string,
		description:@string
	}
	<b>Response</b>:{
		success:@boolean,		
		projects:array(<a href="#/apis?id=projects">@Project</a>),
		db_loaded:@boolean
	}
</pre>

#### Select
<pre>
	<b>Url</b>: /project/select
	<b>Method</b>: POST	
	<b>Description</b>: it selects a new projecct
	<b>Headers</b>:{
		userid:@string
	}
	<b>Body</b>:{
		id:@string
	}
	<b>Response</b>:{
		success:@boolean,		
		project:<a href="#/apis?id=projects">@Project</a>
	}
</pre>

#### Update (NIY)
<pre>
	<b>Url</b>: /project
	<b>Method</b>: PUT	
	<b>Description</b>: it updates a new projecct
	<b>Headers</b>:{
		userid:@string
	}
	<b>Body</b>:{
		projects:array(<a href="#/apis?id=projects">@Project</a>)
	}
	<b>Response</b>:{
		success:@boolean,		
		projects:array(<a href="#/apis?id=projects">@Project</a>)
	}
</pre>

### Layout

<pre>
	<b>Url</b>: /layout
	<b>Method</b>: Get	
	<b>Description</b>: it fetches all the layouts
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:{
	}
	<b>Response</b>:{
		layout:array(<a href="#/apis?id=layout">@Layout</a>)
	}
</pre>

### Collections

#### Fetch
<pre>
	<b>Url</b>: /collections
	<b>Method</b>: GET	
	<b>Description</b>: it fetches all the collections or the specified ones
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>: array(@string) (optional)
	<b>Response</b>:array(<a href="#/apis?id=collection">@CollectionWithKeySets</a>)
</pre>

#### Create
<pre>
	<b>Url</b>: /collections
	<b>Method</b>: POST	
	<b>Description</b>: it creates a new collection or the specified number of collections
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:{
		numberOfCollections:@int
	}
	<b>Response</b>:array(<a href="#/apis?id=collection">@Collection</a>)
</pre>

#### Update
<pre>
	<b>Url</b>: /collections
	<b>Method</b>: PUT	
	<b>Description</b>: it updates specified collections
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(<a href="#/apis?id=collection">@Collection</a>)
	<b>Response</b>:array(<a href="#/apis?id=collection">@collection</a>)
</pre>

#### Renaming
<pre>
	<b>Url</b>: /collections/renaming
	<b>Method</b>: PUT	
	<b>Description</b>: it renames specified collections
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(<a href="#/apis?id=collection">@Collection</a>)
	<b>Response</b>:array(<a href="#/apis?id=collection">@collection</a>)
</pre>

#### Remove
<pre>
	<b>Url</b>: /collections
	<b>Method</b>: DELETE	
	<b>Description</b>: it removes specified collections
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(@int)
	<b>Response</b>:{
		success:@boolean
	}
</pre>

#### Copy With Ref
<pre>
	<b>Url</b>: /collections/copy/ref
	<b>Method</b>: POST	
	<b>Description</b>: it copies collections with refrence to the original collections
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(<a href="#/apis?id=collection">@CollectionWithLayout</a>)
	<b>Response</b>:array({
		alternatives:array(<a href="#/apis?id=alternative">@AlternativeDetailed</a>),
		collections:array(<a href="#/apis?id=collection">@CollectionWithKeySets</a>)
	})
</pre>

#### Clone
<pre>
	<b>Url</b>: /collections/clone
	<b>Method</b>: POST	
	<b>Description</b>: it clones collections with no refrence to the original collections. The alternatives inside the collection will have refrence to the original alternatives.
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(<a href="#/apis?id=collection">@CollectionWithLayout</a>)
	<b>Response</b>:array({
		alternatives:array(<a href="#/apis?id=alternative">@AlternativeDetailed</a>),
		collections:array(<a href="#/apis?id=collection">@CollectionWithKeySets</a>)
	})
</pre>

#### Deep Clone
<pre>
	<b>Url</b>: /collections/clone/deep
	<b>Method</b>: POST	
	<b>Description</b>: it clones collections with no refrence to the original collections. The alternatives inside the collection will not have refrence to the original alternatives.
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:array(<a href="#/apis?id=collection">@CollectionWithLayout</a>)
	<b>Response</b>:array({
		alternatives:array(<a href="#/apis?id=alternative">@AlternativeDetailed</a>),
		collections:array(<a href="#/apis?id=collection">@CollectionWithKeySets</a>)
	})
</pre>

#### Sink
<pre>
	<b>Url</b>: /collections/sink
	<b>Method</b>: POST	
	<b>Description</b>: it puts a collection into the sink
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:{
		collectionId:@string
	}
	<b>Response</b>:{
		success:@boolean
	}
</pre>

### Alternatives
### Generative

#### Cartesian Product
<pre>
	<b>Url</b>: /computeCP
	<b>Method</b>: POST	
	<b>Description</b>: <a href="#/cp">Check the description here</a>
	<b>Headers</b>:{
		userid:@string,
		projectid:@string
	}
	<b>Body</b>:{
		collectionId:@string
	}
	<b>Response</b>:{
		success:@boolean
	}
</pre>

### Grasshopper
### Websocket

### Admin

#### Clean Database
<pre>
	<b>Url</b>: /clean-db?projectId=
	<b>Method</b>: Get	
	<b>Description</b>: it removes everything in a project 
	<b>Body</b>:{}
	<b>Response</b>:{
		success:@boolean
	}
</pre>







