**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / LanguageConfiguration

# Interface: LanguageConfiguration

The language configuration interfaces defines the contract between extensions
and various editor features, like automatic bracket insertion, automatic indentation etc.

## Hierarchy

* **LanguageConfiguration**

## Index

### Properties

* [\_\_characterPairSupport](_index_d_._plugin_.languageconfiguration.md#__characterpairsupport)
* [\_\_electricCharacterSupport](_index_d_._plugin_.languageconfiguration.md#__electriccharactersupport)
* [brackets](_index_d_._plugin_.languageconfiguration.md#brackets)
* [comments](_index_d_._plugin_.languageconfiguration.md#comments)
* [indentationRules](_index_d_._plugin_.languageconfiguration.md#indentationrules)
* [onEnterRules](_index_d_._plugin_.languageconfiguration.md#onenterrules)
* [wordPattern](_index_d_._plugin_.languageconfiguration.md#wordpattern)

## Properties

### \_\_characterPairSupport

• `Optional` **\_\_characterPairSupport**: { autoClosingPairs: { close: string ; notIn?: string[] ; open: string  }[]  }

*Defined in [index.d.ts:4596](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4596)*

**Deprecated** Do not use.

**`deprecated`** * Use the autoClosingPairs property in the language configuration file instead.

#### Type declaration:

Name | Type |
------ | ------ |
`autoClosingPairs` | { close: string ; notIn?: string[] ; open: string  }[] |

___

### \_\_electricCharacterSupport

• `Optional` **\_\_electricCharacterSupport**: { brackets?: any ; docComment?: { close?: string ; lineStart: string ; open: string ; scope: string  }  }

*Defined in [index.d.ts:4570](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4570)*

**Deprecated** Do not use.

**`deprecated`** Will be replaced by a better API soon.

#### Type declaration:

Name | Type | Description |
------ | ------ | ------ |
`brackets?` | any | This property is deprecated and will be **ignored** from the editor.  **`deprecated`**   |
`docComment?` | { close?: string ; lineStart: string ; open: string ; scope: string  } | This property is deprecated and not fully supported anymore by the editor (scope and lineStart are ignored). Use the autoClosingPairs property in the language configuration file instead.  **`deprecated`**   |

___

### brackets

• `Optional` **brackets**: [CharacterPair](../modules/_index_d_._plugin_.md#characterpair)[]

*Defined in [index.d.ts:4547](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4547)*

The language's brackets.
This configuration implicitly affects pressing Enter around these brackets.

___

### comments

• `Optional` **comments**: [CommentRule](_index_d_._plugin_.commentrule.md)

*Defined in [index.d.ts:4542](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4542)*

The language's comment settings.

___

### indentationRules

• `Optional` **indentationRules**: [IndentationRule](_index_d_._plugin_.indentationrule.md)

*Defined in [index.d.ts:4559](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4559)*

The language's indentation settings.

___

### onEnterRules

• `Optional` **onEnterRules**: [OnEnterRule](_index_d_._plugin_.onenterrule.md)[]

*Defined in [index.d.ts:4563](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4563)*

The language's rules to be evaluated when pressing Enter.

___

### wordPattern

• `Optional` **wordPattern**: RegExp

*Defined in [index.d.ts:4555](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4555)*

The language's word definition.
If the language supports Unicode identifiers (e.g. JavaScript), it is preferable
to provide a word definition that uses exclusion of known separators.
e.g.: A regex that matches anything except known separators (and dot is allowed to occur in a floating point number):
  /(-?\d*\.\d\w*)|([^\`\~\!\@\#\%\^\&\*\(\)\-\=\+\[\{\]\}\\\|\;\:\'\"\,\.\<\>\/\?\s]+)/g
