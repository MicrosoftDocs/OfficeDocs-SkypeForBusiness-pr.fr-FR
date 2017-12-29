---
title: "Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Guide de démarrage rapide pour la configuration des forfaits d'appels dans Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
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
Pour activer l'onglet **Appels** dans Teams et permettre à vos utilisateurs de passer et recevoir des appels PSTN, vous devez leur fournir un système téléphonique et un forfait d'appels. Pour en savoir plus à ce sujet, lisez [Configurer des forfaits d'appels](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).

> [!IMPORTANT]
> Avant de configurer des forfaits d'appels dans Teams, tenez compte des restrictions suivantes :
> * **La fonction Voix Hybride n'est pas prise en charge dans Teams** - Teams ne prend pas en charge la fonction Voix hybride pour le moment. Il n'est pas conseillé aux clients qui utilisent la Voix hybride de modifier les stratégies de réception des appels dans Teams, ceci pouvant engendrer des interruptions de service.
> * **Les appels fédérés ne sont pas pris en charge dans Teams** - Teams ne prend pas en charge les appels fédérés (appels entre clients/entreprises) pour le moment. Les appels fédérés seront toujours acheminés vers Skype Entreprise indépendamment de la configuration de l'appel jusqu'à la prise en charge de cette fonction dans Teams.

## <a name="teams-interop-policy-configuration"></a>Configuration de la stratégie d'interopérabilité de Teams
Pour activer la réception des appels dans Teams, vous devez mettre à jour la stratégie d'interopérabilité de Teams à l'aide d'une session Windows PowerShell distante avec les applets de commande [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Entreprise, afin de rediriger les appels vers Teams. Pour en savoir plus sur la fonction d'interopérabilité de Teams, consultez [Interopérabilité entre Microsoft Teams et Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

> [!TIP]
> Pour rechercher les applets de commande PowerShell dont vous avez besoin, entrez CsTeamsInteropPolicy dans le champ **Filtre** de la [documentation des applets de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-interop-policy"></a>Stratégie d'interopérabilité de Teams par défaut
Teams intègre une configuration de stratégie par défaut conçue pour garantir l'ininterruption des flux de travail professionnels existants pendant le déploiement de Teams. Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams. Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue à la mise en place et au déploiement de Teams.

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

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>Procédure de configuration de Teams pour utiliser la stratégie par défaut
Par défaut, la stratégie d'interopérabilité générale de Teams est appliquée à tous les utilisateurs de votre client et configurée avec les paramètres standard décrits ci-après. Si pour un motif quelconque vous avez octroyé des stratégies différentes à vos utilisateurs et souhaitez rétablir les paramètres par défaut, vous devrez appliquer la stratégie d'interopérabilité générale de Teams via la session Windows PowerShell distante de Skype Entreprise :

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Bien qu'il soit possible de modifier la stratégie d'interopérabilité générale de Teams à partir des valeurs par défaut, nous vous déconseillons fortement de le faire. 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configuration de Teams pour recevoir des appels PSTN entrants
Pour recevoir des appels RTC entrants dans Teams, vous devez configurer Teams en tant qu'application d'appel par défaut en appliquant la stratégie d'interopérabilité de Teams après avoir défini le paramètre `CallingDefaultClient` sur Teams.

> [!IMPORTANT]
> Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.

Considérez l'utilisation de la stratégie d'interopérabilité de Teams préconfigurée suivante pour acheminer les appels RTC entrants vers Teams :

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Comportements de la stratégie ci-dessus :
* **Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams. Elle comprend les appels de type Voix sur IP (de Teams et Skype Entreprise) et les appels PSTN. Les appels fédérés continueront d'être reçus dans Skype Entreprise. 
* **Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams. Teams **ne prend pas encore en charge** les appels fédérés.

> [!WARNING]
> Basculer de `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise. Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie. Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>Procédure de configuration de Teams pour recevoir des appels RTC
Appliquez la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise pour rediriger les appels vers Teams :

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>Configuration de Teams pour permettre aux utilisateurs de modifier leur application d'appel préférée
Pour laisser les utilisateurs choisir leur application d'appel préférée et de recevoir les appels dans Teams ou Skype Entreprise, vous devez créer une stratégie d'interopérabilité personnalisée de Teams dans laquelle le paramètre `AllowEndUserClientOverride` est activé.

Voici un exemple de stratégie d'interopérabilité de Teams permettant à l'utilisateur de choisir son application d'appel préférée :

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Une fois cette stratégie personnalisée appliquée aux utilisateurs, l'option de modification de l'application d'appel préférée sera disponible sur le client Teams permettant ainsi aux utilisateurs d'effectuer la modification eux-mêmes.

![Option d'application d'appel préférée](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> Il est recommandé d'appliquer cette configuration à un ensemble initial d'utilisateurs avant d'apporter des modifications à plus grande échelle ou dans toute votre organisation.

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Procédure de création et d'application d'une stratégie d'interopérabilité personnalisée de Teams
Pour créer la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise, procédez comme suit :

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>Voir aussi
[Configurer des forfaits d'appels](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Interopérabilité entre Microsoft Teams et Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Référence de l'applet de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams)
