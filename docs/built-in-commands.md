# Build-in Commands

List of common built-in commands in theia.

## 1. Common Commands
### core.open
### core.copy
### core.paste
### core.copy.path
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |
### core.undo
### core.redo
### core.selectAll
### core.nextTab
### core.previousTab
### core.nextTabInGroup
### core.previousTabInGroup
### core.nextTabGroup
### core.previousTabBar
### core.close.tab
#### Parameters Event:
Name | Type |
------ | ------ |
`event?` | Event |
```
/** An event which takes place in the DOM. */
interface Event {
    /**
     * Returns true or false depending on how event was initialized. True if event goes through its target's ancestors in reverse tree order, and false otherwise.
     */
    readonly bubbles: boolean;
    cancelBubble: boolean;
    /**
     * Returns true or false depending on how event was initialized. Its return value does not always carry meaning, but true can indicate that part of the operation during which event was dispatched, can be canceled by invoking the preventDefault() method.
     */
    readonly cancelable: boolean;
    /**
     * Returns true or false depending on how event was initialized. True if event invokes listeners past a ShadowRoot node that is the root of its target, and false otherwise.
     */
    readonly composed: boolean;
    /**
     * Returns the object whose event listener's callback is currently being invoked.
     */
    readonly currentTarget: EventTarget | null;
    /**
     * Returns true if preventDefault() was invoked successfully to indicate cancelation, and false otherwise.
     */
    readonly defaultPrevented: boolean;
    /**
     * Returns the event's phase, which is one of NONE, CAPTURING_PHASE, AT_TARGET, and BUBBLING_PHASE.
     */
    readonly eventPhase: number;
    /**
     * Returns true if event was dispatched by the user agent, and false otherwise.
     */
    readonly isTrusted: boolean;
    returnValue: boolean;
    /** @deprecated */
    readonly srcElement: EventTarget | null;
    /**
     * Returns the object to which event is dispatched (its target).
     */
    readonly target: EventTarget | null;
    /**
     * Returns the event's timestamp as the number of milliseconds measured relative to the time origin.
     */
    readonly timeStamp: number;
    /**
     * Returns the type of event, e.g. "click", "hashchange", or "submit".
     */
    readonly type: string;
    /**
     * Returns the invocation target objects of event's path (objects on which listeners will be invoked), except for any nodes in shadow trees of which the shadow root's mode is "closed" that are not reachable from event's currentTarget.
     */
    composedPath(): EventTarget[];
    initEvent(type: string, bubbles?: boolean, cancelable?: boolean): void;
    /**
     * If invoked when the cancelable attribute value is true, and while executing a listener for the event with passive set to false, signals to the operation that caused event to be dispatched that it needs to be canceled.
     */
    preventDefault(): void;
    /**
     * Invoking this method prevents event from reaching any registered event listeners after the current one finishes running and, when dispatched in a tree, also prevents event from reaching any other objects.
     */
    stopImmediatePropagation(): void;
    /**
     * When dispatched in a tree, invoking this method prevents event from reaching any objects other than the current object.
     */
    stopPropagation(): void;
    readonly AT_TARGET: number;
    readonly BUBBLING_PHASE: number;
    readonly CAPTURING_PHASE: number;
    readonly NONE: number;
}
```
### core.close.other.tabs
#### Parameters: 
Name | Type |
------ | ------ |
`event?` | [Event](#Parameters-Event) |
### core.close.right.tabs
#### Parameters:
Name | Type |
------ | ------ |
`event?` | [Event](#Parameters-Event) |
### core.close.all.tabs
#### Parameters:
Name | Type |
------ | ------ |
`event?` | [Event](#Parameters-Event) |
### core.close.main.tab
### core.close.other.main.tabs
### core.close.all.main.tabs
### core.collapse.tab
#### Parameters:
Name | Type |
------ | ------ |
`event?` | [Event](#Parameters-Event) |
### core.collapse.all.tabs
### core.toggle.bottom.panel
### core.toggleMaximized
#### Parameters:
Name | Type |
------ | ------ |
`event?` | [Event](#Parameters-Event) |
### core.save
### core.saveWithoutFormatting
### core.saveAll
### core.about
### core.openView
### workbench.action.selectTheme
### workbench.action.selectIconTheme


## 2. Workspace Commands
### workspace:open
### workspace:openFile
### workspace:openFolder
### workspace:openWorkspace
### workspace:close
### workspace:openRecent
### workspace:saveAs
### file.saveAs
#### Parameters:
Name | Type |
------ | ------ |
`uri` | URI |
### file.newFile
#### Parameters:
Name | Type |
------ | ------ |
`uri` | URI |
### file.newFolder
#### Parameters:
Name | Type |
------ | ------ |
`uri` | URI |
### file.rename
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |
### file.duplicate
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |
### file.delete
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |
### file.compare
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |
### workspace:addFolder
### workspace:removeFolder
#### Parameters:
Name | Type |
------ | ------ |
`uris` | URI[] |

## 3. Git Commands
### git.clone
Name | Type |
------ | ------ |
`url?` | string |
`folder?` | string |
`branch?` | string |
### git.fetch
### git.pull.default
### git.pull
### git.push.default
### git.push
### git.merge
### git.checkout
### git.commit.all
### git-commit-add-sign-off
### git.commit.amend
### git.commit.signOff
### git.open.file
Name | Type |
------ | ------ |
`widget` | Widget |
### git.open.changes
Name | Type |
------ | ------ |
`widget` | Widget |
### git.sync
### git.publish
### git.stage
Name | Type |
------ | ------ |
`ScmResource[]` | ScmResource[] |
```
interface ScmResource {
    /** The uri of the underlying resource inside the workspace. */
    readonly sourceUri: URI;
    readonly decorations?: ScmResourceDecorations;
    open(): Promise<void>;

    readonly group: ScmResourceGroup;
}
interface ScmResourceDecorations {
    tooltip?: string;
    source?: string;
    letter?: string;
    color?: string;
}
ScmResourceGroup extends Disposable {
    readonly id: string;
    readonly label: string;
    readonly resources: ScmResource[];
    readonly hideWhenEmpty?: boolean;
    readonly provider: ScmProvider;
}
```
### git.stage.all
### git.open.changed.file
Name | Type |
------ | ------ |
`ScmResource[]` | ScmResource[] |
### git.unstage
Name | Type |
------ | ------ |
`ScmResource[]` | ScmResource[] |
### git.unstage.all
### git.discard
Name | Type |
------ | ------ |
`ScmResource[]` | ScmResource[] |
### git.discard.all
### git.stash
### git.stash.apply
### git.stash.apply.latest
### git.commit.stash.pop
### git.commit.stash.drop
### git-refresh
### git-init

## 4. Git-Diff Commands
### git-diff:open-file-diff
Name | Type |
------ | ------ |
`fileUri` | URI |
### git.navigate-changes.previous
Name | Type |
------ | ------ |
`widget` | Widget |
### git.navigate-changes.next
Name | Type |
------ | ------ |
`widget` | Widget |

## 5. Terminal Commands
### terminal:new
### terminal:<zero-width space>new:active:workspace
### terminal:clear
### terminal:context
Name | Type |
------ | ------ |
`uri` | URI |
### terminal:split
Name | Type |
------ | ------ |
`widget` | Widget |
### terminal:find
### terminal:find:cancel
### terminal:<zero-width space>scroll:line:up
### terminal:<zero-width space>scroll:line:down
### terminal:<zero-width space>scroll:top
### terminal:<zero-width space>scroll:page:up
### terminal:<zero-width space>scroll:page:down

## 6. Output Commands
### output:append
Name | Type |
------ | ------ |
`name` | string |
`text` | string |
### output:appendLine
Name | Type |
------ | ------ |
`name` | string |
`text` | string |
### output:clear
Name | Type |
------ | ------ |
`name` | string |
### output:show
Name | Type |
------ | ------ |
`name` | string |
`options` | { preserveFocus?: boolean } |
### output:hide
Name | Type |
------ | ------ |
`name` | string |
### output:dispose
Name | Type |
------ | ------ |
`name` | string |
### output:widget:clear
### output:widget:lock
Name | Type |
------ | ------ |
`widget` | Widget |
### output:widget:unlock
Name | Type |
------ | ------ |
`widget` | Widget |
### output:pick-clear
### output:pick-show
### output:pick-hide
### output:pick-dispose
### output:copy-all


## 7. Vscode Commands
### vscode.open
Name | Type |
------ | ------ |
`resource` | URI |
`columnOrOptions?` | `ViewColumn | TextDocumentShowOptions` |
```
enum ViewColumn {
    Active = -1,
    Beside = -2,
    One = 1,
    Two = 2,
    Three = 3,
    Four = 4,
    Five = 5,
    Six = 6,
    Seven = 7,
    Eight = 8,
    Nine = 9
}
/**
 * Represents options to configure the behavior of showing a document in an editor.
 */
interface TextDocumentShowOptions {
    /**
     * An optional selection to apply for the document in the editor.
     */
    selection?: Range;

    /**
     * An optional flag that when `true` will stop the editor from taking focus.
     */
    preserveFocus?: boolean;

    /**
     * An optional flag that controls if an editor-tab will be replaced
     * with the next editor or if it will be kept.
     */
    preview?: boolean;

    /**
     * Denotes a location of an editor in the window. Editors can be arranged in a grid
     * and each column represents one editor location in that grid by counting the editors
     * in order of their appearance.
     */
    viewColumn?: theia.ViewColumn;
}
interface Range {
    /**
     * Line number on which the range starts (starts at 1).
     */
    readonly startLineNumber: number;
    /**
     * Column on which the range starts in line `startLineNumber` (starts at 1).
     */
    readonly startColumn: number;
    /**
     * Line number on which the range ends.
     */
    readonly endLineNumber: number;
    /**
     * Column on which the range ends in line `endLineNumber`.
     */
    readonly endColumn: number;
}
```
### vscode.openFolder
Name | Type |
------ | ------ |
`resource` | URI |
`arg` | `boolean | IOpenFolderAPICommandOptions = {}` |
```
interface IOpenFolderAPICommandOptions {
    forceNewWindow?: boolean;
    forceReuseWindow?: boolean;
    noRecentEntry?: boolean;
}
```
### vscode.diff
Name | Type |
------ | ------ |
`left` | URI |
`right` | URI |
`label?` | string |
`options?` | TextDocumentShowOptions |
### workbench.action.files.newUntitledFile
### workbench.action.files.openFile
### workbench.action.files.openFolder
### workbench.action.addRootFolder
### workbench.action.gotoLine
### workbench.action.quickOpen
### workbench.action.openSettings
### workbench.extensions.installExtension
Name | Type |
------ | ------ |
`vsixUriOrExtensionId` | `UriComponents | string` |
```
interface UriComponents {
    scheme: string;
    authority: string;
    path: string;
    query: string;
    fragment: string;
    external?: string;
}
```
### workbench.action.files.save
Name | Type |
------ | ------ |
`uri?` | monaco.Uri |
### workbench.action.files.saveAll
### workbench.action.closeActiveEditor
Name | Type |
------ | ------ |
`uri?` | monaco.Uri |
### workbench.action.closeOtherEditors
Name | Type |
------ | ------ |
`uri?` | monaco.Uri |
### workbench.action.closeEditorsInGroup
Name | Type |
------ | ------ |
`uri?` | monaco.Uri |
### workbench.action.closeEditorsInOtherGroups
### workbench.action.closeEditorsToTheLeft
### workbench.action.closeEditorsToTheRight
### workbench.action.closeAllEditors
### workbench.action.nextEditor
### workbench.action.previousEditor
### workbench.action.navigateBack
### workbench.action.navigateForward
### workbench.action.navigateToLastEditLocation
### openInTerminal
Name | Type |
------ | ------ |
`resource` | URI |
### workbench.action.revertAndCloseActiveEditor
### vscode.executeDefinitionProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
 ```
 interface Position {
    readonly lineNumber: number;
    readonly column: number;
}   
 ```
### vscode.executeDeclarationProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeTypeDefinitionProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeImplementationProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeHoverProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeDocumentHighlights
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeReferenceProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.executeDocumentSymbolProvider
Name | Type |
------ | ------ |
`resource` | URI |
### vscode.executeFormatDocumentProvider
Name | Type |
------ | ------ |
`resource` | URI |
`options` | FormattingOptions |
```
 interface FormattingOptions {
    tabSize: number;
    insertSpaces: boolean;
}
```
### vscode.executeFormatRangeProvider
Name | Type |
------ | ------ |
`resource` | URI |
`range` | Range |
`options` | FormattingOptions |
### vscode.executeFormatOnTypeProvider
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
`ch` | string |
`options` | FormattingOptions |
### vscode.prepareCallHierarchy
Name | Type |
------ | ------ |
`resource` | URI |
`position` | Position |
### vscode.provideIncomingCalls
Name | Type |
------ | ------ |
`item` | CallHierarchyItem |
```
interface CallHierarchyItem {
    _sessionId?: string;
    _itemId?: string;

    kind: SymbolKind;
    name: string;
    detail?: string;
    uri: UriComponents;
    range: Range;
    selectionRange: Range;
}
```
### vscode.provideOutgoingCalls
Name | Type |
------ | ------ |
`item` | CallHierarchyItem |
### workbench.action.openRecent
### explorer.newFolder
### workbench.action.terminal.sendSequence
Name | Type |
------ | ------ |
`args?` | { text?: string } |
### workbench.action.terminal.kill
### workbench.view.explorer
### copyFilePath
### copyRelativeFilePath
### revealInExplorer
Name | Type |
------ | ------ |
`resource` | `URI | object` |
    
## 8. Debug Commands
### workbench.action.debug.start
Name | Type |
------ | ------ |
`config?` | DebugSessionOptions |
```
interface DebugSessionOptions {
    configuration: DebugConfiguration
    workspaceFolderUri?: string
}
interface DebugConfiguration {
    /**
     * The type of the debug adapter session.
     */
    type: string;

    /**
     * The name of the debug adapter session.
     */
    name: string;

    /**
     * Additional debug type specific properties.
     */
    [key: string]: any;

    /**
     * The request type of the debug adapter session.
     */
    request: string;

    /**
     * If noDebug is true the launch request should launch the program without enabling debugging.
     */
    noDebug?: boolean;

    /**
     * Optional data from the previous, restarted session.
     * The data is sent as the 'restart' attribute of the 'terminated' event.
     * The client should leave the data intact.
     */
    __restart?: any;

    /** default: default */
    debugViewLocation?: DebugViewLocation

    /** default: neverOpen */
    openDebug?: 'neverOpen' | 'openOnSessionStart' | 'openOnFirstSessionStart' | 'openOnDebugBreak';

    /** default: neverOpen */
    internalConsoleOptions?: 'neverOpen' | 'openOnSessionStart' | 'openOnFirstSessionStart'

    /** Task to run before debug session starts */
    preLaunchTask?: string | TaskIdentifier;

    /** Task to run after debug session ends */
    postDebugTask?: string | TaskIdentifier;
}
type DebugViewLocation = 'default' | 'left' | 'right' | 'bottom';
interface TaskIdentifier {
    type: string;
    [name: string]: string;
}
```
### workbench.action.debug.run 
Name | Type |
------ | ------ |
`config?` | DebugSessionOptions |
### workbench.action.debug.stop
### workbench.action.debug.restart
### debug.configurations.open
### debug.configurations.add
### workbench.action.debug.stepOver
### workbench.action.debug.stepInto
### workbench.action.debug.stepOut
### workbench.action.debug.continue
### workbench.action.debug.pause
### debug.thread.continue.all
### debug.thread.pause.all
### editor.debug.action.toggleBreakpoint
### editor.debug.action.inlineBreakpoint     
### debug.breakpoint.add.conditional
### debug.breakpoint.add.logpoint
### debug.breakpoint.add.function
### debug.breakpoint.disableAll
### debug.breakpoint.edit
### debug.logpoint.edit
### debug.breakpoint.remove
### debug.logpoint.remove
### debug.breakpoint.removeAll
### debug.breakpoint.toggleEnabled
### editor.debug.action.showDebugHover
### debug.frame.restart
### debug.callStack.copy
### debug.variable.setValue    
### debug.variable.copyValue
### debug.variable.copyAsExpression  
### debug.variable.watch   
### debug.watch.addExpression  
Name | Type |
------ | ------ |
`widget` | Widget |
### debug.watch.editExpression  
### debug.watch.copyExpressionValue 
### debug.watch.removeExpression   
### debug.watch.collapseAllExpressions  
Name | Type |
------ | ------ |
`widget` | Widget |
### debug.watch.removeAllExpressions
Name | Type |
------ | ------ |
`widget` | Widget |
### debug.thread.context.context.next
### debug.thread.context.stepin   
### debug.thread.context.stepout
### debug.thread.context.continue   
### debug.thread.context.pause  
### debug.thread.context.terminate   
### debug.session.context.stop  
### debug.session.context.restart   
### debug.session.context.pauseAll   
### debug.session.context.continueAll 
### debug.session.context.reveal    
### debug.session.context.openLeft
### debug.session.context.openRight   
### debug.session.context.openBottom   
### debug.editor.context.addBreakpoint
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.addBreakpoint.conditional
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.add.logpoint 
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.removeBreakpoint
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.edit.breakpoint
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.enableBreakpoint   
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.disableBreakpoint
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.logpoint.remove
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.logpoint.edit
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.logpoint.enable
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.editor.context.logpoint.disable
Name | Type |
------ | ------ |
`position` | monaco.Position |
### debug.breakpointWidget.accept 
### debug.breakpointWidget.close 

    
## 9. Task Command
### task:run
Name | Type |
------ | ------ |
`args` | any[] |
### task:run:build  
### task:run:test
### workbench.action.tasks.runTask   
### task:run:last   
### task:attach
### task:run:text   
### task:configure  
### task:open_user
### task:clear-history  
### task:show-running   
### task:terminate
### task:restart-running  

    
## 10. Editor Command
### textEditor.commands.showReferences 
### textEditor.commands.configIndentation
### textEditor.commands.configEol   
### textEditor.commands.indentUsingSpaces  
### textEditor.commands.indentUsingTabs
### textEditor.change.language
### textEditor.change.encoding   
### textEditor.commands.go.back  
### textEditor.commands.go.forward   
### textEditor.commands.go.lastEdit  
### textEditor.commands.clear.history   
### workbench.action.showAllEditors  
### editor.action.toggleMinimap   
### editor.action.toggleRenderWhitespace
### editor.action.toggleWordWrap

    
    
## 11. Navigator Command
### navigator.reveal
Name | Type |
------ | ------ |
`event?` | Event |
### navigator.toggle.hidden.files
### navigator.toggle.autoReveal  
Name | Type |
------ | ------ |
`widget` | Widget |
### navigator.refresh 
Name | Type |
------ | ------ |
`widget` | Widget |
### navigator.collapse.all
Name | Type |
------ | ------ |
`widget` | Widget |
### navigator.addRootFolder  
### workbench.files.action.focusFilesExplorer    
### navigator.copyRelativeFilePath
Name | Type |
------ | ------ |
`uris` | URI[] |    
### navigator.open   
### compare:first    
### compare:second   


## 12. Perferences Command
### preferences:open
### preferences:openJson.toolbar
Name | Type |
------ | ------ |
`preferenceNode` | Preference.NodeWithValueInAllScopes |  
```
interface NodeWithValueInAllScopes extends TreeNode {
    preference: PreferenceWithValueInAllScopes;
}
interface PreferenceWithValueInAllScopes {
    values?: ValuesInAllScopes;
    data: PreferenceDataProperty;
}
interface PreferenceDataProperty extends PreferenceItem {
    description?: string;
    markdownDescription?: string;
    scope?: PreferenceScope;
}
enum PreferenceScope {
    Default,
    User,
    Workspace,
    Folder
}
```
### preferences:copyJson.name
Name | Type |
------ | ------ |
{ id, value } | { id: string, value: string; } |  
### preferences:reset
Name | Type |
------ | ------ |
{ id } | { id: string } |  
### preferences:copyJson.value
Name | Type |
------ | ------ |
{ id, value } | { id: string, value: string; } |  
    
    
    
## 13. Search Command
### search-in-workspace.toggle
### search-in-workspace.open 
### search-in-workspace.in-folder
Name | Type |
------ | ------ |
uris | URI[] |  
### search-in-workspace.refresh
Name | Type |
------ | ------ |
widget | Widget | 
### search-in-workspace.cancel
Name | Type |
------ | ------ |
widget | Widget | 
### search-in-workspace.collapse-all
Name | Type |
------ | ------ |
widget | Widget | 
### search-in-workspace.clear-all 
Name | Type |
------ | ------ |
widget | Widget | 
    
    
    
## 14. Console Command
### console.selectAll 
### console.collapseAll
### console.clear
### console.execute  
### console.navigatePrevious
### console.navigateNext

    
## 15. Electron Menu Command
### theia.toggleDevTools
### view.reload  
### view.zoomIn  
### view.zoomOut  
### view.resetZoom   
### close.window  

  
