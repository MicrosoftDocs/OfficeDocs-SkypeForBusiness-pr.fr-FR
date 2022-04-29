---
title: Gérer les connecteurs Microsoft 365 et personnalisés
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Avec les connecteurs, votre équipe reste au courant des dernières activités, en leur fournissant directement dans un canal du contenu et des mises à jour de services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 100db95adf900a48898515b9bb9a3a753b47de4f
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125439"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gérer les connecteurs Microsoft 365 et personnalisés

Pour maintenir la mise à jour de votre équipe, les connecteurs fournissent des mises à jour de contenu et de service fréquemment utilisées directement dans un canal Teams. Avec les connecteurs, vos utilisateurs Teams peuvent recevoir des mises à jour de services populaires tels que Trello, Wunderlist, GitHub et Azure DevOps Services. Les mises à jour sont publiées directement dans le flux de conversation de leur équipe.

Microsoft 365 connecteurs sont utilisés avec des groupes Microsoft Teams et Microsoft 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes. Les Microsoft Teams et les Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes. Toutefois, si vous désactivez les connecteurs configurés pour un groupe Microsoft 365, cela désactive également la possibilité pour le groupe Microsoft 365 de créer des connecteurs.

Tout membre d’une équipe peut connecter son équipe aux services cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont informés des activités de ce service. Les connecteurs continuent de fonctionner après le départ du membre qui a initialement configuré le connecteur. Tout membre d’équipe disposant des autorisations d’ajout ou de suppression peut modifier la configuration des connecteurs par d’autres membres.

## <a name="enable-or-disable-connectors-in-teams"></a>Activer ou désactiver des connecteurs dans Teams

Le module PowerShell V2 Exchange Online utilise l’authentification moderne et fonctionne avec l’authentification multifacteur, appelée MFA, pour se connecter à tous les environnements PowerShell Exchange associés dans Microsoft 365. Les administrateurs peuvent utiliser Exchange Online PowerShell pour désactiver les connecteurs d’un locataire entier ou d’une boîte aux lettres de groupe spécifique, ce qui affecte tous les utilisateurs de ce locataire ou boîte aux lettres. Il n’est pas possible de désactiver pour quelques utilisateurs spécifiques. En outre, les connecteurs sont désactivés par défaut pour Cloud de la communauté du secteur public, appelés locataires Cloud de la communauté du secteur public.

Le paramètre client remplace le paramètre de groupe. Par exemple, si un administrateur active les connecteurs pour le groupe et les désactive sur le locataire, les connecteurs du groupe sont désactivés. Pour activer un connecteur dans Teams, [connectez-vous à Exchange Online PowerShell à l’aide](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) de l’authentification moderne avec ou sans MFA.

### <a name="commands-to-enable-or-disable-connectors"></a>Commandes permettant d’activer ou de désactiver des connecteurs

Exécutez les commandes suivantes dans Exchange Online PowerShell :

* Pour désactiver les connecteurs pour le locataire : `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Pour désactiver les messages actionnables pour le locataire : `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Pour activer les connecteurs pour Teams, exécutez les commandes suivantes :
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Pour plus d’informations sur l’échange de modules PowerShell, consultez [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Pour activer ou désactiver Outlook connecteurs, [connectez des applications à vos groupes dans Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!---TBD: Delete this section after customer migration to new Webhook URL is complete --->

#### <a name="connector-url-update-notification"></a>Notification de mise à jour de l’URL du connecteur

Les connecteurs Teams passent à une nouvelle URL pour améliorer la sécurité. Pendant la transition, vous recevrez une notification pour mettre à jour le connecteur configuré. Mettez à jour votre connecteur au plus tôt pour éviter toute interruption des services de connecteur. Pour mettre à jour votre connecteur :

1. Dans la page de configuration des connecteurs, recherchez le message **Attention requise** en regard du connecteur configuré.

   ![Capture d’écran du message Attention requise.](media/Teams_Attention_Required_message.png)

1. Pour recréer la connexion pour les connecteurs webhook entrants, sélectionnez **Mettre à jour l’URL** et utilisez l’URL de webhook générée.

   ![Capture d’écran du bouton Mettre à jour l’URL.](media/Teams_update_URL_button.png)

1. Pour les autres types de connecteurs, supprimez le connecteur et recréez la configuration du connecteur. Une **URL est un message à jour** qui s’affiche.

   ![La capture d’écran de l’URL est un message à jour.](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>Voir aussi

* [Vue d’ensemble des connecteurs personnalisés et des webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Créer des connecteurs Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)