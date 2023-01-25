---
title: Gérer les connecteurs Microsoft 365 et les connecteurs personnalisés
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment les connecteurs permettent à votre équipe de rester à jour en fournissant fréquemment du contenu et des mises à jour directement dans un canal Teams pour les services que vous utilisez.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983682"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Gérer les connecteurs Microsoft 365 et les connecteurs personnalisés

Les connecteurs dans Microsoft Teams fournissent des mises à jour de contenu et de service directement à partir de services tiers dans un canal Teams. À l’aide de connecteurs, les utilisateurs reçoivent des mises à jour de services populaires tels que Trello, Wunderlist, GitHub et Azure DevOps Services. Les mises à jour sont publiées directement dans le flux de conversation. Cela permet à tous les membres de rester synchronisés et de recevoir rapidement les informations pertinentes.

Les connecteurs Microsoft 365 sont utilisés avec les groupes Teams et Microsoft 365. Vous pouvez utiliser les mêmes connecteurs dans Teams et Microsoft Exchange. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

Si les autorisations d’équipe le permettent, tout membre d’une équipe peut ajouter un connecteur dans l’équipe et tous les membres de l’équipe sont avertis des activités de ce service. Tout membre d’équipe disposant des autorisations d’ajout ou de suppression peut modifier la configuration des connecteurs par d’autres membres.

## <a name="enable-or-disable-connectors-in-teams"></a>Activer ou désactiver des connecteurs dans Teams

Le module Exchange Online PowerShell v2 utilise l’authentification moderne et fonctionne avec l’authentification multifacteur (MFA) pour se connecter à tous les environnements PowerShell associés à Exchange dans Microsoft 365. Les administrateurs peuvent utiliser Exchange Online PowerShell pour désactiver les connecteurs d’un client entier ou d’une boîte aux lettres de groupe spécifique, ce qui affecte tous les utilisateurs de ce locataire ou boîte aux lettres. Il n’est pas possible de désactiver pour quelques utilisateurs spécifiques.

Le paramètre client remplace le paramètre de groupe. Par exemple, si un administrateur active les connecteurs pour le groupe et les désactive sur le client, les connecteurs du groupe sont désactivés. Pour activer un connecteur dans Teams, [connectez-vous à Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) à l’aide de l’authentification moderne avec ou sans MFA.

Pour activer ou désactiver un connecteur, exécutez les commandes suivantes dans Exchange Online PowerShell :

* Pour désactiver les connecteurs pour le client : `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Pour désactiver les messages actionnables pour le client : `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Pour activer les connecteurs pour Teams, exécutez les commandes suivantes :
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Pour plus d’informations sur Exchange module PowerShell, consultez [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Pour activer ou désactiver des connecteurs Outlook, [connectez des applications à vos groupes dans Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Publier des connecteurs pour votre organisation

Pour mettre un connecteur personnalisé à la disposition des utilisateurs de votre organisation, chargez une application de connecteur personnalisée dans le catalogue d’applications de votre organisation. Les utilisateurs finaux au sein de l’organisation peuvent installer, configurer et utiliser le connecteur dans une équipe.

> [!IMPORTANT]
> Les connecteurs personnalisés ne sont pas disponibles dans les environnements Cloud de la communauté du secteur public (GCC), Government Community Cloud-High (GCCH) et DoD (Department of Defense).

Pour utiliser des connecteurs dans une équipe ou un canal, ouvrez le menu Plus d’options dans le coin supérieur droit d’un canal. Dans le menu, sélectionnez **Connecteurs**, puis localisez ou recherchez le connecteur requis. Configurez le connecteur sélectionné si nécessaire.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Ajoutez des connecteurs à votre canal dans Teams à partir des options Plus dans le coin supérieur droit du canal.":::

## <a name="update-url-of-a-connector"></a>Mettre à jour l'URL d'un connecteur

Les connecteurs Teams passent à une nouvelle URL pour renforcer la sécurité. Pendant la transition, vous recevrez une notification pour mettre à jour le connecteur configuré. Mettez à jour votre connecteur au plus tôt pour éviter toute interruption des services du connecteur. Pour mettre à jour votre connecteur :

1. Dans la page de configuration des connecteurs, recherchez le message **Attention requise** en regard du connecteur configuré.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Capture d’écran du message Attention requise.":::

1. Pour recréer la connexion pour les connecteurs de webhooks entrants, sélectionnez **Mettre à jour l'URL** et utilisez l'URL de webhook générée.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Capture d’écran du bouton Mettre à jour l’URL.":::

1. Pour les autres types de connecteurs, supprimez le connecteur et recréez la configuration du connecteur. Un message **L’URL est à jour** s'affiche.

   :::image type="content" source="media/teams-url-updated.png" alt-text="La capture du message L’URL est à jour.":::

## <a name="considerations-when-using-connectors-in-teams"></a>Considérations relatives à l’utilisation de connecteurs dans Teams

* Les connecteurs sont désactivés par défaut dans les environnements de la Cloud de la communauté du secteur public (GCC). Pour les activer, définissez les paramètres `ConnectorsEnabled` ou `ConnectorsEnabledForTeams` sur `$true` avec l’applet de commande `SetOrganizationConfig`. Connectez-vous à [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

* Si l’utilisateur qui a ajouté un connecteur à une équipe quitte l’équipe, le connecteur continue de fonctionner.

* Les connecteurs suivants ne sont pas disponibles à partir de janvier 2023 :

  * AHA
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * BEANSTALK
  * BITBUCKET
  * BITBUCKETSERVER
  * COPAIN
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * GROOVE
  * HEROKU
  * HONEYBADGER
  * INTERPHONE
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ARCEAU
  * RUNSCOPE
  * SATISMETER
  * SÉMAPHORE
  * SENTRY
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * SUBVERSION
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>Articles connexes

* [Vue d’ensemble des connecteurs personnalisés et des webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Comment créer des connecteurs Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
