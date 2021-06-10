---
title: Mises à niveau assistées | Skype Mise à niveau vers une version Teams Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Vue d’ensemble des mises à niveau assistées Skype Entreprise Online vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c19a0569fe56e9bf8c822b1418ac2fe0685532b
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855933"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams

Microsoft propose des mises à niveau assistées vers Teams pour aider les organisations à effectuer une transition réussie à partir de Skype Entreprise Online à la mise à niveau du service à compter du 31 juillet 2021. Que votre organisation effectuera la mise à niveau à partir d’un environnement *Skype Entreprise Online* ou *Skype Entreprise Online* avec un environnement hybride (utilisateurs à la fois dans Skype Entreprise **Online** et Skype Entreprise Server), les mises à niveau assistées réduisent le nombre de tâches techniques que vous devez effectuer et permettent de vous concentrer davantage sur la préparation de l’organisation, les connaissances des utilisateurs et la formation Teams.

Nous vous recommandons de consulter nos conseils [de mise à niveau](https://aka.ms/SkypeToTeams) avant de le mettre à niveau. Nos recommandations de mise à niveau incluent des activités recommandées et des ressources utiles pour effectuer une mise à niveau d’Skype Entreprise Online vers Teams. Ces conseils s’appliquent à toute organisation qui planifie une mise à niveau vers Teams, qu’elle gère tous les aspects de la mise à niveau ou utilise le processus assisté.

> [!NOTE]
> Si vous êtes programmé pour une mise à niveau assistée vers Teams, vous pouvez effectuer votre propre mise à niveau à partir d’Skype Entreprise Online avant la date de mise à niveau prévue. Pour plus d’informations sur la mise à niveau manuelle vers Teams, consultez nos [instructions de mise à niveau.](https://aka.ms/SkypeToTeams)
>
> Les mises à niveau assistées ne sont pas disponibles pour les déploiements locaux d’Skype Entreprise Server.

## <a name="notifications-for-scheduled-customers"></a>Notifications pour les clients programmés

Skype Entreprise Les clients en ligne qui sont programmés pour des mises à niveau assistées vers Teams recevront une série de notifications de mise à niveau. Ces notifications commenceront 90 jours avant la date de mise à niveau prévue. Ces notifications seront remises en tant que *plan* pour la modification des publications dans le Centre de messages Microsoft 365, les notifications de mise à niveau de tableau de bord dans le Centre d’administration Teams et les indicateurs dans l’application pour les utilisateurs finaux.

Les notifications de mise à niveau incluront la date prévue de la mise à niveau assistée, et incluront des liens vers des ressources et des formations de mise à niveau pour contribuer à l’adoption et à l’utilisation des Teams.

## <a name="the-assisted-upgrade-experience"></a>L’expérience de mise à niveau assistée

Les mises à niveau assistées commenceront en août 2021 avec des dates spécifiques du client partagées dans les notifications de planification mentionnées ci-dessus.

Votre expérience de mise à niveau assistée diffère légèrement selon que vous avez un environnement Skype Entreprise Online-only ou Skype Entreprise Online avec un environnement hybride :

- **Skype Entreprise Online-only** Le processus de mise à niveau assisté applique la `TeamsUpgradeOverridePolicy` stratégie à votre organisation. Lorsque cette stratégie est appliquée, tous vos utilisateurs Skype Entreprise Online sont placés en mode Teams uniquement.
- **Skype Entreprise Online avec un système hybride** Les environnements hybrides peuvent avoir des utilisateurs qui se classent dans l’une des catégories suivantes :

  - Utilisateurs locaux homed on Skype Entreprise Server
  - Skype Entreprise Utilisateurs en ligne en Teams mode uniquement
  - Skype Entreprise Utilisateurs en ligne **qui ne sont pas** en Teams mode Uniquement

  Si vous avez un mélange d’utilisateurs dans chacune des catégories répertoriées ci-dessus, le processus de mise à niveau assistée basculera uniquement les utilisateurs de Skype Entreprise Online en mode Teams Uniquement s’ils ne sont pas encore dans ce mode. Les utilisateurs Skype Entreprise l’environnement local ne seront pas impactés par le processus de mise à niveau assistée.

> [!NOTE]
> Ne vous inquiétez pas si votre mise à niveau assistée est prévue pour une date ultérieure au 31 juillet 2021. Votre organisation pourra utiliser Skype Entreprise Online jusqu’à la fin de la mise à niveau.

La durée de la mise à niveau variera en fonction du volume des utilisateurs et des caractéristiques du déploiement. Dans la plupart des cas, les utilisateurs au sein d’un client seront mis à niveau dans les 24 heures après le début de la mise à niveau. Pendant ce temps, les utilisateurs finaux auront toujours accès à Skype Entreprise Online. Une fois la mise à niveau terminée et que les utilisateurs se seront Skype Entreprise Online, ils commenceront à utiliser Teams pour la messagerie, les réunions et les appels.

## <a name="the-post-upgrade-experience"></a>L’expérience après la mise à niveau

Une fois la mise à niveau assistée terminée, le **mode coexistence** des utilisateurs mis à niveau est Teams uniquement. Nous vous recommandons de passer en [revue Teams considérations en mode uniquement](teams-only-mode-considerations.md) avant votre mise à niveau. Le tableau ci-dessous donne une vue d’ensemble de l’expérience utilisateur Teams utilisateur uniquement.

:::row:::
    :::column span="1":::
        **Conversation et appel**
    :::column-end:::
    :::column span="3":::
        - Tous les appels et conversations sont démarrés et reçus dans Teams
        - Les utilisateurs peuvent communiquer (conversation/appel) avec n’importe quel Skype Entreprise utilisateur
        - Les organisations peuvent permettre aux Teams de communiquer avec les utilisateurs du service grand public Skype en gérant les [autorisations d’accès externe](manage-external-access.md)
        - Teams utilisateurs qui tentent de se Skype Entreprise online sont redirigés vers le Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Réunions**
    :::column-end:::
    :::column span="3":::
        - Les utilisateurs programment toutes les nouvelles réunions dans Teams (plug-in remplacé)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Données migrées**
    :::column-end:::
    :::column span="3":::
        - Contacts existants provenant de Skype Entreprise Online, y compris fédérés (mais aucune liste de distribution)
        - Les contacts sont migrés lorsque les utilisateurs se Teams connexion pour la première fois.
            > [!IMPORTANT]
            >Les contacts doivent être migrés dans les 90 jours suivant la fin de votre mise à niveau.
        - Les réunions Skype Entreprise Online existantes sont converties en réunions Teams réunion
            > [!IMPORTANT]
            > Les clients Skype Entreprise configurations en ligne doivent utiliser Meeting Migration Service (MMS) pour migrer des réunions Skype Entreprise Online vers Teams réunions. Nous vous recommandons d’utiliser MMS avant la date de mise à niveau assistée. Pour plus d’informations sur MMS, voir [Utiliser Meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Si vous avez un déploiement Skype Entreprise Server hybride et une mise à niveau vers Teams, vous pouvez déplacer les utilisateurs entre Skype Entreprise Server et Teams une fois la mise à niveau terminée.

## <a name="related-content"></a>Contenu associé

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Déclassement de Skype Entreprise Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md)
