---
title: Guide de démarrage rapide - Configuration des forfaits d’appels
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guide de démarrage rapide pour la configuration des plans d’appel dans Microsoft Teams afin de rendre un ensemble d’utilisateurs opérationnel.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101180"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams
==============================================================

Ce guide vous aide à configurer et à utiliser un ensemble d’utilisateurs pour leur permettre d’explorer les forfaits d’appels dans Teams.

Lire l’annonce des plans d’appel dans Teams du 12 décembre 2017 : [Intelligent Communications passe](https://aka.ms/ipyqus) à l’étape suivante avec les appels dans Teams

> [!NOTE]
> Nous vous recommandons, en parallèle de ce guide de démarrage rapide, de lire Phone System avec les [forfaits](calling-plan-landing-page.md) d’appels et [FastTrack](https://aka.ms/cloudvoice) pour planifier et conduire un déploiement réussi.

En ajoutant des forfaits d’appels, une fonctionnalité de Microsoft 365 et Office 365 optimisée par Skype Entreprise, vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques vers ou depuis des lignes fixes et des téléphones mobiles via le réseau téléphonique commuté (PSTN).

![Capture d’écran montrant la page Contacts dans Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Conditions préalables à l’activation de **l’onglet** Appels dans Teams
Pour activer  l’onglet Appels dans Teams, les utilisateurs doivent avoir des appels en tête-à-tête activés dans Teams et utiliser un client Teams qui prend en charge les appels 1:1 Teams. Pour découvrir comment gérer les appels en tête-à-tête dans Teams, lisez [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Pour connaître les clients qui supportent les appels, consultez les [limites et les spécifications de Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Pour l’instant, la messagerie vocale ne sera pas disponible dans l’onglet Appels, sauf si l’utilisateur est activé pour les appels PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions préalables à l’activation **du pavé de numérotation** dans Teams
Pour activer **l’onglet** Pavé de numérotation dans Teams et permettre à vos utilisateurs d’effectuer et de recevoir des appels PSTN, vous devez mettre en service les utilisateurs pour les forfaits téléphoniques et les plans d’appel. Pour découvrir comment configurer des forfaits d’appels, lisez [Configurer les forfaits d’appels.](./set-up-calling-plans.md)
De plus, pour les utilisateurs de Teams uniquement, vous devez vous assurer que la stratégie « Autoriser les appels privés » est activée dans la stratégie d’appel teams. Pour [plus d’informations, voir Gérer Teams lors](./manage-teams-skypeforbusiness-admin-center.md) de la transition vers le nouveau Centre d’administration Microsoft Teams.
> [!NOTE]
> Vous pouvez également utiliser le routage direct pour permettre à vos utilisateurs d’effectuer et de recevoir des appels RSTN. Pour découvrir comment configurer le routage direct, lisez [Configurer le routage direct.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Utilisation de TeamsUpgradePolicy pour contrôler la place des appels
Pour contrôler l’accès aux appels entrants (et aux conversations) dans Teams ou Skype Entreprise, les administrateurs utilisent TeamsUpgradePolicy, en utilisant le Centre d’administration [de Microsoft Teams](https://aka.ms/teamsadmincenter) ou une session de Windows PowerShell distante avec les cmdlets [Skype](/powershell/module/skype) Entreprise.


La configuration par défaut de TeamsUpgradePolicy est le mode Islands, qui est conçu pour garantir que les flux de travail d’entreprise existants ne soient pas interrompus pendant un déploiement Teams. Par défaut, les appels VoIP, PSTN et fédérés vers vos utilisateurs continueront d’être acheminés vers Skype Entreprise jusqu’à ce que vous actualisiez la stratégie pour activer les appels entrants vers Teams.  Lorsque les destinataires sont en mode îles :

 - Les appels VOIP entrants provenant de Skype Entreprise arrivent toujours dans le client Skype Entreprise du destinataire.
 - Les appels VOIP entrants en provenance de Teams arrivent dans Teams, si l’expéditeur et le destinataire *se trouvent dans le même client.*
 - Les appels VOIP fédérés entrants (quel que soit l’origine du client) et les appels PSTN arrivent toujours dans le client Skype Entreprise du destinataire.
 
Pour vous assurer que les appels VOIP et PSTN entrants arrivent toujours dans le client Teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, affectez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy.  Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec [Skype Entreprise.](./migration-interop-guidance-for-teams-with-skype.md)

**NOTES**
 - Les téléphones IP Skype Entreprise recevront des appels, même si l’utilisateur est en mode TeamsOnly.  
 - Les utilisateurs qui ont été mis en service avec des licences Système téléphonique et Forfaits d’appels pour une utilisation avec Skype Entreprise Online (par exemple, avec une valeur de OnlineVoiceRoutingPolicy) verront l’onglet Appels activé dans Teams et pourront passer des appels RSTN sortants de Teams sans que les administrateurs n’ont à prendre d’action administrative.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour recevoir tous les appels VOIP et PSTN entrants dans Teams
Pour vous assurer que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le Centre d’administration Microsoft Teams, ou utilisez la session de Windows PowerShell distante Skype Entreprise pour mettre à jour TeamsUpgradePolicy comme suit :

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Système téléphonique avec Forfaits d’appels](calling-plan-landing-page.md)

[Référence de l’cmdlet Skype Entreprise PowerShell](/powershell/module/skype)