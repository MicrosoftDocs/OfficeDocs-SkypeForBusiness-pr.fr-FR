---
title: Guide de démarrage rapide - Configuration des forfaits d’appels
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guide de démarrage rapide pour configurer des plans d’appel Microsoft Teams vous pouvez rendre un ensemble d’utilisateurs opérationnel.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeb9fae94d186e841cdacbd05879ab2891b9ba2a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745690"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams

Ce guide vous aide à rendre un ensemble d’utilisateurs opérationnels pour leur permettre d’explorer les forfaits d’appels Teams.

Lire l’annonce des plans d’appels du 12 décembre 2017 dans Teams : Intelligent [Communications passe](https://aka.ms/ipyqus) à l’étape suivante avec les appels dans Teams

> [!NOTE]
> Nous vous recommandons, en parallèle de ce guide de démarrage rapide, de lire les Système téléphonique des [plans](calling-plan-landing-page.md) d’appels et des FastTrack pour planifier et conduire un déploiement réussi. [](https://aka.ms/cloudvoice)

En ajoutant des forfaits d’appels, une fonctionnalité de Microsoft 365 et de Office 365 optimisée par Skype Entreprise, vous pouvez désormais utiliser Teams pour passer et recevoir des appels vers ou depuis des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).

![Capture d’écran montrant la page Contacts dans Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Conditions préalables à l’activation **de l’onglet** Appels dans Teams
Pour activer  l’onglet Appels dans Teams les utilisateurs doivent avoir activé les appels en face à face dans Teams et utiliser un client Teams qui prend en charge les appels Teams en deux temps. Pour découvrir comment gérer les appels 1:1 dans Teams, lisez [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy) Pour savoir quels clients prendre en charge les appels, consultez les [limites et spécifications pour Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Pour l’instant, la messagerie vocale ne sera pas disponible dans l’onglet Appels, sauf si l’utilisateur est activé pour les appels PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions préalables à l’activation **du pavé de numérotation** Teams
Pour activer  l’onglet Pavé de numérotation dans Teams et permettre à vos utilisateurs d’effectuer et de recevoir des appels PSTN, vous devez mettre en service les utilisateurs pour les plans de Système téléphonique et d’appel. Pour découvrir comment configurer des forfaits d’appels, lisez [Configurer les forfaits d’appels.](./set-up-calling-plans.md)
De plus, pour Teams utilisateurs uniquement, vous devez vous assurer que la stratégie « Autoriser les appels privés » est activée dans la Teams d’appel. Pour [plus d Teams informations, voir](./manage-teams-skypeforbusiness-admin-center.md) Gérer les Teams pendant la transition vers le nouveau centre Microsoft Teams’administration.
> [!NOTE]
> Vous pouvez également utiliser le routage direct pour permettre à vos utilisateurs d’effectuer et de recevoir des appels RSTN. Pour découvrir comment configurer le routage direct, lisez [Configurer le routage direct.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Utilisation de TeamsUpgradePolicy pour contrôler la place des appels
Pour contrôler l’accès aux appels entrants (et aux conversations) dans Teams ou Skype Entreprise, les administrateurs utilisent TeamsUpgradePolicy, en utilisant le Centre d’administration [Microsoft Teams](https://aka.ms/teamsadmincenter) ou une session de Windows PowerShell distante avec le [Skype Entreprise](/powershell/module/skype) des cmdlets.


La configuration par défaut de TeamsUpgradePolicy est le mode Îles, qui est conçu pour garantir que les flux de travail existants d’entreprise ne soient pas interrompus pendant un Teams automatique. Par défaut, les appels VoIP, PSTN et fédérés vers vos utilisateurs continueront d’être acheminés vers Skype Entreprise jusqu’à ce que vous mettez à jour la stratégie pour activer les appels entrants vers Teams.  Lorsque les destinataires sont en mode îles :

 - Les appels VOIP entrants provenant de Skype Entreprise arrivent toujours dans le client de Skype Entreprise destinataire.
 - Appels VOIP entrants provenant d’un Teams entrants sur Teams, si l’expéditeur et le destinataire se *trouvent dans le même client.*
 - Les appels VOIP fédérés entrants (quel que soit l’origine du client) et les appels PSTN arrivent toujours dans le client Skype Entreprise destinataire.
 
Pour vous assurer que les appels VOIP et PSTN entrants arrivent toujours dans le client Teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, affectez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy).  Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec [d Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

**NOTES**
 - Skype Entreprise Les téléphones IP recevront des appels, même si l’utilisateur est en mode TeamsOnly.  
 - Les utilisateurs qui ont été mis en service avec des licences Système téléphonique et Forfaits d’appels pour une utilisation avec Skype Entreprise Online (par exemple, une valeur de OnlineVoiceRoutingPolicy) verront l’onglet Appels activé dans Teams et pourront passer des appels RSTN sortants à partir d’Teams sans que les administrateurs n’ont à prendre d’mesures administratives.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour recevoir tous les appels VOIP et PSTN entrants dans Teams
Pour vous assurer que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le Centre d’administration Microsoft Teams ou utilisez une session Windows PowerShell distante de Skype Entreprise pour mettre à jour TeamsUpgradePolicy comme suit :

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Système téléphonique avec Forfaits d’appels](calling-plan-landing-page.md)

[Skype Entreprise Référence de l’cmdlet PowerShell](/powershell/module/skype)
