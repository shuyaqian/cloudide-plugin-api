**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / CompletionContext

# Interface: CompletionContext

Contains additional information about the context in which
[completion provider](#CompletionItemProvider.provideCompletionItems) is triggered.

## Hierarchy

* **CompletionContext**

## Index

### Properties

* [triggerCharacter](_index_d_._plugin_.completioncontext.md#triggercharacter)
* [triggerKind](_index_d_._plugin_.completioncontext.md#triggerkind)

## Properties

### triggerCharacter

• `Optional` `Readonly` **triggerCharacter**: string

*Defined in [index.d.ts:3926](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3926)*

Character that triggered the completion item provider.

`undefined` if provider was not triggered by a character.

The trigger character is already in the document when the completion provider is triggered.

___

### triggerKind

• `Readonly` **triggerKind**: [CompletionTriggerKind](../enums/_index_d_._plugin_.completiontriggerkind.md)

*Defined in [index.d.ts:3917](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3917)*

How the completion was triggered.
