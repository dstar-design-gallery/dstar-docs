# Terms & Concepts

***

<img src="https://raw.githubusercontent.com/dstar-design-gallery/dstar-docs/master/media/DStarIntroduction.gif" 
    width="400" />

*parametric modeller to the right, DStar UI to the left*

<br>

| element | description |
|---------|-------------|
| canvas | All collections are rendered within a top level grid layout. In the interface, this corresponds to the whitespace on the background. The Canvas extends indefinitely along the X+ and Y+ axes. Holding middle mouse button while panning provides fast transition. |
| alternative | Alternatives are represented by different views in the UI. *Thumbnail* View represents them as icons, while *Parallel View* as paths and etc. Alternatives can be selected, copied, pasted, edited or deleted. Each alternative is unique in a collection, but may appear many times across collections. Highlighting an alternative in one collection highlights it in all collections. |
| collection | Collections group alternatives. They also provide operations that apply to some or all alternatives within them. They can be named, resized, hidden, as well as copied, pasted or deleted. They embody *views* i.e. can represent alternatives in different view types (currently: *thumbnail*, *parallel*, *list*). |
| view | Logically one and the some item (alternatives, collections) may be represented with distinct items on the UI. These distinct representations are said to be views of an alternative/collection. Views can appear in thumbnail, parallel or list forms. |
| reference | Distinct representations of an alternative/collection refer to each other (by sharing the same reference ID). An operation that apply on one alternative/collection view applies to all alternatives/collections that it refers to. An alternative/collection can be *copied as reference*. |
| clone | Cloning an alternative/collection creates a new one with the same properties, but it severs the reference between them. Operations apply to cloned alternatives/collections can be distinct. |
| select | Selection is cumulative, and selecting a new item appends it to the selection list. Alternatives and collections are kept in separate lists. Several operations apply to selection lists, such as copy, paste, edit and delete. |
| model | Each alternative corresponds to an aspect of a model i.e. a representation of the model that abstracts its properties. Models are directly manipulated by the operations on the front-end (*Gallery*), and updates the alternative on the front-end in return. |
