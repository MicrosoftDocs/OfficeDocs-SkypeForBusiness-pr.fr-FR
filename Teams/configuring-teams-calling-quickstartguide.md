---
title: Guide de démarrage rapide - Configuration des forfaits d'appels dans Microsoft Teams
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Guide de démarrage rapide pour la configuration des plans d’appel dans Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304436"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams
==============================================================

Ce guide vous aidera à obtenir un ensemble d’utilisateurs up et en cours d’exécution afin qu’ils peuvent Explorer appelant Plans dans les équipes.

Lire l’annonce 12 décembre 2017, des Plans de l’appel dans les équipes : [Communications Intelligent prend l’étape suivante avec l’appel dans les équipes](https://aka.ms/ipyqus)

> [!NOTE]
> Nous vous recommandons, en parallèle avec ce guide de démarrage rapide, lire [Système téléphonique avec des Plans de l’appel](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) plan et lecteur de réussir votre déploiement.

En ajoutant l’appel Plans - une fonctionnalité Office 365 par Skype pour les entreprises - vous pouvez maintenant utiliser des équipes pour émettre et recevoir des appels téléphoniques vers ou à partir des lignes terrain et téléphones mobiles via le réseau téléphonique commuté (RTC).

![L’appel dans les équipes](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Conditions requises pour l’activation de l’onglet **appels** dans les équipes
Pour activer l’onglet **appels** dans les équipes, les utilisateurs doivent disposer de 1:1 appel activé dans les équipes et à l’aide d’un client équipes qui prend en charge les équipes de 1:1 appel. Pour savoir comment gérer l’appel de 1:1 dans les équipes, consultez [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Pour savoir quels clients prennent en charge l’appel, lisez [les spécifications pour les équipes Microsoft et limites](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Actuellement, la messagerie vocale ne sera pas disponible dans l’onglet appels, sauf si l’utilisateur est activé pour les appels PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions requises pour l’activation du **Pavé de numérotation** dans les équipes
Pour activer l’onglet **Pavé de numérotation** dans les équipes et autoriser les utilisateurs à émettre et recevoir des appels PSTN, vous devrez mettre en service des utilisateurs pour le système téléphonique et Plans de l’appel. Pour savoir comment configurer des Plans de l’appel, lisez [configurer des Plans de l’appel](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Vous pouvez également utiliser le routage Direct pour autoriser les utilisateurs à émettre et recevoir des appels PSTN. Pour savoir comment configurer le routage Direct, consultez [Configurer le routage Direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>À l’aide de TeamsUpgradePolicy au contrôle où les appels atteindre
Pour contrôler si les appels entrants (et salles de conversation) atteindre dans des équipes ou Skype pour les entreprises, les administrateurs utilisent TeamsUpgradePolicy, à l’aide d’un [Centre d’administration de Microsoft équipes](https://aka.ms/teamsadmincenter) ou une session Windows PowerShell à distance avec la [Skype pour les entreprises](https://docs.microsoft.com/powershell/module/skype) applets de commande.


La configuration par défaut de TeamsUpgradePolicy est le mode (îles), qui est conçu pour s’assurer que des professionnels de flux de travail n’est pas interrompu pendant un déploiement d’équipes. Par défaut, VoIP, PSTN et les appels fédérés à vos utilisateurs continuera à être acheminés vers Skype pour les entreprises jusqu'à ce que vous mettez à jour la stratégie pour activer les appels entrants aux équipes.  Lorsque les destinataires sont en mode (îles) :

 - VOIP entrant appelle que Skype origine dans for Business toujours terrestre dans Skype du destinataire pour le client d’entreprise.
 - VOIP entrant appelle à l’origine de terrain d’équipes dans les équipes, *Si l’expéditeur et le destinataire sont sur le même client*.
 - Entrant fédérés VOIP (quel que soit le client provient) et appels PSTN toujours terrestre dans Skype du destinataire pour le client d’entreprise.
 
Pour vous assurer qu’entrant VOIP et PSTN appelle toujours terrestre dans un client de l’utilisateur équipes, mettre à jour en mode de coexistence de l’utilisateur pour être TeamsOnly (c'est-à-dire, les assigner l’instance de « UpgradeToTeams » de TeamsUpgradePolicy.  Pour plus d’informations sur les modes de coexistence et de TeamsUpgradePolicy, voir [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**NOTES**
 - Skype pour les téléphones IP Business recevra les appels, même si l’utilisateur est en mode TeamsOnly.  
 - Utilisateurs qui ont été mis en service avec un système téléphonique et appel des Plans de licences pour une utilisation avec Skype pour Business Online (par exemple, ils ont été assignés une valeur de OnlineVoiceRoutingPolicy), l’onglet appels activés dans les équipes et peuvent passer des appels PSTN sortants à partir de Équipes sans avoir à aucune action d’administration des administrateurs.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour la réception de tous les VOIP et PSTN entrants des appels dans les équipes
Pour garantir que les utilisateurs reçoivent tous les appels entrants VOIP et PSTN dans les équipes, définit le mode de coexistence de l’utilisateur TeamsOnly dans le centre d’administration Microsoft Teams, ou bien utilisez Skype pour la session Windows PowerShell à distance Business pour mettre à jour TeamsUpgradePolicy comme suit :

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Système téléphonique avec les Plans d’appel](calling-plan-landing-page.md)

[Skype pour référence d’applet de commande PowerShell Business](https://docs.microsoft.com/powershell/module/skype)

