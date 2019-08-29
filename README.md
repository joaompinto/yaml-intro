# YAML Syntax

## Introduction
YAML is a flexible, human readable text based format that is widely used on computer systems as a configuration language. YAML stands for “YAML Ain’t Markup Language”. It is easier to read (by humans) than JSON or XML, and can contain richer meta data.


## Element Kinds
YAML provides three main kind of elements: comments, scalars and collections

### Comments
The hash _("#")_symbol placed at the start of a line, or into an unquoted string will set all the remaining content as a comment. Comments are not actual date, they are removed when the data is processed, they usually provide some auxiliary description.

Comment examples:
```yaml
# Nextl line is a string value followed by a comment
The text # the effective value of this line is: The text
``` 

### Scalars
Scalars are used to represent simple values like _numbers_, _strings(text)_ or _booleans_. 

Example of scalar elements:
```yaml
Hello world     # String
```
```yaml
3               # Integer number
```
```yaml
"3"             # This is 3 as text
```
```yaml
1.2             # Floating point number
```
```yaml
False           # Boolean
```

**When you provide a value containing special characters that you want to be treated as text, you must surround it with single or double quotes**

### Collections
Collections are use to group zero or more elements, there are two types of collections: _sequences_ and _mappings_. A collection can include other collections allowing the creation of more complex hierarchical structures.

#### Sequences
A sequence is an ordered list of elements.

##### Block Sequences
A block sequence is defined by starting a value with a dash followed by a space `'- '`, the remaining content of that line is interpreted as the list element. Each consecutive line started with the `'- '` at the same line position will be used to provide additional elements to the list.

Block sequence example:
```yaml
# Next is a list with three elements
- Banana
# Comments do not break sequences
- Apple
# A sequence can have elements from different types
- 3.12
```

##### Flow Sequences
A flow sequence is defined by starting a value with a `'['` symbol, separating multiple values using the `','` symbol, the sequence must be terminated with a `']'` symbol.

Flow sequence example:
```yaml
[Banane, Apple, 3.12]
```

#### Mappings
A mapping is an unordered collection of _key: value_ pairs, where _key_ is a string (limited to 2014 chars) and the value can be a scalar or a collection. Keys within a collection must be unique. It can be defined by providing a value with the format _'key : value'_.

Mapping block example 1
```yaml
name: Bob
age: 40
```
Mapping block example 2
```yaml
S: Small
M: Medium
L: Large
XL: Extra large
```

##### Flow Mapping
A flow mapping is defined by starting a value with the `'{'`, separating multiple pairs using the  `','` symbol`, the mapping must be terminated with a `'}'`.

Mapping flow example 1:
```yaml
{ name: Bob, age: 40 }
```
Mapping flow example 2:
```yaml
{ S: Small, M: Medium, L: Large, XL: Extra large }
```

Mapping gives you the ability to list keys with values, 

A sequence is an ordered list of elements, it can be defined by starting a line using a dash followed by a space `«- »`, the remaining content of that line is interpreted as the list element. Each consecutive line started with the `«- »` placed at the same position will be used to provide additional elements to the list.

Sequence example:
```yaml
- Banana
# Comments do not break sequences
- Apple
# A sequence can have elements from different types
- 3.12
```

## Basic Rule
Use a text editor with good support for YAML documents, a very popular option is Microsoft's [vscode] with [RedHat's YAML extension] .

[vscode]: https://code.visualstudio.com/
[RedHat's YAML extension]: https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml


## More Examples

Mapping, sequence, mapping
```yaml
name: Rick Brown
age: 71
sons: 
  - name: Ted Silver
    age: 42
    sons:
      - name: Bob Boot
        age: 10
```
Sequence, mapping, sequence
```yaml
- user: bob
  scores:
  - 40
  - 18
  - 200

- user: "{joe}"
  scores: [700, 99]
```
