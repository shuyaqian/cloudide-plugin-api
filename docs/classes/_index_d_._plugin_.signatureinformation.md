**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / SignatureInformation

# Class: SignatureInformation

Represents the signature of something callable. A signature
can have a label, like a function-name, a doc-comment, and
a set of parameters.

## Hierarchy

* **SignatureInformation**

## Index

### Constructors

* [constructor](_index_d_._plugin_.signatureinformation.md#constructor)

### Properties

* [activeParameter](_index_d_._plugin_.signatureinformation.md#activeparameter)
* [documentation](_index_d_._plugin_.signatureinformation.md#documentation)
* [label](_index_d_._plugin_.signatureinformation.md#label)
* [parameters](_index_d_._plugin_.signatureinformation.md#parameters)

## Constructors

### constructor

\+ **new SignatureInformation**(`label`: string, `documentation?`: string \| [MarkdownString](_index_d_._plugin_.markdownstring.md)): [SignatureInformation](_index_d_._plugin_.signatureinformation.md)

*Defined in [index.d.ts:3555](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3555)*

Creates a new signature information object.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`label` | string | A label string. |
`documentation?` | string \| [MarkdownString](_index_d_._plugin_.markdownstring.md) | A doc string.  |

**Returns:** [SignatureInformation](_index_d_._plugin_.signatureinformation.md)

## Properties

### activeParameter

• `Optional` **activeParameter**: number

*Defined in [index.d.ts:3555](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3555)*

The index of the active parameter.

If provided, this is used in place of [`SignatureHelp.activeSignature`](#SignatureHelp.activeSignature).

___

### documentation

• `Optional` **documentation**: string \| [MarkdownString](_index_d_._plugin_.markdownstring.md)

*Defined in [index.d.ts:3543](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3543)*

The human-readable doc-comment of this signature. Will be shown
in the UI but can be omitted.

___

### label

•  **label**: string

*Defined in [index.d.ts:3537](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3537)*

The label of this signature. Will be shown in
the UI.

___

### parameters

•  **parameters**: [ParameterInformation](_index_d_._plugin_.parameterinformation.md)[]

*Defined in [index.d.ts:3548](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3548)*

The parameters of this signature.
