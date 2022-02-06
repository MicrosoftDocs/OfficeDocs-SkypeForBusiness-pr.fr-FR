---
title: Teams’intégration de Outlook messagerie électronique
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 'Découvrez les fonctionnalités Teams et Outlook’intégration de la messagerie électronique, notamment les fonctionnalités qui  letaient les utilisateurs à partager des informations entre les messages électroniques dans Outlook et les conversations ou les conversations de canal dans Teams.'
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="teams-and-outlook-email-integration"></a>Teams’intégration de Outlook messagerie électronique

Microsoft Teams inclut des fonctionnalités qui permet aux utilisateurs de votre organisation de partager facilement des informations entre les messages électroniques dans Outlook et les conversations de conversation ou de canal dans Teams et de rester au fait des conversations manquées. Cet article vous donne une vue d’ensemble de ces fonctionnalités et des contrôles d’administration qui s’appliquent.

## <a name="share-to-outlook"></a>Partager en Outlook

**Partager avec d Outlook** permet aux utilisateurs de partager une copie d’une conversation Teams à un e-mail dans Outlook, sans avoir à quitter Teams. Cette fonctionnalité est utile si les utilisateurs ont besoin de partager des conversations ou des mises à jour de statut avec des utilisateurs extérieurs à leur équipe immédiate ou même à votre organisation. Allez en haut de la conversation dans Teams, **sélectionnez s s « Autres options** » et sélectionnez **Partager Outlook**.  Pour plus d’informations, [voir Partager Outlook’Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Capture d’écran montrant la fonctionnalité Partager Outlook’Teams.](media/share-to-outlook.png)

Pour utiliser cette fonctionnalité, Outlook sur le web doit être désactivé pour l’utilisateur. Si Outlook sur le web est désactivé, l’option **Partager Outlook’est** pas affichée dans Teams pour l’utilisateur. Pour savoir comment activer et désactiver les Outlook sur le web, voir Activer ou désactiver Outlook sur le web [pour une boîte aux lettres](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>E-mails d’activité actionnable

Les utilisateurs obtiennent automatiquement des messages d’activité manquée actionnables qui les aident à rattraper les conversations manquées Teams. Les messages d’activité manquée indiquent les dernières réponses d’une conversation, y compris les messages qui ont été envoyés après le message manqué, et les utilisateurs peuvent cliquer sur Répondre pour répondre directement à partir d’Outlook. Pour en savoir plus, voir [Répondre aux e-mails d’activité manqué de Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Cette fonctionnalité n’est pas prise en charge dans Outlook pour Mac versions antérieures d’Outlook pour Windows. Pour plus d’informations, voir [Messages actionnables dans Outlook et Office 365 groupes](/outlook/actionable-messages/).

![Capture d’écran montrant un e-mail d’activité manquée.](media/missed-activity-email.png)

![Capture d’écran montrant comment répondre à un e-mail d’activité manquée.](media/missed-activity-email-reply.png)

Vous pouvez utiliser l’cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) avec le paramètre **SmtpActionableMessagesEnabled** pour désactiver les e-mails actionnables. Par défaut, le **paramètre SmtpActionableMessagesEnabled** est réglé sur **true**. La définition du paramètre sur **False** a pour rôle de couper ou de Office 365. Pour Teams utilisateurs, cela signifie que **l’option Répondre** directement dans Outlook n’est pas disponible dans les e-mails d’activité manquée. Au lieu de cela, les e-mails d’activité manquées incluent une option Répondre **dans** Teams que les utilisateurs peuvent répondre dans Teams.

Voir également [Messages actionnables dans Outlook et Office 365 Groupes d’équipes](/outlook/actionable-messages/).
