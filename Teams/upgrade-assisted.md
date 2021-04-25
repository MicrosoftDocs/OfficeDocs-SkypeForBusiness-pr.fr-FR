---
title: Mises à niveau assistées | Mise à niveau de Skype Business Online vers Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Vue d'ensemble des mises à niveau assistées de Skype Entreprise Online vers Teams
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995195"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams

Microsoft propose des mises à niveau assistées vers Teams pour aider les organisations à effectuer une transition réussie à partir de Skype Entreprise Online à mesure que le service prend fin le 31 juillet 2021. Les mises à niveau assistées réduisent le nombre de tâches techniques que vous devez effectuer et permettent de vous concentrer davantage sur la préparation de l'organisation, la sensibilisation des utilisateurs et la formation teams.

Nous vous recommandons de consulter nos conseils [de mise à niveau](https://aka.ms/SkypeToTeams) avant de le mettre à niveau. Nos recommandations de mise à niveau incluent des activités recommandées et des ressources utiles pour effectuer une mise à niveau de Skype Entreprise Online vers Teams. Ces conseils s'appliquent à toute organisation qui planifie une mise à niveau vers Teams, qu'elle gère tous les aspects de la mise à niveau ou utilise le processus assisté.

> [!NOTE]
> Si vous êtes programmé pour une mise à niveau assistée vers Teams, vous pouvez effectuer votre propre mise à niveau à partir de Skype Entreprise Online avant la date de mise à niveau prévue. Pour plus d'informations sur la mise à niveau manuelle vers Teams, consultez nos [instructions de mise à niveau.](https://aka.ms/SkypeToTeams)
>
> La mise à niveau assistée n'est pas disponible pour les déploiements locaux de Skype Entreprise Server.

## <a name="notifications-for-scheduled-customers"></a>Notifications pour les clients programmés

Les clients Skype Entreprise Online qui doivent recevoir des mises à niveau assistées vers Teams recevront une série de notifications de mise à niveau. Ces notifications commenceront 90 jours avant la date de mise à niveau prévue. Ces notifications seront remises en tant que *plan* pour la modification des publications dans le Centre de messages Microsoft 365, les notifications de mise à niveau des tableaux de bord dans le Centre d'administration Teams et les indicateurs dans l'application aux utilisateurs finaux.

Les notifications de mise à niveau incluront la date prévue de la mise à niveau assistée et incluront des liens vers des ressources et des formations de mise à niveau pour contribuer à l'adoption et à l'utilisation de Teams.

## <a name="the-assisted-upgrade-experience"></a>L'expérience de mise à niveau assistée

Les mises à niveau assistées commenceront en août 2021 avec des dates spécifiques du client partagées dans les notifications de planification mentionnées ci-dessus.

La durée de la mise à niveau variera en fonction du volume des utilisateurs et des caractéristiques du déploiement. Toutefois, dans la plupart des cas, les utilisateurs au sein d'un client seront mis à niveau dans les 24 heures après le début de la mise à niveau. Pendant ce temps, les utilisateurs finaux auront toujours accès aux fonctionnalités de Skype Entreprise Online. Une fois la mise à niveau terminée et que les utilisateurs se connectent à Skype Entreprise Online, ils commencent à utiliser Teams pour la messagerie, les réunions et les appels.

## <a name="the-post-upgrade-experience"></a>L'expérience après la mise à niveau

Une fois la mise à niveau assistée terminée, le **mode coexistence** pour les utilisateurs mis à niveau est réglé sur Teams uniquement et Ne peut être modifié que par Microsoft dans un autre mode de coexistence. Nous vous recommandons de passer en revue [les considérations en mode Teams uniquement](teams-only-mode-considerations.md) avant votre mise à niveau. Le tableau ci-dessous fournit une vue d'ensemble de l'expérience utilisateur de Teams uniquement.

:::row:::
    :::column span="1":::
        **Conversation et appel**
    :::column-end:::
    :::column span="3":::
        - Tous les appels et conversations sont démarrés et reçus dans Teams
        - Les utilisateurs peuvent communiquer (conversation/appel) avec n'importe quel utilisateur de Skype Entreprise
        - Les organisations peuvent permettre aux utilisateurs de Teams de communiquer avec les utilisateurs du service grand public Skype en gérant les [autorisations d'accès externe](manage-external-access.md)
        - Les utilisateurs de Teams qui tentent de se connecter à Skype Entreprise Online seront redirigés vers Teams
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
        - Contacts existants de Skype Entreprise Online incluant des contacts fédérés (mais aucune liste de distribution)
        - Les réunions Skype Entreprise Online existantes sont converties en réunions Teams
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>Contenu associé

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Déclassement de Skype Entreprise Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md)
