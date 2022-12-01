---
title: Gérer les e-mails d’activité actionnables
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: En savoir plus sur l’activation et la désactivation des e-mails d’activité actionnables des conversations Microsoft Teams
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198506"
---
# <a name="manage-actionable-activity-emails"></a>Gérer les e-mails d’activité actionnables

Les e-mails d’activité actionnables sont activés par défaut et informent les utilisateurs de votre organisation des conversations manquées sur Microsoft Teams.

Un e-mail d’activité manquée affiche les dernières réponses à une conversation, y compris les messages envoyés après le message manqué. Cette fonctionnalité permet aux utilisateurs de répondre directement à partir d’Outlook en sélectionnant **Répondre**.

## <a name="disable-actionability-in-missed-activity-emails"></a>Désactiver l’actionabilité dans les e-mails d’activité manquée

Bien que cette fonctionnalité soit activée par défaut, vous pouvez désactiver l’actionabilité dans les e-mails d’activité au sein de votre organisation en exécutant la commande suivante :

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

Une fois la fonctionnalité désactivée, l’option **Répondre** est remplacée par **Répondre dans Teams** , ce qui rend les e-mails d’activité manqués plus considérés comme actionnables. Les utilisateurs ne pourront plus répondre directement à partir d’Outlook et sont invités à poursuivre la conversation sur Teams.

> [!NOTE]
> Cette fonctionnalité n’est pas prise en charge dans Outlook pour Mac ou certaines versions antérieures d’Outlook pour Windows. Pour plus d’informations, voir [Messages actionnables dans Outlook et Office 365 Groupes](/outlook/actionable-messages/).

## <a name="related-topics"></a>Rubriques connexes

[Répondre aux e-mails d’activité manqués à partir d’Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Messages actionnables dans Outlook et groupes Office 365](/outlook/actionable-messages/).
