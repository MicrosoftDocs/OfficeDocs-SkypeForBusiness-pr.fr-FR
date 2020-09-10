---
title: Équipe et intégration de la messagerie Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: En savoir plus sur les fonctionnalités d’intégration de la messagerie et des équipes et sur les fonctionnalités qui permettent aux utilisateurs de partager des informations entre le courrier électronique dans Outlook, les conversations ou les conversations par canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34498b73b70937eefcff267bc7a3b01068ab9557
ms.sourcegitcommit: 430aac8c5848fbcaf680ea447bfa2f9d5fa994e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420608"
---
# <a name="teams-and-outlook-email-integration"></a>Équipe et intégration de la messagerie Outlook

Microsoft teams inclut des fonctionnalités qui permettent aux utilisateurs de votre organisation de partager plus facilement des informations entre le courrier électronique dans Outlook, les conversations ou les conversations par canal dans Microsoft teams et de rester informé des conversations manquées. Cet article fournit une vue d’ensemble des fonctionnalités et des contrôles d’administration qui s’appliquent.

## <a name="share-to-outlook"></a>Partager dans Outlook

**Partager sur Outlook** permet aux utilisateurs de partager une copie d’une conversation d’équipe à un E-mail dans Outlook, sans avoir à quitter Teams. Cette fonctionnalité est utile si les utilisateurs ont besoin de partager des conversations ou des mises à jour d’État avec des utilisateurs en dehors de leur équipe immédiate ou même de votre organisation. Accédez au début de la conversation dans Teams, sélectionnez **̇ ̇ ̇ plus d’options**, puis sélectionnez **partager dans Outlook**.  Pour en savoir plus, voir [partager avec Outlook depuis teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Capture d’écran illustrant la fonctionnalité partager dans Outlook dans teams](media/share-to-outlook.png)

Pour utiliser cette fonctionnalité, Outlook sur le Web doit être activé pour l’utilisateur. Si Outlook n’est pas activé sur le Web, l’option **partager avec Outlook** ne s’affiche pas dans teams pour l’utilisateur. Pour plus d’informations sur l’activation et la désactivation d’Outlook sur le Web, voir [activer ou désactiver Outlook sur le Web pour une boîte aux lettres](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Messages d’activité interactifs

Les utilisateurs obtiennent automatiquement des messages d’activité manqués interactifs qui les aident à prendre des conversations manquées dans Teams. Les messages d’activité manqués indiquent les dernières réponses d’une conversation, y compris les messages envoyés après le message manqué, et les utilisateurs peuvent cliquer sur **répondre** pour répondre directement à partir d’Outlook. Pour plus d’informations, voir [répondre à des messages d’activité manqués d’Outlook et des messages interactifs](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) [dans les groupes outlook et Office 365](https://docs.microsoft.com/outlook/actionable-messages/).

![Capture d’écran montrant un e-mail d’activité manquée](media/missed-activity-email.png)

![Capture d’écran illustrant la façon de répondre à un message d’activité manquée](media/missed-activity-email-reply.png)

Vous pouvez utiliser l’applet de connexion [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) avec le paramètre **SmtpActionableMessagesEnabled** pour désactiver les messages exploitables. Par défaut, le paramètre **SmtpActionableMessagesEnabled** est défini sur **true**. La définition du paramètre sur **false** désactive les messages électroniques exploitables dans Office 365. Pour les utilisateurs d’équipes, cela signifie que l’option **répondre** pour répondre directement dans Outlook n’est pas disponible dans les messages d’activité manqués. Au lieu de cela, les messages d’activité manquées incluent une option **répondre dans teams** pour que les utilisateurs répondent dans Teams.
