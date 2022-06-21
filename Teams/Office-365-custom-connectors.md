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
description: Découvrez comment les connecteurs maintiennent votre équipe à jour en fournissant fréquemment du contenu et des mises à jour directement dans un canal Teams pour les services que vous utilisez.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: de0c0398d511aca05a69220e0e35a28268535c59
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190444"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gérer les connecteurs Microsoft 365 et personnalisés

Pour maintenir la mise à jour de votre équipe, les connecteurs fournissent des mises à jour de contenu et de service fréquemment utilisées directement dans un canal Teams. Avec les connecteurs, vos utilisateurs Teams peuvent recevoir des mises à jour de services populaires tels que Trello, Wunderlist, GitHub et Azure DevOps Services. Les mises à jour sont publiées directement dans le flux de conversation de leur équipe.

Microsoft 365 connecteurs sont utilisés avec des groupes Microsoft Teams et Microsoft 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes. Les Microsoft Teams et les Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes. Toutefois, si vous désactivez les connecteurs configurés pour un groupe Microsoft 365, cela désactive également la possibilité pour le groupe Microsoft 365 de créer des connecteurs.

Tout membre d’une équipe peut connecter son équipe aux services cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont informés des activités de ce service. Les connecteurs continuent de fonctionner après le départ du membre qui a initialement configuré le connecteur. Tout membre d’équipe disposant des autorisations d’ajout ou de suppression peut modifier la configuration des connecteurs par d’autres membres.

## <a name="enable-or-disable-connectors-in-teams"></a>Activer ou désactiver des connecteurs dans Teams

Le module PowerShell V2 Exchange Online utilise l’authentification moderne et fonctionne avec l’authentification multifacteur, appelée MFA, pour se connecter à tous les environnements PowerShell Exchange associés dans Microsoft 365. Les administrateurs peuvent utiliser Exchange Online PowerShell pour désactiver les connecteurs d’un locataire entier ou d’une boîte aux lettres de groupe spécifique, ce qui affecte tous les utilisateurs de ce locataire ou boîte aux lettres. Il n’est pas possible de désactiver pour quelques utilisateurs spécifiques. En outre, les connecteurs sont désactivés par défaut pour Cloud de la communauté du secteur public, appelés locataires Cloud de la communauté du secteur public.

Le paramètre client remplace le paramètre de groupe. Par exemple, si un administrateur active les connecteurs pour le groupe et les désactive sur le locataire, les connecteurs du groupe sont désactivés. Pour activer un connecteur dans Teams, [connectez-vous à Exchange Online PowerShell à l’aide](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) de l’authentification moderne avec ou sans MFA.

Pour activer ou désactiver un connecteur, exécutez les commandes suivantes dans Exchange Online PowerShell :

* Pour désactiver les connecteurs pour le locataire : `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Pour désactiver les messages actionnables pour le locataire : `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Pour activer les connecteurs pour Teams, exécutez les commandes suivantes :
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Pour plus d’informations sur l’échange de modules PowerShell, consultez [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Pour activer ou désactiver Outlook connecteurs, [connectez des applications à vos groupes dans Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Publier des connecteurs pour votre organisation

Si vous souhaitez qu’un connecteur personnalisé soit disponible uniquement pour les utilisateurs de votre organisation, vous pouvez charger une application de connecteur personnalisée dans le catalogue d’applications de votre organisation. Après avoir chargé le package d’application, les utilisateurs finaux peuvent installer le connecteur à partir du catalogue d’applications de l’organisation et configurer et utiliser le connecteur dans une équipe.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> Les connecteurs personnalisés ne sont pas disponibles dans Cloud de la communauté du secteur public (Cloud de la communauté du secteur public), Cloud de la communauté du secteur public-High et department of Defense (DOD).

Pour utiliser des connecteurs dans une équipe ou un canal, ouvrez le menu Plus d’options dans le coin supérieur droit d’un canal. Dans le menu, sélectionnez **Connecteurs** , puis recherchez ou recherchez l’application de connecteur requise. Configurez le connecteur sélectionné si nécessaire.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Ajoutez des connecteurs à votre canal dans Teams à partir des options Plus dans le coin supérieur droit du canal.":::

## <a name="update-url-of-a-connector"></a>Mettre à jour l’URL d’un connecteur

Les connecteurs Teams passent à une nouvelle URL pour améliorer la sécurité. Pendant la transition, vous recevrez une notification pour mettre à jour le connecteur configuré. Mettez à jour votre connecteur au plus tôt pour éviter toute interruption des services de connecteur. Pour mettre à jour votre connecteur :

1. Dans la page de configuration des connecteurs, recherchez le message **Attention requise** en regard du connecteur configuré.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Capture d’écran du message Attention requise.":::

1. Pour recréer la connexion pour les connecteurs webhook entrants, sélectionnez **Mettre à jour l’URL** et utilisez l’URL de webhook générée.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Capture d’écran du bouton Mettre à jour l’URL.":::

1. Pour les autres types de connecteurs, supprimez le connecteur et recréez la configuration du connecteur. Une **URL est un message à jour** qui s’affiche.

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="La capture d’écran de l’URL est un message à jour.":::

## <a name="see-also"></a>Voir aussi

* [Vue d’ensemble des connecteurs et webhooks personnalisés](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Créer des connecteurs Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
