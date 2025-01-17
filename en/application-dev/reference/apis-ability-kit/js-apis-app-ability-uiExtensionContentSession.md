# @ohos.app.ability.UIExtensionContentSession (UI Operation Class for ExtensionAbilities with UI)

**UIExtensionContentSession** is an instance created when the [UIExtensionAbility](js-apis-app-ability-uiExtensionAbility.md) loads UI content. When the UIExtensionComponent starts a UIExtensionAbility, the UIExtensionAbility creates a UIExtensionContentSession instance and returns it through the [onSessionCreate](js-apis-app-ability-uiExtensionAbility.md#uiextensionabilityonsessioncreate) callback. One UIExtensionComponent corresponds to one **UIExtensionContentSession** instance, which provides methods such as UI loading and result notification. The **UIExtensionContentSession** instances of multiple UIExtensionAbilities are operated separately.

> **NOTE**
>
> The initial APIs of this module are supported since API version 10. Newly added APIs will be marked with a superscript to indicate their earliest API version.
>
> The APIs of this module can be used only in the stage model.

## Modules to Import

```ts
import { UIExtensionContentSession } from '@kit.AbilityKit';
```

## UIExtensionContentSession.loadContent

loadContent(path: string, storage?: LocalStorage): void

Loads content from a page associated with a local storage to the window corresponding to the current UIExtensionComponent.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name | Type                                           | Mandatory| Description                                                        |
| ------- | ----------------------------------------------- | ---- | ------------------------------------------------------------ |
| path    | string                                          | Yes  | Path of the page from which the content will be loaded.                                        |
| storage | [LocalStorage](../../quick-start/arkts-localstorage.md) | No  | A storage unit, which provides storage for variable state properties and non-variable state properties of an application. This parameter is left blank by default.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md) and [Ability Error Codes](errorcode-ability.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |
| 16000050 | Internal error. |

## UIExtensionContentSession.terminateSelf

terminateSelf(callback: AsyncCallback&lt;void&gt;): void

Stops the window object corresponding to this **UIExtensionContentSession** instance. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name| Type| Mandatory| Description|
| -------- | -------- | -------- | -------- |
| callback | AsyncCallback&lt;void&gt; | Yes| Callback used to return the result. If the window object is stopped, **err** is **undefined**; otherwise, **err** is an error object.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |

## UIExtensionContentSession.terminateSelf

terminateSelf(): Promise&lt;void&gt;

Stops the window object corresponding to this **UIExtensionContentSession** instance. This API uses a promise to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Return value**

| Type| Description|
| -------- | -------- |
| Promise&lt;void&gt; | Promise that returns no value.|

## UIExtensionContentSession.terminateSelfWithResult

terminateSelfWithResult(parameter: AbilityResult, callback: AsyncCallback&lt;void&gt;): void

Stops the window object corresponding to this **UIExtensionContentSession** instance and returns the result to the UIExtensionComponent. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name| Type| Mandatory| Description|
| -------- | -------- | -------- | -------- |
| parameter | [AbilityResult](js-apis-inner-ability-abilityResult.md) | Yes| Result returned to the UIExtensionComponent.|
| callback | AsyncCallback&lt;void&gt; | Yes| Callback used to return the result. If the window object is stopped, **err** is **undefined**; otherwise, **err** is an error object.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |

## UIExtensionContentSession.terminateSelfWithResult

terminateSelfWithResult(parameter: AbilityResult): Promise&lt;void&gt;

Stops the window object corresponding to this **UIExtensionContentSession** instance and returns the result to the UIExtensionComponent. This API uses a promise to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name| Type| Mandatory| Description|
| -------- | -------- | -------- | -------- |
| parameter | [AbilityResult](js-apis-inner-ability-abilityResult.md) | Yes| Result returned to the UIExtensionComponent.|

**Return value**

| Type| Description|
| -------- | -------- |
| Promise&lt;void&gt; | Promise that returns no value.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |

## UIExtensionContentSession.setWindowPrivacyMode

setWindowPrivacyMode(isPrivacyMode: boolean): Promise&lt;void&gt;

Sets whether the window is in privacy mode. A window in privacy mode cannot be captured or recorded. This API uses a promise to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Required permissions**: ohos.permission.PRIVACY_WINDOW

**Parameters**

| Name| Type| Mandatory| Description|
| ------------- | ------- | -- | ----------------------------------------------------- |
| isPrivacyMode | boolean | Yes| Whether the window is in privacy mode. The value **true** means that the window is in privacy mode, and **false** means the opposite.|

**Return value**

| Type| Description|
| ------------------- | ------------------------ |
| Promise&lt;void&gt; | Promise that returns no value.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 201      | The application does not have permission to call the interface. |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |

## UIExtensionContentSession.setWindowPrivacyMode

setWindowPrivacyMode(isPrivacyMode: boolean, callback: AsyncCallback&lt;void&gt;): void

Sets whether the window is in privacy mode. A window in privacy mode cannot be captured or recorded. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Required permissions**: ohos.permission.PRIVACY_WINDOW

**Parameters**

| Name| Type| Mandatory| Description|
| ------------- | ------------------------- | -- | ------------------------------------------------------ |
| isPrivacyMode | boolean                   | Yes| Whether the window is in privacy mode. The value **true** means that the window is in privacy mode, and **false** means the opposite. |
| callback      | AsyncCallback&lt;void&gt; | Yes| Callback used to return the result. If the setting is successful, **err** is **undefined**. Otherwise, **err** is an error object.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 201      | The application does not have permission to call the interface. |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |

## UIExtensionContentSession.startAbilityByType<sup>11+</sup>

startAbilityByType(type: string, wantParam: Record<string, Object>,
    abilityStartCallback: AbilityStartCallback, callback: AsyncCallback\<void>): void

Implicitly starts a given type of UIExtensionAbility. This API uses an asynchronous callback to return the result. It can be called only by applications running in the foreground.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name| Type| Mandatory| Description|
| -------- | -------- | -------- | -------- |
| type | string | Yes| Type of the UIExtensionAbility to start.<!--Del--> For details, see [Starting an Application of the Specified Type](../../application-models/start-intent-panel.md#matching-rules).<!--DelEnd-->|
| wantParam | Record<string, Object> | Yes| Extended parameter.|
| abilityStartCallback | [AbilityStartCallback](js-apis-inner-application-abilityStartCallback.md) | Yes| Callback used to return the detailed error information if the startup fails.|
| callback | AsyncCallback\<void> | Yes|Callback used to return the result. If the ability is started, **err** is **undefined**; otherwise, **err** is an error object.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md) and [Ability Error Codes](errorcode-ability.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |
| 16000050 | Internal error. |

## UIExtensionContentSession.startAbilityByType<sup>11+</sup>

startAbilityByType(type: string, wantParam: Record<string, Object>,
    abilityStartCallback: AbilityStartCallback): Promise\<void>

Implicitly starts a given type of UIExtensionAbility. This API uses a promise to return the result. It can be called only by applications running in the foreground.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Parameters**

| Name| Type| Mandatory| Description|
| -------- | -------- | -------- | -------- |
| type | string | Yes| Type of the UIExtensionAbility to start.<!--Del--> For details, see [Starting an Application of the Specified Type](../../application-models/start-intent-panel.md#matching-rules).<!--DelEnd-->|
| wantParam | Record<string, Object> | Yes| Extended parameter.|
| abilityStartCallback | [AbilityStartCallback](js-apis-inner-application-abilityStartCallback.md) | Yes| Callback used to return the detailed error information if the startup fails.|

**Return value**

| Type| Description|
| -------- | -------- |
| Promise\<void> | Promise that returns no value.|

**Error codes**

For details about the error codes, see [Universal Error Codes](../errorcode-universal.md) and [Ability Error Codes](errorcode-ability.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 401      | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types. |
| 16000050 | Internal error. |

## UIExtensionContentSession.getUIExtensionWindowProxy<sup>12+</sup>

getUIExtensionWindowProxy(): uiExtension.WindowProxy

Obtains the window proxy of this UIExtensionAbility.

**System capability**: SystemCapability.Ability.AbilityRuntime.Core

**Return value**

| Type| Description|
| -------- | -------- |
| uiExtension.WindowProxy | Window proxy.|

**Error codes**

For details about the error codes, see [Ability Error Codes](errorcode-ability.md).

| ID| Error Message|
| ------- | -------------------------------- |
| 16000050 | Internal error. |

**Example**

```ts
// Index.ets
import { UIExtensionContentSession } from '@kit.AbilityKit';
import uiExtension from '@ohos.arkui.uiExtension';

let storage = LocalStorage.getShared();

@Entry(storage)
@Component
struct Extension {
  @State message: string = 'EmbeddedUIExtensionAbility Index';
  private session: UIExtensionContentSession | undefined = storage.get<UIExtensionContentSession>('session');
  private extensionWindow: uiExtension.WindowProxy | undefined = this.session?.getUIExtensionWindowProxy();

  aboutToAppear(): void {
    this.extensionWindow?.on('windowSizeChange', (size) => {
      console.info(`size = ${JSON.stringify(size)}`);
    });
    this.extensionWindow?.on('avoidAreaChange', (info) => {
      console.info(`type = ${JSON.stringify(info.type)}, area = ${JSON.stringify(info.area)}`);
    });
  }

  aboutToDisappear(): void {
    this.extensionWindow?.off('windowSizeChange');
    this.extensionWindow?.off('avoidAreaChange');
  }

  build() {
    Column() {
      Text(this.message)
        .fontSize(20)
        .fontWeight(FontWeight.Bold)
    }
    .width('100%')
  }
}
```

 <!--no_check--> 