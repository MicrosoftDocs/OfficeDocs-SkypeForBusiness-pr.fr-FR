---
title: Guide de démarrage rapide - Configuration des forfaits d’appels
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guide de démarrage rapide pour la configuration des forfaits d’appels dans Microsoft Teams afin que vous puissiez obtenir un ensemble d’utilisateurs opérationnels.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789579"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams

Ce guide vous aide à mettre en place et à exécuter un ensemble d’utilisateurs afin qu’ils puissent explorer les forfaits d’appels dans Teams.

Lire l’annonce du 12 décembre 2017 des forfaits d’appels dans Teams : Les [communications intelligentes passent à l’étape suivante avec l’appel dans Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Nous vous recommandons de lire, parallèlement à ce guide de démarrage rapide, [le système téléphonique avec forfaits d’appels](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et piloter un déploiement réussi.

En ajoutant des forfaits d’appels - une fonctionnalité Microsoft 365 et Office 365 optimisée par Skype Entreprise - vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques vers ou depuis des lignes terrestres et des téléphones mobiles via le réseau téléphonique commuté (RTC).

![Capture d’écran montrant la page Contacts dans Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Conditions préalables à l’activation de l’onglet **Appels** dans Teams
Pour activer l’onglet **Appels** dans Teams, les utilisateurs doivent activer l’appel 1:1 dans Teams et utiliser un client Teams qui prend en charge l’appel Teams 1:1. Pour savoir comment gérer les appels 1:1 dans Teams, lisez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Pour savoir quels clients prennent en charge les appels, lisez [les limites et les spécifications de Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> Actuellement, la messagerie vocale ne sera pas disponible dans l’onglet Appels, sauf si l’utilisateur est activé pour les appels RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions préalables à l’activation du **pavé de numérotation** dans Teams
Pour activer l’onglet **Pavé de numérotation** dans Teams et permettre à vos utilisateurs d’effectuer et de recevoir des appels RTC, vous devez approvisionner les utilisateurs pour le système téléphonique et les forfaits d’appels. Pour savoir comment configurer des forfaits d’appels, lisez [Configurer les plans d’appel](./set-up-calling-plans.md).
En outre, pour Les utilisateurs Teams uniquement, vous devez vous assurer que « Autoriser les appels privés » est activé dans la stratégie d’appel Teams. Pour plus d’informations, consultez [Gérer Teams pendant la transition vers le nouveau Centre](./manage-teams-skypeforbusiness-admin-center.md) d’administration Microsoft Teams.
> [!NOTE]
> Vous pouvez également utiliser le routage direct pour permettre à vos utilisateurs d’effectuer et de recevoir des appels RTC. Pour savoir comment configurer le routage direct, consultez [Configurer le routage direct](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Utilisation de TeamsUpgradePolicy pour contrôler l’emplacement des appels
Pour contrôler si les appels entrants (et les conversations) arrivent dans Teams ou Skype Entreprise, les administrateurs utilisent TeamsUpgradePolicy, à l’aide du [Centre d’administration Microsoft Teams](https://aka.ms/teamsadmincenter) ou d’une session de Windows PowerShell distante avec les [applets de commande Skype Entreprise](/powershell/module/skype).


La configuration par défaut de TeamsUpgradePolicy est le mode Islands, qui est conçu pour garantir que les workflows métier existants ne sont pas interrompus pendant un déploiement Teams. Par défaut, les appels VoIP, PSTN et fédérés à vos utilisateurs continueront d’être acheminés vers Skype Entreprise jusqu’à ce que vous mettiez à jour la stratégie pour activer les appels entrants vers Teams.  Lorsque les destinataires sont en mode îles :

 - Les appels VOIP entrants qui proviennent de Skype Entreprise arrivent toujours dans le client Skype Entreprise du destinataire.
 - Les appels VOIP entrants qui proviennent de Teams arrivent dans Teams *, si l’expéditeur et le récepteur se trouvent dans le même locataire*.
 - Les appels VOIP fédérés entrants (quel que soit le client d’origine) et les appels RTC arrivent toujours dans le client Skype Entreprise du destinataire.
 
Pour vous assurer que les appels VOIP et PSTN entrants arrivent toujours dans le client Teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (ce qui signifie que vous lui affectez l’instance « UpgradeToTeams » de TeamsUpgradePolicy.  Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, consultez [les conseils sur la migration et l’interopérabilité pour les organisations utilisant Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

**NOTES**
 - Skype Entreprise téléphones IP recevront des appels, même si l’utilisateur est en mode TeamsOnly.  
 - Les utilisateurs qui ont été approvisionnés avec des licences de système téléphonique et de forfaits d’appels pour une utilisation avec Skype Entreprise Online (par exemple, ils ont reçu la valeur OnlineVoiceRoutingPolicy), ont l’onglet Appels activés dans Teams et peuvent passer des appels RTC sortants à partir de Teams sans que les administrateurs aient à prendre des mesures administratives.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour qu’ils reçoivent tous les appels VOIP et RTC entrants dans Teams
Pour vous assurer que les utilisateurs reçoivent tous les appels VOIP et RTC entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le Centre d’administration Microsoft Teams, ou utilisez Skype Entreprise session de Windows PowerShell distante pour mettre à jour TeamsUpgradePolicy comme suit :

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Système téléphonique avec Forfaits d’appels](calling-plan-landing-page.md)

[Skype Entreprise référence d’applet de commande PowerShell](/powershell/module/skype)
