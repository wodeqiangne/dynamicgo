<!-- Code generated by gomarkdoc. DO NOT EDIT -->

# generic

```go
import "github.com/cloudwego/dynamicgo/thrift/generic"
```

## Index

- [Variables](<#variables>)
- [func DescriptorToPathNode(desc *thrift.TypeDescriptor, root *PathNode, opts *Options) error](<#func-descriptortopathnode>)
- [func FreePathNode(p *PathNode)](<#func-freepathnode>)
- [func GetDescByPath(desc *thrift.TypeDescriptor, path ...Path) (ret *thrift.TypeDescriptor, err error)](<#func-getdescbypath>)
- [type Node](<#type-node>)
  - [func NewNode(t thrift.Type, src []byte) Node](<#func-newnode>)
  - [func NewNodeBinary(val []byte) Node](<#func-newnodebinary>)
  - [func NewNodeBool(val bool) Node](<#func-newnodebool>)
  - [func NewNodeByte(val byte) Node](<#func-newnodebyte>)
  - [func NewNodeDouble(val float64) Node](<#func-newnodedouble>)
  - [func NewNodeInt16(val int16) Node](<#func-newnodeint16>)
  - [func NewNodeInt32(val int32) Node](<#func-newnodeint32>)
  - [func NewNodeInt64(val int64) Node](<#func-newnodeint64>)
  - [func NewNodeString(val string) Node](<#func-newnodestring>)
  - [func (self Node) Binary() ([]byte, error)](<#func-node-binary>)
  - [func (self Node) Bool() (bool, error)](<#func-node-bool>)
  - [func (self Node) Byte() (byte, error)](<#func-node-byte>)
  - [func (self *Node) Check() error](<#func-node-check>)
  - [func (self Node) Children(out *[]PathNode, recurse bool, opts *Options) (err error)](<#func-node-children>)
  - [func (self Node) ElemType() thrift.Type](<#func-node-elemtype>)
  - [func (self Node) ErrCode() meta.ErrCode](<#func-node-errcode>)
  - [func (self Node) Error() string](<#func-node-error>)
  - [func (self Node) Field(id thrift.FieldID) (v Node)](<#func-node-field>)
  - [func (self Node) Fields(ids []PathNode, opts *Options) (err error)](<#func-node-fields>)
  - [func (self Node) Float64() (float64, error)](<#func-node-float64>)
  - [func (self Node) Foreach(handler func(path Path, node Node) bool, opts *Options) error](<#func-node-foreach>)
  - [func (self Node) ForeachKV(handler func(key Node, val Node) bool, opts *Options) error](<#func-node-foreachkv>)
  - [func (self Node) Fork() Node](<#func-node-fork>)
  - [func (self Node) GetByInt(key int) (v Node)](<#func-node-getbyint>)
  - [func (self Node) GetByPath(pathes ...Path) Node](<#func-node-getbypath>)
  - [func (self Node) GetByRaw(key []byte) (v Node)](<#func-node-getbyraw>)
  - [func (self Node) GetByStr(key string) (v Node)](<#func-node-getbystr>)
  - [func (self Node) GetMany(pathes []PathNode, opts *Options) error](<#func-node-getmany>)
  - [func (self Node) GetTree(tree *PathNode, opts *Options) error](<#func-node-gettree>)
  - [func (self Node) Gets(keys []PathNode, opts *Options) (err error)](<#func-node-gets>)
  - [func (self Node) Index(i int) (v Node)](<#func-node-index>)
  - [func (self Node) Indexes(ins []PathNode, opts *Options) (err error)](<#func-node-indexes>)
  - [func (self Node) Int() (int, error)](<#func-node-int>)
  - [func (self Node) IntMap(opts *Options) (map[int]interface{}, error)](<#func-node-intmap>)
  - [func (self Node) Interface(opts *Options) (interface{}, error)](<#func-node-interface>)
  - [func (self Node) InterfaceMap(opts *Options) (map[interface{}]interface{}, error)](<#func-node-interfacemap>)
  - [func (self Node) IsEmpty() bool](<#func-node-isempty>)
  - [func (self Node) IsErrNotFound() bool](<#func-node-iserrnotfound>)
  - [func (self Node) IsError() bool](<#func-node-iserror>)
  - [func (self Node) KeyType() thrift.Type](<#func-node-keytype>)
  - [func (self Node) Len() (int, error)](<#func-node-len>)
  - [func (self Node) List(opts *Options) ([]interface{}, error)](<#func-node-list>)
  - [func (self Node) Raw() []byte](<#func-node-raw>)
  - [func (self *Node) SetByPath(sub Node, path ...Path) (exist bool, err error)](<#func-node-setbypath>)
  - [func (self *Node) SetMany(pathes []PathNode, opts *Options) (err error)](<#func-node-setmany>)
  - [func (self Node) StrMap(opts *Options) (map[string]interface{}, error)](<#func-node-strmap>)
  - [func (self Node) String() (string, error)](<#func-node-string>)
  - [func (self Node) Type() thrift.Type](<#func-node-type>)
  - [func (self *Node) UnsetByPath(path ...Path) error](<#func-node-unsetbypath>)
- [type Options](<#type-options>)
- [type Path](<#type-path>)
  - [func NewPathBinKey(key []byte) Path](<#func-newpathbinkey>)
  - [func NewPathFieldId(id thrift.FieldID) Path](<#func-newpathfieldid>)
  - [func NewPathFieldName(name string) Path](<#func-newpathfieldname>)
  - [func NewPathIndex(index int) Path](<#func-newpathindex>)
  - [func NewPathIntKey(key int) Path](<#func-newpathintkey>)
  - [func NewPathStrKey(key string) Path](<#func-newpathstrkey>)
  - [func (self Path) Bin() []byte](<#func-path-bin>)
  - [func (self Path) Id() thrift.FieldID](<#func-path-id>)
  - [func (self Path) Int() int](<#func-path-int>)
  - [func (self Path) Str() string](<#func-path-str>)
  - [func (self Path) String() string](<#func-path-string>)
  - [func (self Path) ToRaw(t thrift.Type) []byte](<#func-path-toraw>)
  - [func (self Path) Type() PathType](<#func-path-type>)
  - [func (self Path) Value() interface{}](<#func-path-value>)
- [type PathNode](<#type-pathnode>)
  - [func NewPathNode() *PathNode](<#func-newpathnode>)
  - [func (self *PathNode) Assgin(recurse bool, opts *Options) error](<#func-pathnode-assgin>)
  - [func (self PathNode) Fork() PathNode](<#func-pathnode-fork>)
  - [func (self *PathNode) Load(recurse bool, opts *Options) error](<#func-pathnode-load>)
  - [func (self PathNode) Marshal(opt *Options) (out []byte, err error)](<#func-pathnode-marshal>)
  - [func (self PathNode) MarshalIntoBuffer(out *[]byte, opt *Options) error](<#func-pathnode-marshalintobuffer>)
  - [func (self *PathNode) ResetAll()](<#func-pathnode-resetall>)
  - [func (self *PathNode) ResetValue()](<#func-pathnode-resetvalue>)
- [type PathType](<#type-pathtype>)
- [type Value](<#type-value>)
  - [func NewValue(desc *thrift.TypeDescriptor, src []byte) Value](<#func-newvalue>)
  - [func (self Value) Field(id thrift.FieldID) (v Value)](<#func-value-field>)
  - [func (self Value) FieldByName(name string) (v Value)](<#func-value-fieldbyname>)
  - [func (self Value) Fork() Value](<#func-value-fork>)
  - [func (self Value) GetByInt(key int) (v Value)](<#func-value-getbyint>)
  - [func (self Value) GetByPath(pathes ...Path) Value](<#func-value-getbypath>)
  - [func (self Value) GetByStr(key string) (v Value)](<#func-value-getbystr>)
  - [func (self Value) Index(i int) (v Value)](<#func-value-index>)
  - [func (self Value) MarshalTo(to *thrift.TypeDescriptor, opts *Options) ([]byte, error)](<#func-value-marshalto>)
  - [func (self *Value) SetByPath(sub Value, path ...Path) (exist bool, err error)](<#func-value-setbypath>)
  - [func (self *Value) UnsetByPath(path ...Path) error](<#func-value-unsetbypath>)


## Variables

```go
var (
    // UseNativeSkipForGet indicates to use native.Skip (instead of go.Skip) method to skip thrift value
    // This only works for single-value searching API like GetByInt()/GetByRaw()/GetByStr()/Field()/Index()/GetByPath() methods.
    // WARN: this will promote performance when thrift value to be skipped is large, but may decrease preformance when thrift value is small.
    UseNativeSkipForGet = false

    // DefaultNodeSliceCap is the default capacity of a Node or NodePath slice
    // Usually, a Node or NodePath slice is used to store intermediate or consequential elements of a generic API like Children()|Interface()|SetMany()
    DefaultNodeSliceCap = 16
)
```

## func DescriptorToPathNode

```go
func DescriptorToPathNode(desc *thrift.TypeDescriptor, root *PathNode, opts *Options) error
```

DescriptorToPathNode converts a thrift type descriptor to a DOM, assgining path to root NOTICE: it only recursively converts STRUCT type

## func FreePathNode

```go
func FreePathNode(p *PathNode)
```

FreePathNode put a PathNode back to memory pool

## func GetDescByPath

```go
func GetDescByPath(desc *thrift.TypeDescriptor, path ...Path) (ret *thrift.TypeDescriptor, err error)
```

GetDescByPath searches longitudinally and returns the sub descriptor of the desc specified by path

## type Node

Node is a generic wrap of raw thrift data

```go
type Node struct {
    // contains filtered or unexported fields
}
```

### func NewNode

```go
func NewNode(t thrift.Type, src []byte) Node
```

NewNodeBool create a new node with given type and data WARN: it WON'T check the correctness of the data

### func NewNodeBinary

```go
func NewNodeBinary(val []byte) Node
```

NewNodeBinary converts a \[\]byte value to a STRING node

### func NewNodeBool

```go
func NewNodeBool(val bool) Node
```

NewNodeBool converts a bool value to a BOOL node

### func NewNodeByte

```go
func NewNodeByte(val byte) Node
```

NewNodeInt8 converts a byte value to a BYTE node

### func NewNodeDouble

```go
func NewNodeDouble(val float64) Node
```

NewNodeDouble converts a float64 value to a DOUBLE node

### func NewNodeInt16

```go
func NewNodeInt16(val int16) Node
```

NewNodeInt16 converts a int16 value to a I16 node

### func NewNodeInt32

```go
func NewNodeInt32(val int32) Node
```

NewNodeInt32 converts a int32 value to a I32 node

### func NewNodeInt64

```go
func NewNodeInt64(val int64) Node
```

NewNodeInt64 converts a int64 value to a I64 node

### func NewNodeString

```go
func NewNodeString(val string) Node
```

NewNodeString converts a string value to a STRING node

### func \(Node\) Binary

```go
func (self Node) Binary() ([]byte, error)
```

Binary returns the bytes value contained by a BINARY node

### func \(Node\) Bool

```go
func (self Node) Bool() (bool, error)
```

Bool returns the bool value contained by a BOOL node

### func \(Node\) Byte

```go
func (self Node) Byte() (byte, error)
```

Byte returns the byte value contained by a I8/BYTE node

### func \(\*Node\) Check

```go
func (self *Node) Check() error
```

Check checks if it is a ERROR node and returns corresponding error

### func \(Node\) Children

```go
func (self Node) Children(out *[]PathNode, recurse bool, opts *Options) (err error)
```

Children loads all its children and children's children recursively \(if recurse is true\). out is used for store children, and it is always reset to zero length before use.

NOTICE: if opts.NotScanParentNode is true, the parent nodes \(PathNode.Node\) of complex \(LIST/SET/MAP/STRUCT\) type won't be assgined data

### func \(Node\) ElemType

```go
func (self Node) ElemType() thrift.Type
```

ElemType returns the thrift type of a LIST/SET/MAP node's element

### func \(Node\) ErrCode

```go
func (self Node) ErrCode() meta.ErrCode
```

ErrCode return the meta.ErrCode of a ERROR node

### func \(Node\) Error

```go
func (self Node) Error() string
```

Error return error message if it is a ERROR node

### func \(Node\) Field

```go
func (self Node) Field(id thrift.FieldID) (v Node)
```

Field returns a sub node at the given field id from a STRUCT node.

### func \(Node\) Fields

```go
func (self Node) Fields(ids []PathNode, opts *Options) (err error)
```

Fields returns all sub nodes ids along with the given int path from a STRUCT node.

### func \(Node\) Float64

```go
func (self Node) Float64() (float64, error)
```

Float64 returns the float64 value contained by a DOUBLE node

### func \(Node\) Foreach

```go
func (self Node) Foreach(handler func(path Path, node Node) bool, opts *Options) error
```

Foreach scan each element of a complex type \(LIST/SET/MAP/STRUCT\), and call handler sequentially with corresponding path and node

### func \(Node\) ForeachKV

```go
func (self Node) ForeachKV(handler func(key Node, val Node) bool, opts *Options) error
```

ForeachKV scan each element of a MAP type, and call handler sequentially with corresponding key and value

### func \(Node\) Fork

```go
func (self Node) Fork() Node
```

Fork forks the node to a new node, copy underlying data as well

### func \(Node\) GetByInt

```go
func (self Node) GetByInt(key int) (v Node)
```

GetByInt returns a sub node at the given int key from a MAP\<INT,xx\> node.

### func \(Node\) GetByPath

```go
func (self Node) GetByPath(pathes ...Path) Node
```

GetByPath searches longitudinally and return a sub node at the given path from the node.

The path is a list of PathFieldId, PathIndex, PathStrKey, PathBinKey, PathIntKey, Each path MUST be a valid path type for current layer \(e.g. PathFieldId is only valid for STRUCT\). Empty path will return the current node.

### func \(Node\) GetByRaw

```go
func (self Node) GetByRaw(key []byte) (v Node)
```

GetByInt returns a sub node at the given bytes key from a MAP node. The key must be deep equal \(bytes.Equal\) to the key in the map.

### func \(Node\) GetByStr

```go
func (self Node) GetByStr(key string) (v Node)
```

GetByInt returns a sub node at the given int key from a MAP\<STRING,xx\> node.

### func \(Node\) GetMany

```go
func (self Node) GetMany(pathes []PathNode, opts *Options) error
```

GetMany searches transversely and returns all the sub nodes along with the given pathes.

### func \(Node\) GetTree

```go
func (self Node) GetTree(tree *PathNode, opts *Options) error
```

GetTree returns a tree of all sub nodes along with the given path on the tree. It supports longitudinally search \(like GetByPath\) and transversely search \(like GetMany\) both.

### func \(Node\) Gets

```go
func (self Node) Gets(keys []PathNode, opts *Options) (err error)
```

Gets returns all sub nodes along with the given key \(PathStrKey|PathIntKey|PathBinKey\) path from a MAP node.

### func \(Node\) Index

```go
func (self Node) Index(i int) (v Node)
```

Index returns a sub node at the given index from a LIST/SET node.

### func \(Node\) Indexes

```go
func (self Node) Indexes(ins []PathNode, opts *Options) (err error)
```

Indexes returns all sub nodes along with the given int path from a LIST/SET node.

### func \(Node\) Int

```go
func (self Node) Int() (int, error)
```

Int returns the int value contaned by a I8/I16/I32/I64 node

### func \(Node\) IntMap

```go
func (self Node) IntMap(opts *Options) (map[int]interface{}, error)
```

StrMap returns the integer keys and interface elements contained by a MAP\<I8|I16|I32|I64,XX\> node

### func \(Node\) Interface

```go
func (self Node) Interface(opts *Options) (interface{}, error)
```

Interface returns the go interface value contained by a node. If the node is a STRUCT, it will return a map\[thrift.FieldID\]interface\{\} If it is a map, it will return map\[int|string|interface\{\}\]interface\{\}, which depends on the key type

### func \(Node\) InterfaceMap

```go
func (self Node) InterfaceMap(opts *Options) (map[interface{}]interface{}, error)
```

InterfaceMap returns the interface keys and interface elements contained by a MAP node. If the key type is complex \(LIST/SET/MAP/STRUCT\), it will be stored using its pointer since its value are not supported by Go

### func \(Node\) IsEmpty

```go
func (self Node) IsEmpty() bool
```

IsEmpty tells if the node is thrift.STOP

### func \(Node\) IsErrNotFound

```go
func (self Node) IsErrNotFound() bool
```

IsErrorNotFound tells if the node is not\-found\-data error

### func \(Node\) IsError

```go
func (self Node) IsError() bool
```

IsEmtpy tells if the node is thrift.ERROR

### func \(Node\) KeyType

```go
func (self Node) KeyType() thrift.Type
```

KeyType returns the thrift type of a MAP node's key

### func \(Node\) Len

```go
func (self Node) Len() (int, error)
```

Len returns the element count of container\-kind type \(LIST/SET/MAP\)

### func \(Node\) List

```go
func (self Node) List(opts *Options) ([]interface{}, error)
```

List returns interface elements contained by a LIST/SET node

### func \(Node\) Raw

```go
func (self Node) Raw() []byte
```

Return its underlying raw data

### func \(\*Node\) SetByPath

```go
func (self *Node) SetByPath(sub Node, path ...Path) (exist bool, err error)
```

SetByPath sets the sub node at the given path.

### func \(\*Node\) SetMany

```go
func (self *Node) SetMany(pathes []PathNode, opts *Options) (err error)
```

SetMany searches longitudinally and sets the sub nodes at the given pathes.

### func \(Node\) StrMap

```go
func (self Node) StrMap(opts *Options) (map[string]interface{}, error)
```

StrMap returns the string keys and interface elements contained by a MAP\<STRING,XX\> node

### func \(Node\) String

```go
func (self Node) String() (string, error)
```

String returns the string value contianed by a STRING node

### func \(Node\) Type

```go
func (self Node) Type() thrift.Type
```

Type returns the thrift type of the node

### func \(\*Node\) UnsetByPath

```go
func (self *Node) UnsetByPath(path ...Path) error
```

## type Options

Opions for generic.Node

```go
type Options struct {
    // DisallowUnknow indicates to report error when read unknown fields.
    DisallowUnknow bool

    // WriteDefault indicates to write value if a DEFAULT requireness field is not set.
    WriteDefault bool

    // NoCheckRequireNess indicates not to check requiredness when writing.
    NotCheckRequireNess bool

    // UseNativeSkip indicates to use native.Skip (instead of go.Skip) method to skip thrift value
    // WARN: this will promote performance when thrift value to be skipped is large, but may decrease preformance when thrift value is small.
    UseNativeSkip bool

    // MapStructById indicates to use field id as map key instead of when call Node.Interface() on STRUCT type.
    MapStructById bool

    // CastStringAsBinary indicates to cast STRING type to []byte when call Node.Interface()/Map().
    CastStringAsBinary bool

    // NotScanParentNode indicates to only assign children node when PathNode.Load()/Node.Children.
    // Thies will promote performance but may be misued when handle PathNode.
    NotScanParentNode bool

    // ClearDirtyValues indicates one multi-query (includeing
    // Fields()/GetMany()/Gets()/Indexies()) to clear out all nodes
    // in passed []PathNode first
    ClearDirtyValues bool
}
```

## type Path

Path represents the relative position of a sub node in a complex parent node

```go
type Path struct {
    // contains filtered or unexported fields
}
```

### func NewPathBinKey

```go
func NewPathBinKey(key []byte) Path
```

NewPathBinKey creates a PathBinKey path

### func NewPathFieldId

```go
func NewPathFieldId(id thrift.FieldID) Path
```

NewPathFieldId creates a PathFieldId path

### func NewPathFieldName

```go
func NewPathFieldName(name string) Path
```

NewPathFieldName creates a PathFieldName path

### func NewPathIndex

```go
func NewPathIndex(index int) Path
```

NewPathIndex creates a PathIndex path

### func NewPathIntKey

```go
func NewPathIntKey(key int) Path
```

NewPathIntKey creates a PathIntKey path

### func NewPathStrKey

```go
func NewPathStrKey(key string) Path
```

NewPathStrKey creates a PathStrKey path

### func \(Path\) Bin

```go
func (self Path) Bin() []byte
```

Bin returns the raw bytes value of a PathBinKey path

### func \(Path\) Id

```go
func (self Path) Id() thrift.FieldID
```

Id returns the field id of a PathFieldId path

### func \(Path\) Int

```go
func (self Path) Int() int
```

Int returns the int value of a PathIndex\\PathIntKey path

### func \(Path\) Str

```go
func (self Path) Str() string
```

Str returns the string value of a PathFieldName\\PathStrKey path

### func \(Path\) String

```go
func (self Path) String() string
```

String returns the string representation of a Path

### func \(Path\) ToRaw

```go
func (self Path) ToRaw(t thrift.Type) []byte
```

ToRaw converts underlying value to thrift\-encoded bytes

### func \(Path\) Type

```go
func (self Path) Type() PathType
```

Type returns the type of a Path

### func \(Path\) Value

```go
func (self Path) Value() interface{}
```

Value returns the equivalent go interface of a Path

## type PathNode

PathNode is a three node of DOM tree

```go
type PathNode struct {
    Path
    Node
    Next []PathNode
}
```

### func NewPathNode

```go
func NewPathNode() *PathNode
```

NewPathNode get a new PathNode from memory pool

### func \(\*PathNode\) Assgin

```go
func (self *PathNode) Assgin(recurse bool, opts *Options) error
```

Assgin assigns self's raw Value according to its Next Path, which must be set before calling this method.

### func \(PathNode\) Fork

```go
func (self PathNode) Fork() PathNode
```

Fork copy self and its children to a new PathNode

### func \(\*PathNode\) Load

```go
func (self *PathNode) Load(recurse bool, opts *Options) error
```

Load loads self's all children \( and children's children if recurse is true\) into self.Next, no matter whether self.Next is empty or set before \(will be reset\). NOTICE: if opts.NotScanParentNode is true, the parent nodes \(PathNode.Node\) of complex \(map/list/struct\) type won't be assgined data

<details><summary>Example</summary>
<p>

```go
{

	data := getExampleData()
	root := PathNode{
		Node: NewNode(thrift.STRUCT, data),
	}

	err := root.Load(false, opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", root)

	err = root.Load(true, opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", root)

	reuse := pathNodePool.Get().(*PathNode)
	root.Node = NewNode(thrift.STRUCT, data)
	err = root.Load(true, opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", root)
	reuse.ResetValue()
	pathNodePool.Put(reuse)

}
```

</p>
</details>

### func \(PathNode\) Marshal

```go
func (self PathNode) Marshal(opt *Options) (out []byte, err error)
```

Marshal marshals self to thrift bytes

### func \(PathNode\) MarshalIntoBuffer

```go
func (self PathNode) MarshalIntoBuffer(out *[]byte, opt *Options) error
```

MarshalIntoBuffer marshals self to thrift bytes into a buffer

### func \(\*PathNode\) ResetAll

```go
func (self *PathNode) ResetAll()
```

ResetAll resets self and its children, including path and node both

### func \(\*PathNode\) ResetValue

```go
func (self *PathNode) ResetValue()
```

ResetValue resets self's node and its children's node

## type PathType

PathType is the type of path

```go
type PathType uint8
```

```go
const (
    // PathFieldId represents a field id of STRUCT type
    PathFieldId PathType = 1 + iota

    // PathFieldName represents a field name of STRUCT type
    // NOTICE: it is only supported by Value
    PathFieldName

    // PathIndex represents a index of LIST\SET type
    PathIndex

    // Path represents a string key of MAP type
    PathStrKey

    // Path represents a int key of MAP type
    PathIntKey

    // Path represents a raw-bytes key of MAP type
    // It is usually used for neither-string-nor-integer type key
    PathBinKey
)
```

## type Value

Value is a generic API wrapper for operations on thrift data. Node is the underlying raw bytes. Desc is the corresponding type descriptor.

```go
type Value struct {
    Node
    Desc *thrift.TypeDescriptor
}
```

<details><summary>Example (3et Many)</summary>
<p>

```go
{

	desc := getExampleDesc()
	data := getExampleData()
	d1 := desc.Struct().FieldByKey("Msg").Type()
	d2 := desc.Struct().FieldByKey("Subfix").Type()
	v := NewValue(desc, data)

	p := thrift.NewBinaryProtocol([]byte{})
	e1 := "test1"
	p.WriteString(e1)
	v1 := NewValue(d1, p.RawBuf())
	p = thrift.NewBinaryProtocol([]byte{})
	e2 := float64(-255.0001)
	p.WriteDouble(e2)
	v2 := NewValue(d2, p.RawBuf())
	v3 := v.GetByPath(NewPathFieldName("Base"))

	ps := []PathNode{
		{
			Path: NewPathFieldId(1),
			Node: v1.Node,
		},
		{
			Path: NewPathFieldId(32767),
			Node: v2.Node,
		},
		{
			Path: NewPathFieldId(255),
			Node: v3.Node,
		},
	}

	err := v.SetMany(ps, opts)
	if err != nil {
		panic(err)
	}
	any, err := v.Interface(opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", any)

	ps2 := []PathNode{
		{
			Path: NewPathFieldId(1),
		},
		{
			Path: NewPathFieldId(32767),
		},
		{
			Path: NewPathFieldId(255),
		},
	}
	if err := v.GetMany(ps2, opts); err != nil {
		panic(err)
	}
	any0, err := ps2[2].Node.Interface(opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", any0)
}
```

</p>
</details>

### func NewValue

```go
func NewValue(desc *thrift.TypeDescriptor, src []byte) Value
```

NewValue creates a new Value from a raw byte slice.

### func \(Value\) Field

```go
func (self Value) Field(id thrift.FieldID) (v Value)
```

Field returns a sub node at the given field id from a STRUCT value.

### func \(Value\) FieldByName

```go
func (self Value) FieldByName(name string) (v Value)
```

FieldByName returns a sub node at the given field name from a STRUCT value.

### func \(Value\) Fork

```go
func (self Value) Fork() Value
```

NewValueFromNode copy both Node and TypeDescriptor from another Value.

### func \(Value\) GetByInt

```go
func (self Value) GetByInt(key int) (v Value)
```

GetByInt returns a sub node at the given int key from a MAP value.

### func \(Value\) GetByPath

```go
func (self Value) GetByPath(pathes ...Path) Value
```

GetByPath searches longitudinally and return a sub value at the given path from the value.

The path is a list of PathFieldId, PathFieldName, PathIndex, PathStrKey, PathBinKey, PathIntKey, Each path MUST be a valid path type for current layer \(e.g. PathFieldId is only valid for STRUCT\). Empty path will return the current value.

### func \(Value\) GetByStr

```go
func (self Value) GetByStr(key string) (v Value)
```

GetByStr returns a sub node at the given string key from a MAP value.

### func \(Value\) Index

```go
func (self Value) Index(i int) (v Value)
```

Index returns a sub node at the given index from a LIST value.

### func \(Value\) MarshalTo

```go
func (self Value) MarshalTo(to *thrift.TypeDescriptor, opts *Options) ([]byte, error)
```

MarshalTo marshals self value into a sub value descripted by the to descriptor, alse called as "Cutting". Usually, the to descriptor is a subset of self descriptor.

<details><summary>Example</summary>
<p>

```go
{

	desc := getExampleDesc()
	data := getExampleData()
	v := NewValue(desc, data)

	full, err := NewNode(thrift.STRUCT, data).Interface(opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", full)

	pdesc := getExamplePartialDesc()

	out, err := v.MarshalTo(pdesc, opts)
	if err != nil {
		panic(err)
	}

	partial, err := NewNode(thrift.STRUCT, out).Interface(opts)
	if err != nil {
		panic(err)
	}
	fmt.Printf("%#v", partial)
}
```

</p>
</details>

### func \(\*Value\) SetByPath

```go
func (self *Value) SetByPath(sub Value, path ...Path) (exist bool, err error)
```

SetByPath searches longitudinally and sets a sub value at the given path from the value. exist tells whether the node is already exists.

<details><summary>Example</summary>
<p>

```go
{

	desc := getExampleDesc()
	data := getExampleData()
	v := NewValue(desc, data)

	d := desc.Struct().FieldByKey("Base").Type().Struct().FieldByKey("Extra").Type().Elem()
	p := thrift.NewBinaryProtocol([]byte{})
	exp := "中文"
	p.WriteString(exp)
	buf := p.RawBuf()
	vv := NewValue(d, buf)

	ps := []Path{NewPathFieldName("Base"), NewPathFieldName("Extra"), NewPathStrKey("b")}
	exist, err2 := v.SetByPath(vv, ps...)
	if err2 != nil {
		panic(err2)
	}
	println(exist)

	s2 := v.GetByPath(ps...)
	if s2.Error() != "" {
		panic(s2.Error())
	}
	f2, _ := s2.String()
	println(f2)
}
```

</p>
</details>

### func \(\*Value\) UnsetByPath

```go
func (self *Value) UnsetByPath(path ...Path) error
```

UnsetByPath searches longitudinally and unsets a sub value at the given path from the value.



Generated by [gomarkdoc](<https://github.com/princjef/gomarkdoc>)