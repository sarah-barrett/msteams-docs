---
title: Webhooks and connectors
author: clearab
description: Learn how webhooks and connectors help to connect the web services to channels and teams in Microsoft Teams. Learn Incoming, Outgoing Webhooks, and Office 365 Connectors.
ms.localizationpriority: high
ms.topic: overview
ms.author: anclear
---

# Webhooks and connectors

Webhooks and connectors help to connect the web services to channels and teams in Microsoft Teams. Webhooks are user defined HTTP callback that notifies users about any action that has taken place in the Teams channel. It's a way for an app to get real time data. Connectors allow users to subscribe to receive notifications and messages from your web services. They expose an HTTPS endpoint for your service to post messages in the form of cards.

> [!IMPORTANT]
> You can choose to build notification bot Teams app other than Incoming Webhooks. They perform similarly but notification bot has more functionalities. For more information, see [Build notification bot with JavaScript](../sbs-gs-notificationbot.yml) or [Incoming Webhook notification sample](https://github.com/OfficeDev/TeamsFx-Samples/tree/dev/incoming-webhook-notification). To get started, download [Teams Toolkit](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension) now and explore. For more information, see [Teams Toolkit documents](../toolkit/teams-toolkit-fundamentals.md).

## Outgoing Webhooks

Webhooks help Teams to integrate with external apps. With Outgoing Webhooks, you can send text messages from a channel to the web services. After configuring the Outgoing Webhooks, users can @mention Outgoing Webhook and send a message to web services. The service responds within 10 seconds to the message with a text or a card.

> [!NOTE]
> Outgoing Webhooks are configured on a per team basis and cannot be included as part of a normal Teams app.

## Connectors

Connectors allow users to subscribe to receive notifications and messages from the web services. They expose the HTTPS endpoint for the service to post messages to Teams channels, typically in the form of cards.

### Incoming Webhooks

Incoming Webhooks help in posting messages from apps to Teams. If Incoming Webhooks are enabled for a team in any channel, it exposes the HTTPS endpoint, which accepts correctly formatted JSON and inserts the messages into that channel. For example, you can create an Incoming Webhook in your DevOps channel, configure your build, and simultaneously deploy and monitor services to send alerts.

#### Notification bot or Incoming Webhook - choose the right one

Before you start to learn how to build Incoming Webhooks, you may also want to know that you can build Notification Bot using Teams Toolkit. Notification Bots can enable more customizable experience to meet different business scenarios.

Learn more about the differences between Notification Bot and Incoming Webhook so that you can choose correct solutions for your scenarios:

| &nbsp; | Notification bot |  Incoming Webhook |
| --- | --- | --- |
| What is it? | A Teams app | A Teams feature |
| Installation required | Yes | No |
| Suitable scenarios | • Receive regular notifications and messages periodically, for example, receive daily notification of team tasks. <br>  • Receive notifications and messages based on real events. For example, once teammates upload files, you receive notifications. | Communicate with external apps and receive notifications and messages from other apps. |
| Scope configuration | • Teams channel <br> • Group chat <br> • Personal chat | Teams channel |
| Message process | A Notification Bot works as a Teams application. You can define your business logic to process data and show data in a customized format. | Webhook is a Teams feature rather than a Teams application, so it only receives and shows data without processing. |
| Retrieve Teams context | Notification Bot can retrieve Teams context such as the channel or user information, messages, etc. | No |
| Send Adaptive Card | Yes | Yes |
| Send a welcome message | Can send a welcome message | No welcome message |
| Trigger Supported | All triggers supported. If you use Teams Toolkit, you can quickly get template projects with following triggers: <br> • Time trigger hosted on Azure functions. <br> • Restify HTTP trigger hosted on Azure app service <br> • HTTP trigger hosted on Azure Functions | All triggers supported |
| Building Tools | • [Teams Toolkit Overview for Visual Studio Code](../toolkit/teams-toolkit-fundamentals.md) <br> • [Teams Toolkit overview for Visual Studio](../toolkit/teams-toolkit-fundamentals.md) <br> • [TeamsFx Library](../toolkit/TeamsFx-CLI.md) <br> • [TeamsFx SDK](../toolkit/TeamsFx-SDK.md) | No tools required |
| Cloud resource required | Azure Bot Framework | No resources required |
| Tutorial | [Build notification bot with JavaScript](../sbs-gs-notificationbot.yml) | [Incoming Webhook notification sample](https://github.com/OfficeDev/TeamsFx-Samples/tree/dev/incoming-webhook-notification) |

### Office 365 Connectors

Office 365 Connectors allow you to create a custom configuration page for your Incoming Webhook and package them as part of a Teams app. You send messages primarily using Office 365 Connector cards and have the ability to add a limited set of card actions to them. For example, a weather connector that allows users to select a location and any time of the day, to receive updates about tomorrow's weather. They're configured at channel level but are installed at team level.

> [!NOTE]
> You can distribute the Office 365 Connector Teams app to our AppStore.

## Create and send messages

Actionable messages allow users to take action without leaving their email client, increasing user engagement. With Office 365 and Incoming Webhooks, you can send messages by posting a JSON payload to the webhook URL.

## Next step

> [!div class="nextstepaction"]
> [Create Outgoing Webhooks](~/webhooks-and-connectors/how-to/add-outgoing-webhook.md)

## See also

* [Create Incoming Webhooks](~/webhooks-and-connectors/how-to/add-incoming-webhook.md)
* [App capabilities mapped to features](../concepts/design/map-use-cases.md#app-capabilities-mapped-to-features)
* [Create Office 365 Connectors](~/webhooks-and-connectors/how-to/connectors-creating.md)
* [Create and send messages](~/webhooks-and-connectors/how-to/connectors-using.md)
