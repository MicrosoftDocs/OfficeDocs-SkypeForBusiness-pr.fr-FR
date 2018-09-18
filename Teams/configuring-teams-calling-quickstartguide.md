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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882097"
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
Pour activer l'onglet **Appels** dans Teams et permettre à vos utilisateurs de passer et recevoir des appels PSTN, vous devez leur fournir un système téléphonique et un forfait d'appels. Pour savoir comment les configurer, reportez-vous à la section [Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).

## <a name="teams-interop-policy-configuration"></a>Configuration de la stratégie d'interopérabilité de Teams
Pour permettre à Teams de commencer à recevoir des appels, vous devez mettre à jour la stratégie de mise à niveau de Teams et la stratégie d'interopérabilité de Teams à l’aide du [Centre d’administration de Microsoft Teams et Skype Entreprise](https://aka.ms/teamsadmincenter), ou d'une session Windows PowerShell avec les applets de commande de Skype Entreprise [`*-CsTeamsUpgradePolicy` et `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) afin de rediriger les appels vers Teams.

Pour plus d’informations sur la stratégie de mise à niveau de Teams et la stratégie d’interopérabilité de Teams, reportez-vous à la rubrique [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Pour rechercher les applets de commande PowerShell dont vous avez besoin, entrez « CsTeamsUpgradePolicy » ou « CsTeamsInteropPolicy » dans la zone **Filtre** de la [documentation des applets de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Stratégies de mise à niveau et d’interopérabilité de Teams par défaut
Teams intègre une configuration de stratégie par défaut conçue pour garantir que les flux de travail de l’entreprise existants ne soient pas interrompus pendant un déploiement de Teams. Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams. Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue lors de la phase pilote et du déploiement de Teams.

La stratégie de mise à niveau de Teams par défaut est laissée en mode hérité qui respectera la stratégie d’interopérabilité de Teams pour déterminer où les conversations et appels sont dirigés - Teams ou Skype Entreprise.

> [!NOTE]
> Les comportements de la stratégie de mise à niveau de Teams et de la stratégie d’interopérabilité de Teams seront modifiés prochainement. Reportez-vous à la rubrique [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

La stratégie d'interopérabilité de Teams a la configuration par défaut suivante :

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
Pour recevoir des appels PSTN entrants dans Teams, vous devez configurer Teams en tant qu'application d'appel par défaut en appliquant la stratégie de mise à niveau de Teams avec la stratégie d'interopérabilité de Teams correspondante qui définit le paramètre `CallingDefaultClient` sur Teams.

> [!IMPORTANT]
> Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.

Si vous choisissez de continuer à utiliser la stratégie de mise à niveau de Teams héritée, utilisez la stratégie d’interopérabilité de Teams préconfigurée suivante pour acheminer les appels PSTN entrants vers Teams :

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Si vous choisissez d’utiliser la stratégie de mise à niveau de Teams mise à jour, vous devez attribuer le mode TeamsOnly à vos utilisateurs :

Les comportements de la stratégie ci-dessus sont les suivants :
* **Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams. Elle inclut les appels Voix sur IP (depuis Teams et Skype Entreprise) et les appels PSTN. 
* **Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams.

> [!WARNING]
> Actuellement, si basculer `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise. Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie. Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Configuration des utilisateurs pour qu'ils reçoivent les appels PSTN dans Teams
Si vous utilisez la stratégie de mise à niveau de Teams héritée, appliquez la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise pour rediriger les appels vers Teams :

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Si vous choisissez d’utiliser le mode TeamsOnly, vous pouvez modifier le mode de coexistence des utilisateurs sur TeamsOnly via le Centre d’administration de Microsoft Teams et Skype Entreprise, ou via la session Windows PowerShell de Skype Entreprise pour rediriger les appels vers Teams :

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Référence de l'applet de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype)

[Référence de l'applet de commande PowerShell de Teams](https://docs.microsoft.com/powershell/module/teams)
