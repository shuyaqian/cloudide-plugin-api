**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / TextEditorSelectionChangeKind

# Enumeration: TextEditorSelectionChangeKind

Represents sources that can cause [selection change events](#window.onDidChangeTextEditorSelection).

## Index

### Enumeration members

* [Command](_index_d_._plugin_.texteditorselectionchangekind.md#command)
* [Keyboard](_index_d_._plugin_.texteditorselectionchangekind.md#keyboard)
* [Mouse](_index_d_._plugin_.texteditorselectionchangekind.md#mouse)

## Enumeration members

### Command

•  **Command**:  = 3

*Defined in [index.d.ts:532](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L532)*

Selection changed because a command ran.

___

### Keyboard

•  **Keyboard**:  = 1

*Defined in [index.d.ts:524](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L524)*

Selection changed due to typing in the editor.

___

### Mouse

•  **Mouse**:  = 2

*Defined in [index.d.ts:528](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L528)*

Selection change due to clicking in the editor.
