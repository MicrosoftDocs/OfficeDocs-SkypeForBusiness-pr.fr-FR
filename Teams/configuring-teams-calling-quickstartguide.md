---
title: "Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guide de démarrage rapide pour la configuration des forfaits d'appels dans Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f3145455553c8126d66b3e56b69ec646f5f19ad
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530695"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams
==============================================================

Ce guide vous aidera à définir un ensemble d'utilisateurs prêts à utiliser les forfaits d'appels dans Teams.

Lisez l'annonce du 12 décembre 2017 sur les forfaits d'appels dans Teams : [Les communications intelligentes passent la vitesse supérieure avec les appels dans Teams](https://aka.ms/ipyqus)

> [!NOTE]
> En parallèle de ce guide de démarrage rapide, nous vous recommandons de consulter notre [guide pratique](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et réaliser un lancement réussi.

En ajoutant les forfaits d'appels (une fonction Office 365 avec Skype Entreprise), vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques de ou vers des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).

![Appel dans Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prérequis à l'activation de l'onglet **Appels** dans Teams
Pour activer l’onglet **appels** dans les équipes, les utilisateurs doivent disposer de 1:1 appel activé dans les équipes et à l’aide d’un client équipes qui prend en charge les équipes de 1:1 appel. Pour savoir comment gérer l’appel de 1:1 dans les équipes, consultez [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Pour savoir quels clients prennent en charge l’appel, lisez [les spécifications pour les équipes Microsoft et limites](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Actuellement, la messagerie vocale ne sera pas disponible dans l’onglet appels, sauf si l’utilisateur est activé pour les appels PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Conditions requises pour l’activation du **Pavé de numérotation** dans les équipes
Pour activer l’onglet **Pavé de numérotation** dans les équipes et autoriser les utilisateurs à émettre et recevoir des appels PSTN, vous devrez mettre en service des utilisateurs pour le système téléphonique et Plans de l’appel. Pour savoir comment configurer des Plans de l’appel, lisez [configurer des Plans de l’appel](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Vous pouvez également utiliser le routage Direct pour autoriser les utilisateurs à ext et de recevoir des appels PSTN. Pour savoir comment configurer le routage Direct, consultez [Configurer le routage Direct](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).

## <a name="teams-interop-policy-configuration"></a>Configuration de la stratégie d'interopérabilité de Teams
Pour activer les équipes commencer à recevoir des appels, vous devez mettre à jour la stratégie de mise à niveau d’équipes et équipes interopérabilité la stratégie, à l’aide des [équipes Microsoft & Skype entreprise centre d’administration](https://aka.ms/teamsadmincenter) ou une session Windows PowerShell à distance avec le Skype pour les entreprises [ `*-CsTeamsUpgradePolicy`et `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) applets de commande pour rediriger les appels vers les équipes.

Pour plus d’informations sur la stratégie de mise à niveau équipes et équipes PIA, voir [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Pour rechercher les applets de commande PowerShell que vous avez besoin, tapez « CsTeamsUpgradePolicy » ou « CsTeamsInteropPolicy » dans la zone **filtre** dans la [Skype pour la documentation d’applet de commande PowerShell Business](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Par défaut des équipes de stratégies de mise à niveau et interopérabilités
Teams intègre une configuration de stratégie par défaut conçue pour garantir l'ininterruption des flux de travail professionnels existants pendant le déploiement de Teams. Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams. Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue à la mise en place et au déploiement de Teams.

Mise à niveau de stratégie par défaut est conservée au mode hérité qui respecte la stratégie d’interopérabilité de base équipes pour déterminer où des conversations et les appels sont routés--les équipes des équipes ou Skype pour les entreprises.

> [!NOTE]
> Stratégie de mise à niveau les comportements d’équipes et stratégie interopérabilité équipes change bientôt comme décrit dans la [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

La stratégie d'interopérabilité de Teams possède la configuration par défaut suivante :

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Comportements de la configuration par défaut :
* **Pour les clients de Skype Entreprise existants**, cette stratégie vise à garantir que les appels Skype Entreprise sont dirigés vers Skype Entreprise et les appels Teams vers Teams. Les appels PSTN et fédérés seront dirigés vers Skype Entreprise une fois cette stratégie en place.
* **Pour les clients sans Skype Entreprise**, une fois la stratégie en place, outre les appels entre utilisateurs de Teams, seuls les appels PSTN sortants seront disponibles dans Teams. Vous devrez modifier la stratégie d'interopérabilité de Teams attribuée à vos utilisateurs pour recevoir des appels PSTN dans Teams.

> [!NOTE]
> Les utilisateurs ayant reçu une licence de système téléphonique et de forfait d'appels pour Skype Entreprise Online et utilisant la stratégie d'interopérabilité générale par défaut de Teams auront accès à l'onglet Appels dans Teams et pourront passer des appels RTC sortants à partir de Teams sans intervention des administrateurs.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configuration de Teams pour recevoir des appels PSTN entrants
Pour recevoir des appels entrants de PSTN dans les équipes, vous devez configurer des équipes par défaut appelant en appliquant une stratégie de mise à niveau équipes avec la stratégie d’interopérabilité de base équipes correspondante qui définit l’application `CallingDefaultClient` paramètre aux équipes.

> [!IMPORTANT]
> Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.

Si vous choisissez de continuer à utiliser la stratégie de mise à niveau équipes héritée, permet de la stratégie d’interopérabilité de base équipes préconfigurée suivante pour acheminer des appels PSTN entrants aux équipes :

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Si vous choisissez d’utiliser la stratégie de mise à niveau équipes mis à jour, vous devez affecter le mode TeamsOnly à vos utilisateurs.

Comportements de la stratégie ci-dessus :
* **Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams. Elle comprend les appels de type Voix sur IP (de Teams et Skype Entreprise) et les appels PSTN. 
* **Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams.

> [!WARNING]
> Basculer de `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise. Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie. Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Comment configurer les utilisateurs pour la réception de PSTN des appels dans les équipes
Lorsque vous utilisez la stratégie de mise à niveau équipes héritée, appliquer la stratégie de PIA équipes comme indiqué ci-dessus par le biais de Skype pour la session Windows PowerShell à distance Business pour rediriger les appels vers les équipes :

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Si vous choisissez d’utiliser le mode TeamsOnly, vous pouvez modifier le mode de coexistence de l’utilisateur à TeamsOnly via Microsoft Teams & Skype entreprise centre d’administration ou Skype pour la session Windows PowerShell à distance Business pour rediriger les appels vers les équipes :

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de migration et d’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Référence de l'applet de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype)

[Référence de l'applet de commande PowerShell de Teams](https://docs.microsoft.com/powershell/module/teams)
