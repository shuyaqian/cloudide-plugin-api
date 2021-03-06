**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / CompletionItemProvider

# Interface: CompletionItemProvider

The completion item provider interface defines the contract between extensions and
[IntelliSense](https://code.visualstudio.com/docs/editor/intellisense).

Providers can delay the computation of the [`detail`](#CompletionItem.detail)
and [`documentation`](#CompletionItem.documentation) properties by implementing the
[`resolveCompletionItem`](#CompletionItemProvider.resolveCompletionItem)-function. However, properties that
are needed for the initial sorting and filtering, like `sortText`, `filterText`, `insertText`, and `range`, must
not be changed during resolve.

Providers are asked for completions either explicitly by a user gesture or -depending on the configuration-
implicitly when typing words or trigger characters.

## Hierarchy

* **CompletionItemProvider**

## Index

### Methods

* [provideCompletionItems](_index_d_._plugin_.completionitemprovider.md#providecompletionitems)
* [resolveCompletionItem](_index_d_._plugin_.completionitemprovider.md#resolvecompletionitem)

## Methods

### provideCompletionItems

▸ **provideCompletionItems**(`document`: [TextDocument](_index_d_._plugin_.textdocument.md), `position`: [Position](../classes/_index_d_._plugin_.position.md), `token`: [CancellationToken](_index_d_._plugin_.cancellationtoken.md), `context`: [CompletionContext](_index_d_._plugin_.completioncontext.md)): [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[CompletionItem](../classes/_index_d_._plugin_.completionitem.md)[] \| [CompletionList](../classes/_index_d_._plugin_.completionlist.md)>

*Defined in [index.d.ts:3955](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3955)*

Provide completion items for the given position and document.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`document` | [TextDocument](_index_d_._plugin_.textdocument.md) | The document in which the command was invoked. |
`position` | [Position](../classes/_index_d_._plugin_.position.md) | The position at which the command was invoked. |
`token` | [CancellationToken](_index_d_._plugin_.cancellationtoken.md) | A cancellation token. |
`context` | [CompletionContext](_index_d_._plugin_.completioncontext.md) | How the completion was triggered.  |

**Returns:** [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[CompletionItem](../classes/_index_d_._plugin_.completionitem.md)[] \| [CompletionList](../classes/_index_d_._plugin_.completionlist.md)>

An array of completions, a [completion list](#CompletionList), or a thenable that resolves to either.
The lack of a result can be signaled by returning `undefined`, `null`, or an empty array.

___

### resolveCompletionItem

▸ `Optional`**resolveCompletionItem**(`item`: [CompletionItem](../classes/_index_d_._plugin_.completionitem.md), `token`: [CancellationToken](_index_d_._plugin_.cancellationtoken.md)): [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[CompletionItem](../classes/_index_d_._plugin_.completionitem.md)>

*Defined in [index.d.ts:3972](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L3972)*

Given a completion item fill in more data, like [doc-comment](#CompletionItem.documentation)
or [details](#CompletionItem.detail).

The editor will only resolve a completion item once.

*Note* that accepting a completion item will not wait for it to be resolved. Because of that [`insertText`](#CompletionItem.insertText),
[`additionalTextEdits`](#CompletionItem.additionalTextEdits), and [`command`](#CompletionItem.command) should not
be changed when resolving an item.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`item` | [CompletionItem](../classes/_index_d_._plugin_.completionitem.md) | A completion item currently active in the UI. |
`token` | [CancellationToken](_index_d_._plugin_.cancellationtoken.md) | A cancellation token. |

**Returns:** [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[CompletionItem](../classes/_index_d_._plugin_.completionitem.md)>

The resolved completion item or a thenable that resolves to of such. It is OK to return the given
`item`. When no result is returned, the given `item` will be used.
