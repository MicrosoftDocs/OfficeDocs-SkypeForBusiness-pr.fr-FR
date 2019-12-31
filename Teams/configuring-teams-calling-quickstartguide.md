---
title: Guide de démarrage rapide - Configuration des forfaits d'appels dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guide de mise en route pour la configuration des offres d’appel dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0bebe58780456435388f9f5c2b5ef75478dda12
ms.sourcegitcommit: e59914458b4c22cc12556795468bc019e00a8940
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/30/2019
ms.locfileid: "40910002"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams
==============================================================

Ce guide va vous aider à mettre en route un ensemble d’utilisateurs afin qu’ils puissent explorer les plans d’appel dans Teams.

Lire le 12 décembre 2017, annonce des plans d’appel dans teams : [les communications intelligentes prennent l’étape suivante avec les appels dans teams](https://aka.ms/ipyqus)

> [!NOTE]
> Dans le cas d’un guide de démarrage rapide, nous vous conseillons de lire le [système téléphonique avec les offres d’appel](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et conduire un déploiement réussi.

En ajoutant des plans d’appel, une fonctionnalité de 365 Office gérée par Skype entreprise, vous pouvez désormais utiliser les équipes pour passer et recevoir des appels téléphoniques vers des lignes fixes et mobiles via le réseau téléphonique public commuté (RTC).

![Capture d’écran montrant la page contacts dans teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Conditions préalables à l’activation de l’onglet **appels** dans teams
Pour activer l’onglet **appels** dans équipes, les utilisateurs doivent avoir activé l’appel 1:1 dans teams et utiliser un client teams prenant en charge les appels d’équipes 1:1. Pour savoir comment gérer les appels 1:1 dans Teams, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Pour savoir quels clients prennent en charge les appels, prenez connaissance des [limites et des caractéristiques de Microsoft teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Pour le moment, la boîte vocale n’est pas disponible sous l’onglet appels, sauf si l’utilisateur est autorisé à utiliser les appels RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions préalables à l’activation du **pavé de numérotation** dans teams
Pour activer l’onglet **pavé de numérotation** dans teams et permettre aux utilisateurs de passer et de recevoir des appels RTC, vous devez configurer les utilisateurs pour le système téléphonique et les offres d’appels. Pour plus d’informations sur la configuration des forfaits d’appel, consultez la rubrique [configurer les offres d’appels](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).
En outre, pour les utilisateurs d’équipes uniquement, vous devez vous assurer que l’option « autoriser les appels privés » est activée dans la stratégie d’appel d’équipes. Pour plus d’informations, voir [gérer les équipes lors de la transition vers le nouveau centre d’administration Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) .
> [!NOTE]
> Vous pouvez également utiliser le routage direct pour autoriser vos utilisateurs à passer et à recevoir des appels PSTN. Pour savoir comment configurer le routage direct, voir [configurer le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Utilisation de TeamsUpgradePolicy pour contrôler les appels terrestres
Pour contrôler si les appels entrants (et les discussions) dans teams ou Skype entreprise, les administrateurs utilisent TeamsUpgradePolicy, à l’aide du [Centre d’administration Microsoft teams](https://aka.ms/teamsadmincenter) ou à l’aide d’une session Windows PowerShell distante avec les applets [de commande Skype entreprise](https://docs.microsoft.com/powershell/module/skype) .


La configuration par défaut de TeamsUpgradePolicy est le mode îlot, qui est conçu pour garantir que les flux de travail d’entreprise existants ne sont pas interrompus lors du déploiement d’équipes. Par défaut, les appels VoIP, RTC et fédérés vers vos utilisateurs continuent d’être routés vers Skype entreprise tant que vous n’avez pas mis à jour la stratégie pour autoriser les appels entrants vers Teams.  Lorsque les destinataires sont en mode îlot :

 - Les appels VOIP entrants à l’origine de Skype entreprise sont toujours terrains dans le client Skype entreprise du destinataire.
 - Appels VOIP entrants à l’origine dans teams en équipe, *si l’expéditeur et le destinataire se trouvent dans le même client*.
 - Le VOIP fédéré entrant (quel que soit le client qu’il contient) et les appels RTC sont toujours terrains dans le client Skype entreprise du destinataire.
 
Pour vous assurer que les appels VOIP et PSTN entrants restent toujours dans le client teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, attribuez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy.  Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, voir [conseils de migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) .

**NOTES**
 - Les téléphones IP Skype entreprise recevront des appels, même s’ils sont en mode TeamsOnly.  
 - Les utilisateurs qui ont été configurés avec un système téléphonique et des offres d’appels d’offres pour une utilisation avec Skype entreprise Online (par exemple, une valeur de OnlineVoiceRoutingPolicy), l’onglet appels est activé dans teams et peuvent passer des appels RTC Équipes sans qu’ils aient à effectuer d’action administrative.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour qu’ils reçoivent tous les appels VOIP et PSTN entrants dans teams
Pour garantir que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le centre d’administration de Microsoft Teams, ou utilisez la session Windows PowerShell Skype entreprise à distance pour mettre à jour TeamsUpgradePolicy comme suit :

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Système téléphonique avec forfaits d’appels](calling-plan-landing-page.md)

[Référence sur les applets de passe Skype entreprise PowerShell](https://docs.microsoft.com/powershell/module/skype)

