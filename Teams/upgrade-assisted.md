---
title: Mises à niveau assistées | Skype Mise à niveau vers Teams Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Vue d’ensemble des mises à niveau assistées Skype Entreprise Online vers Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456887"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams

Microsoft a Skype Entreprise Online le 31 juillet 2021.  Microsoft fournit un processus de mise à niveau assisté pour aider les organisations à déplacer les utilisateurs Skype Entreprise Online vers Teams uniquement.  Les mises à niveau assistées par Microsoft réduisent le nombre de tâches techniques et simplifient la transition vers un monde sans Skype Entreprise Online, que votre organisation soit :
 - Une organisation en ligne pure qui doit passer *d’Skype Entreprise Online* à la version Teams uniquement, ou
 - Organisation hybride avec des utilisateurs à la fois dans *Skype Entreprise Online*  et un environnement *Skype Entreprise Server* local, qui doit mettre à niveau uniquement son utilisateur Skype Entreprise *Online* vers Teams seul.

Nous vous recommandons de consulter nos [conseils de mise à niveau](https://aka.ms/SkypeToTeams) avant de le mettre à niveau. Nos recommandations de mise à niveau incluent des activités recommandées et des ressources utiles pour effectuer une mise à niveau de Skype Entreprise Online vers Teams. Ces conseils s’appliquent à toute organisation qui planifie une mise à niveau vers Teams, qu’elle gère tous les aspects de la mise à niveau ou utilise le processus assisté.

## <a name="the-assisted-upgrade-experience"></a>L’expérience de mise à niveau assistée
Skype Entreprise Les clients en ligne qui sont programmés pour des mises à niveau assistées vers Teams recevront différentes formes de notifications : Planifier la  modification des publications dans le Centre de messages Microsoft 365, notifications de mise à niveau du tableau de bord dans le Centre d’administration Teams et indicateurs dans l’application pour les utilisateurs finaux. La notification de mise à niveau dans le Centre de messages et le Centre d’administration Teams inclut la date de la mise à niveau assistée, ainsi qu’un lien vers les ressources de mise à niveau et la formation nécessaires pour contribuer à l’adoption et à l’utilisation d’Teams.

L’expérience de mise à niveau assistée diffère légèrement selon que votre organisation compte des utilisateurs dans un environnement Skype Entreprise Server local :
- **Organisations en ligne pures :** Pour les *organisations qui* n’ont pas d’Skype locale pour les utilisateurs de Busineess Server, `TeamsUpgradeOverridePolicy` le processus de mise à niveau assisté applique la stratégie à votre organisation. Lorsque cette stratégie est appliquée, tous les utilisateurs de Skype Entreprise Online sont placés en mode TeamsOnly.
- **Organisations hybrides avec des utilisateurs** Skype Entreprise locaux : cela inclut les organisations qui incluent tous les utilisateurs Skype Entreprise Server, qu’ils soient hybrides ou non. Ces organisations peuvent avoir des utilisateurs qui se classent dans l’une des catégories suivantes :

  - Utilisateurs locaux homed on Skype Entreprise Server (qui peuvent ou non utiliser Teams, mais ne sont pas les seuls Teams utilisateurs)
  - Utilisateurs de TeamsOnly qui ont domicile dans Skype Entreprise Online
  - Utilisateurs non-TeamsOnly homed in Skype Entreprise Online

Le processus de mise à niveau assisté n’aura d’impact que sur la dernière catégorie d’utilisateurs : les utilisateurs non Teams Seuls les utilisateurs homed in Skype Entreprise Online sont mis à niveau en mode Teams uniquement. Les utilisateurs Skype Entreprise sur site et les utilisateurs existants de TeamsOnly ne seront pas impactés par le processus de mise à niveau assistée.

> [!NOTE]
> Votre organisation peut continuer à utiliser Skype Entreprise Online jusqu’à la fin de la mise à niveau. Si vous êtes programmé pour une mise à niveau assistée vers Teams, vous pouvez effectuer votre propre mise à niveau à partir d’Skype Entreprise Online avant la date de mise à niveau prévue. Pour plus d’informations sur la mise à niveau manuelle vers Teams, consultez nos [instructions de mise à niveau](https://aka.ms/SkypeToTeams).

La durée de la mise à niveau varie en fonction du volume des utilisateurs et des caractéristiques du déploiement. Dans la plupart des cas, les utilisateurs au sein d’un client seront mis à niveau dans les 24 heures après le début de la mise à niveau. Pendant ce temps, les utilisateurs finaux auront toujours accès aux Skype Entreprise Online. Une fois la mise à niveau terminée et que les utilisateurs se seront Skype Entreprise Online, ils commenceront à utiliser Teams pour la messagerie, les réunions et les appels.

## <a name="the-post-upgrade-experience"></a>L’expérience après la mise à niveau

Une fois la mise à niveau assistée terminée, le **mode coexistence** pour les utilisateurs mis à niveau est Teams uniquement. Nous vous recommandons de passer en [revue Teams considérations en mode uniquement](teams-only-mode-considerations.md) avant votre mise à niveau. Le tableau ci-dessous donne une vue d’ensemble de l’expérience utilisateur Teams utilisateur uniquement.

:::row:::
    :::column span="1":::
        **Conversation et appels**
    :::column-end:::
    :::column span="3":::
        - Tous les appels et conversations sont démarrés et reçus dans Teams
        - Les utilisateurs peuvent communiquer (conversation/appel) avec n’importe quel Skype Entreprise utilisateur
        - Les organisations peuvent permettre aux Teams utilisateurs de communiquer avec les utilisateurs du service grand public Skype en gérant les [autorisations d’accès externe](manage-external-access.md)
        - Teams utilisateurs qui tentent de se Skype Entreprise online sont redirigés vers Teams
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
            > Les clients courir à des configurations Skype Entreprise Online doivent utiliser Meeting Migration Service (MMS) pour migrer des réunions Skype Entreprise Online vers Teams réunion. Nous vous recommandons d’utiliser MMS avant la date de mise à niveau assistée. Pour plus d’informations sur MMS, voir [Utiliser Meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Si vous avez un déploiement Skype Entreprise Server hybride et que vous devez effectuer une mise à niveau vers Teams, vous pouvez déplacer les utilisateurs entre Skype Entreprise Server et Teams une fois la mise à niveau terminée.

## <a name="related-content"></a>Contenu associé

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Déclassement de Skype Entreprise Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md)
