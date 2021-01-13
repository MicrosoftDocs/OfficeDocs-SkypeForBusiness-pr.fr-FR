---
title: Intégration de la messagerie teams et Outlook
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Découvrez les fonctionnalités d’intégration de la messagerie électronique Teams et Outlook, notamment les fonctionnalités qui letaient les utilisateurs partager des informations entre les e-mails dans Outlook et les conversations ou les conversations de canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802394"
---
# <a name="teams-and-outlook-email-integration"></a>Intégration de la messagerie teams et Outlook

Microsoft Teams inclut des fonctionnalités qui permet aux utilisateurs de votre organisation de partager facilement des informations entre les e-mails dans Outlook et les conversations ou les conversations de canal dans Teams et de rester au fait des conversations manquées. Cet article vous donne une vue d’ensemble de ces fonctionnalités et des contrôles d’administration qui s’appliquent.

## <a name="share-to-outlook"></a>Partager dans Outlook

**Partager avec Outlook** permet aux utilisateurs de partager une copie d’une conversation Teams dans un e-mail dans Outlook, sans avoir à quitter Teams. Cette fonctionnalité est utile si les utilisateurs ont besoin de partager des conversations ou des mises à jour de statut avec des utilisateurs extérieurs à leur équipe immédiate ou même à votre organisation. Allez en haut de la conversation dans Teams, **sélectionnez s s s Autres options,** puis **sélectionnez Partager dans Outlook.**  Pour en savoir plus, voir [Partager dans Outlook à partir de Teams.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Capture d’écran montrant la fonctionnalité Partager avec Outlook dans Teams](media/share-to-outlook.png)

Pour utiliser cette fonctionnalité, Outlook sur le web doit être désactivé pour l’utilisateur. Si Outlook sur le web est désactivé, l’option Partager avec **Outlook** ne s’affiche pas dans Teams pour l’utilisateur. Pour savoir comment activer et désactiver Outlook sur le web, voir Activer ou désactiver Outlook sur le web pour [une boîte aux lettres.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>E-mails d’activité actionnable

Les utilisateurs obtiennent automatiquement des e-mails d’activité manquée actionnables qui les aident à rattraper les conversations manquées dans Teams. Les messages d’activité manquées indiquent les dernières réponses d’une conversation, y compris  les messages qui ont été envoyés après le message manqué, et les utilisateurs peuvent cliquer sur Répondre pour répondre directement à partir d’Outlook. Pour en savoir plus, voir [Répondre aux e-mails d’activité manqués à partir d’Outlook.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Cette fonctionnalité n’est pas prise en charge dans Outlook pour Mac ni dans certaines versions antérieures d’Outlook pour Windows. Pour plus d’informations, voir [Messages actionnables dans Outlook et les groupes Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)

![Capture d’écran montrant un e-mail d’activité manquée](media/missed-activity-email.png)

![Capture d’écran montrant comment répondre à un message d’activité manquée](media/missed-activity-email-reply.png)

Vous pouvez utiliser l’cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) avec le paramètre **SmtpActionableMessagesEnabled** pour désactiver les e-mails actionnables. Par défaut, le **paramètre SmtpActionableMessagesEnabled** **est** true. La définition du paramètre sur **Faux** a pour fonction de couper le courrier électronique actionnable dans Office 365. Pour les utilisateurs de  Teams, cela signifie que l’option Répondre directement dans Outlook n’est pas disponible dans les e-mails d’activité manquée. Au lieu de cela, les e-mails d’activité manquées incluent une option Répondre dans **Teams** pour que les utilisateurs répondent dans Teams.
