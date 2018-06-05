# KIRIK protocol 
## Contents
1. [Documentation](#documentation)
2. [Examples](#examples)
3. [Plugins](#plugins)
4. [Tools](#tools)

## Documentation
MiniApps.run Documentation: https://docs.miniapps.pro/display/MINIAPPS/

## Examples

1. Tic-tac-toe
2. Test-bots fot plug-ins: [msisdn-verification](https://github.com/kirikprotocol/MSISDN-verification-plugin/tree/master/web/msisdn-confirmation-test), [secret-input](https://github.com/kirikprotocol/secret-input-sample), [languege-selection](https://github.com/kirikprotocol/Language-selection-test), [miniapps-test-bot](https://github.com/kirikprotocol/Miniapps-test-bot), [send-file-demo](https://github.com/kirikprotocol/Send-file-demo)
3. [Community bot mamalara.ru](https://github.com/kirikprotocol/Community-bot-mamalara.ru)
4. [FAQ bot](https://github.com/kirikprotocol/API.ai-helper/tree/master/src/com/eyelinecom/whoisd/sads2/apiai/bot/services/apiai)
5. [Smart bots examples](https://github.com/kirikprotocol/Smart-bots-examples)
6. Sample Google Sheet miniapps
7. [Subway-demo-bot](https://github.com/kirikprotocol/Subway-demo-bot)

## Plugins

- [Verification MSISDN](https://github.com/kirikprotocol/MSISDN-verification-plugin)
- [TiPay plugin](https://github.com/kirikprotocol/TiPay-plugin)
- [CCC plugin (Chat call-center)]()
- [Bitrix24 plugin](https://github.com/kirikprotocol/Bitrix24-plugin)
- [VK-market plugin](https://github.com/kirikprotocol/VK-market-plugin)
- [Google calendar plugin](https://github.com/kirikprotocol/Google-calendar-plugin)
- [Sender plugin](https://github.com/kirikprotocol/Sender-plugin)
- [API.AI helper](https://github.com/kirikprotocol/API.ai-helper)
- [MS QNA helper](https://github.com/kirikprotocol/MS-QNA-helper)


### Calling MiniApps Plugins

In MiniApps a plugin (a.k.a. template, gadget) is a separate component of the platform that adds functionality when connected to a service. There are plugins constituting an integral part of the platform (built-in plugins), as well as third-party plugins developed by independent programmers. The latter can be developed using the MiniApps capabilities, or external tools.

Three methods of plugin calls are available at present.

1. Specifying attributes of a page, or a page element.
Examples: MSISDN verification with the use of  "msisdn-required" page attribute, or entry of Telegram password when specifying the type of an entry field.
2. Following a link with a special protocol.
Example: going to the MSISDN verification plugin using the verify://msisdn link.
3. Following a link to a miniapps.run platform built-in plugin using a specially formed HTTP address.

The first two methods are described in [MSISDN verification](https://github.com/kirikprotocol/MSISDN-verification-plugin).

#### HTTP Notation for Plugin Calls

A plugin is called by following a link of a special format. The link is formed based on:

- Plugin identifier. 
Every plugin identifier is unique and does not depend on a particular MiniApps unit.

- Parameters transmitted. 
The set of supported parameters is plugin specific.

This link is a correct HTTP URL and has the following format. Access to this address is not guaranteed, neither the address is requested from MiniApps when following the link - handling of addresses on plugins.miniapps.run is done locally.
```
http://plugins.miniapps.run/<PLUGIN_ID>?param1=value1&param2=value2&param3=value3
```
Where:

- http://plugins.miniapps.run is the mandatory constant prefix;
- PLUGIN_ID - plugin identifier;
- The arguments are transferred as regular query parameters.

Example:
```
<navigation>
  <link pageId="http://plugins.miniapps.run/msisdn-verification?type=c2s&success_url=private.jsp">
    Go to page
  </link>
</navigation>
```

#### Supported Plugins

The set of supported plugins is determined in the MiniApps settings.

|Plugin               |identifier           |Description                                                                       |
|:--------------------|:--------------------|:---------------------------------------------------------------------------------|
|[MSISDN Verifier](https://github.com/kirikprotocol/MSISDN-verification-plugin)|msisdn-verification  |	If MSISDN is absent in the user profile, the user is prompted to go through MSISDN verification procedure. If the verification is successful, the user is allowed to proceed to the next page.                    |
|[TiPay Payment](https://github.com/kirikprotocol/TiPay-plugin)|tipаy-payment        |The user is prompted to start a TiPay payment procedure.                          |
|[Password Entry](https://github.com/kirikprotocol/Secret-input-sample)|password-input       |Entry of a password without storing it in the TG chat history.                    |
|[Language Selection](https://github.com/kirikprotocol/Language-selection-test)|language-selection   |The preferred language is selected and stored in the user profile.                |
|Session Invalidation |invalidate-session   |Invalidation of the current session.                                              |
|Profile Clean-out    |clear-profile        |Clean-out of a user profile.                                                      |
|[API.ai Assistant](https://github.com/kirikprotocol/API.ai-helper)|ai_apiai             |The dialog is transferred to API.ai bot.                                          |
|[MS QNA Assistant](https://github.com/kirikprotocol/MS-QNA-helper)|ai_msqna             |The dialog is transferred to https://qnamaker.ai bot.                             |
|[Bitrix](https://github.com/kirikprotocol/Bitrix24-plugin)|bitrix               |The user's dialog is handed over to Bitrix support.                               |
|[Google Calendar](https://github.com/kirikprotocol/Google-calendar-plugin)|google-calendar      |An event is added to Google Calendar.                                             |
|[VK Market](https://github.com/kirikprotocol/VK-market-plugin)|vk-market            |Passage to VK Market, picking up goods, order placement.                          |
|[Mass Messaging](https://github.com/kirikprotocol/Sender-plugin)|sender-plugin        |Mass message to all users of a service.                                           |
|Quest                |tester-google-sheets |Quests and quizzes with results written to Google Sheets.                         |
|Whitelist            |whitelist            |This plugin restricts access to a bot to specific users.                          |
|IPS Poll Results     |ips-stats            |This plugin displays the results of an IPS poll.                                  |

## Tools

- STT
- AI plugins
- Personalization 2
- SAA 2.0
- [IPS](https://github.com/kirikprotocol/IPS)
- ALS 
- Libs: [RSM](https://github.com/kirikprotocol/RSM), db-template, db-template-test 
