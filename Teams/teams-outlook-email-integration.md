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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899688"
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
