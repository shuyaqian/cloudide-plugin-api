**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / ColorInformation

# Class: ColorInformation

Represents a color range from a document.

## Hierarchy

* **ColorInformation**

## Index

### Constructors

* [constructor](_index_d_._plugin_.colorinformation.md#constructor)

### Properties

* [color](_index_d_._plugin_.colorinformation.md#color)
* [range](_index_d_._plugin_.colorinformation.md#range)

## Constructors

### constructor

\+ **new ColorInformation**(`range`: [Range](_index_d_._plugin_.range.md), `color`: [Color](_index_d_._plugin_.color.md)): [ColorInformation](_index_d_._plugin_.colorinformation.md)

*Defined in [index.d.ts:4088](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4088)*

Creates a new color range.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`range` | [Range](_index_d_._plugin_.range.md) | The range the color appears in. Must not be empty. |
`color` | [Color](_index_d_._plugin_.color.md) | The value of the color. |

**Returns:** [ColorInformation](_index_d_._plugin_.colorinformation.md)

## Properties

### color

•  **color**: [Color](_index_d_._plugin_.color.md)

*Defined in [index.d.ts:4088](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4088)*

The actual color value for this color range.

___

### range

•  **range**: [Range](_index_d_._plugin_.range.md)

*Defined in [index.d.ts:4083](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L4083)*

The range in the document where this color appears.
