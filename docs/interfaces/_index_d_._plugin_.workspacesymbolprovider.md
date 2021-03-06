**[@cloudide/plugin](../README.md)**

> [Globals](../README.md) / ["index.d"](../modules/_index_d_.md) / ["plugin"](../modules/_index_d_._plugin_.md) / WorkspaceSymbolProvider

# Interface: WorkspaceSymbolProvider

The workspace symbol provider interface defines the contract between extensions and
the [symbol search](https://code.visualstudio.com/docs/editor/editingevolved#_open-symbol-by-name)-feature.

## Hierarchy

* **WorkspaceSymbolProvider**

## Index

### Methods

* [provideWorkspaceSymbols](_index_d_._plugin_.workspacesymbolprovider.md#provideworkspacesymbols)
* [resolveWorkspaceSymbol](_index_d_._plugin_.workspacesymbolprovider.md#resolveworkspacesymbol)

## Methods

### provideWorkspaceSymbols

▸ **provideWorkspaceSymbols**(`query`: string, `token`: [CancellationToken](_index_d_._plugin_.cancellationtoken.md)): [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md)[]>

*Defined in [index.d.ts:2828](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L2828)*

Project-wide search for a symbol matching the given query string.

The `query`-parameter should be interpreted in a *relaxed way* as the editor will apply its own highlighting
and scoring on the results. A good rule of thumb is to match case-insensitive and to simply check that the
characters of *query* appear in their order in a candidate symbol. Don't use prefix, substring, or similar
strict matching.

To improve performance implementors can implement `resolveWorkspaceSymbol` and then provide symbols with partial
[location](#SymbolInformation.location)-objects, without a `range` defined. The editor will then call
`resolveWorkspaceSymbol` for selected symbols only, e.g. when opening a workspace symbol.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`query` | string | A query string, can be the empty string in which case all symbols should be returned. |
`token` | [CancellationToken](_index_d_._plugin_.cancellationtoken.md) | A cancellation token. |

**Returns:** [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md)[]>

An array of document highlights or a thenable that resolves to such. The lack of a result can be
signaled by returning `undefined`, `null`, or an empty array.

___

### resolveWorkspaceSymbol

▸ `Optional`**resolveWorkspaceSymbol**(`symbol`: [SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md), `token`: [CancellationToken](_index_d_._plugin_.cancellationtoken.md)): [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md)>

*Defined in [index.d.ts:2842](https://github.com/huaweicloud/cloudide-plugin-api/blob/1ab5ef8/index.d.ts#L2842)*

Given a symbol fill in its [location](#SymbolInformation.location). This method is called whenever a symbol
is selected in the UI. Providers can implement this method and return incomplete symbols from
[`provideWorkspaceSymbols`](#WorkspaceSymbolProvider.provideWorkspaceSymbols) which often helps to improve
performance.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`symbol` | [SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md) | The symbol that is to be resolved. Guaranteed to be an instance of an object returned from an earlier call to `provideWorkspaceSymbols`. |
`token` | [CancellationToken](_index_d_._plugin_.cancellationtoken.md) | A cancellation token. |

**Returns:** [ProviderResult](../modules/_index_d_._plugin_.md#providerresult)\<[SymbolInformation](../classes/_index_d_._plugin_.symbolinformation.md)>

The resolved symbol or a thenable that resolves to that. When no result is returned,
the given `symbol` is used.
