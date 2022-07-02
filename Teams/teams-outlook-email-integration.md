---
title: Intégration des e-mails Teams et Outlook
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez les fonctionnalités d’intégration des e-mails Teams et Outlook, notamment les fonctionnalités qui permettent aux utilisateurs de partager des informations entre les e-mails dans Outlook et les conversations de conversation ou de canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606233"
---
# <a name="teams-and-outlook-email-integration"></a>Intégration des e-mails Teams et Outlook

Microsoft Teams inclut des fonctionnalités qui permettent aux utilisateurs de votre organisation de partager facilement des informations entre les e-mails dans Outlook et les conversations de conversation ou de canal dans Teams et de rester informés des conversations manquées. Cet article vous donne une vue d’ensemble de ces fonctionnalités et des contrôles d’administration qui s’appliquent.

## <a name="share-to-outlook"></a>Partager vers Outlook

**Partager vers Outlook permet aux** utilisateurs de partager une copie d’une conversation Teams vers un e-mail dans Outlook, sans avoir à quitter Teams. Cette fonctionnalité est pratique si les utilisateurs doivent partager des conversations ou des mises à jour d’état avec des utilisateurs extérieurs à leur équipe immédiate ou même à votre organisation. Accédez en haut de la conversation dans Teams, sélectionnez **... Plus d’options**, puis **sélectionnez Partager vers Outlook**.  Pour plus d’informations, consultez [Partager vers Outlook à partir de Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Capture d’écran montrant la fonctionnalité Partager vers Outlook dans Teams.](media/share-to-outlook.png)

Pour utiliser cette fonctionnalité, Outlook sur le web doit être activée pour l’utilisateur. Si Outlook sur le web est désactivé, l’option **Partager vers Outlook** n’est pas affichée dans Teams pour l’utilisateur. Pour savoir comment activer et désactiver Outlook sur le web, consultez [Activer ou désactiver Outlook sur le web pour une boîte aux lettres](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>E-mails d’activité actionnables

Les utilisateurs reçoivent automatiquement des e-mails d’activité manqués actionnables qui les aident à rattraper les conversations manquées dans Teams. Les e-mails d’activité manqués affichent les dernières réponses d’une conversation, y compris les messages qui ont été envoyés après le message manqué, et les utilisateurs peuvent cliquer sur **Répondre** pour répondre directement à partir d’Outlook. Pour en savoir plus, consultez [Répondre aux e-mails d’activité manqués d’Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Cette fonctionnalité n’est pas prise en charge dans Outlook pour Mac ou certaines versions antérieures d’Outlook pour Windows. Pour plus d’informations, consultez [messages actionnables dans Outlook et les groupes Office 365](/outlook/actionable-messages/).

![Capture d’écran montrant un e-mail d’activité manqué.](media/missed-activity-email.png)

![Capture d’écran montrant comment répondre à un e-mail d’activité manqué.](media/missed-activity-email-reply.png)

Vous pouvez utiliser l’applet de commande [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) avec le paramètre **SmtpActionableMessagesEnabled** pour désactiver les e-mails actionnables. Par défaut, le paramètre **SmtpActionableMessagesEnabled** a la **valeur true**. La définition du paramètre sur **false** désactive les messages électroniques actionnables dans Office 365. Pour les utilisateurs Teams, cela signifie que l’option **Répondre** pour répondre directement dans Outlook n’est pas disponible dans les e-mails d’activité manqués. Au lieu de cela, les e-mails d’activité manqués incluent une option **Répondre dans Teams** permettant aux utilisateurs de répondre dans Teams.

Consultez également [les messages actionnables dans Outlook et les groupes Office 365](/outlook/actionable-messages/).
