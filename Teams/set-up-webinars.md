---
title: Configurer des webinaires
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Découvrez comment gérer les stratégies d’inscription aux webinaires et aux réunions dans Teams.
ms.openlocfilehash: 097f4c385261ba1aea96990751d208b99d4d8b93
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950431"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Configurer des webinaires dans Microsoft Teams

> [!NOTE]
> Cet article décrit certaines fonctionnalités des webinaires qui sont en préversion et nécessitent une licence Teams Premium.

Microsoft propose désormais une nouvelle expérience de webinaire ; Cet article explique comment mettre à jour vos paramètres pour utiliser ces fonctionnalités.

Nous vous recommandons d’utiliser la nouvelle expérience de webinaire si vous envisagez d’utiliser des webinaires.

L’inscription aux réunions inclut des fonctionnalités de webinaire de base, la possibilité d’exiger l’inscription aux réunions et un rapport de présence. En activant la nouvelle expérience de webinaire, vous avez la possibilité d’utiliser l’inscription aux réunions et de nombreuses nouvelles fonctionnalités de webinaire, telles que :

- Événement dédié et page d’inscription pour votre webinaire
- Co-organisateurs
- Bios du présentateur sur la page de l’événement
- Vue d’ensemble et gestion de l’état de l’inscription

Pour en savoir plus sur les nouvelles fonctionnalités disponibles pour vos utilisateurs finaux, consultez Les [webinaires Bien démarrer avec Teams](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3).

Si l’inscription aux réunions de votre organisation est activée, tous les webinaires nouvellement créés bénéficieront de la nouvelle expérience. Les webinaires précédemment planifiés utilisent l’expérience de webinaire précédente. La nouvelle expérience utilise TeamsEventsPolicy. Si vous avez désactivé les webinaires, ils restent désactivés à mesure que la nouvelle expérience est déployée.

Actuellement, l’expérience de webinaire de base est contrôlée par l’inscription aux réunions à l’aide de la stratégie de réunion Teams (Set-CsTeamsMeetingPolicy). À l’avenir, le paramètre d’inscription à la réunion ne contrôlera pas les webinaires; Les webinaires passent au contrôle de la stratégie d’événements Teams (Set-CsTeamsEventsPolicy).

La nouvelle expérience de webinaire est configurée dans PowerShell. Consultez des exemples sur [la configuration de la nouvelle expérience de webinaire](#set-up-new-webinar-experience).

Pour plus d’informations sur les différences entre les réunions, les webinaires et les événements en direct, consultez [Réunions, webinaires et événements en direct](quick-start-meetings-live-events.md).

> [!NOTE]
> Pour les utilisateurs locaux, la nouvelle expérience de webinaire n’est pas encore disponible.
>
> La nouvelle expérience de webinaire n’est pas disponible pour Microsoft 365 GCC, Microsoft 365 GCC High ou Microsoft 365 DoD. L’expérience de webinaire existante n’est pas disponible pour Microsoft 365 GCC High ou Microsoft 365 DoD.

> [!IMPORTANT]
> Pour permettre aux utilisateurs de configurer des webinaires, Listes Microsoft doivent être configurés dans SharePoint en activant la création de listes personnelles à des fins d’eDiscovery. Pour plus d’informations, consultez [Paramètres de contrôle pour Listes Microsoft](/sharepoint/control-lists).

## <a name="set-up-new-webinar-experience"></a>Configurer une nouvelle expérience de webinaire

Vous devez utiliser PowerShell pour configurer la nouvelle expérience de webinaire pour votre organisation. La possibilité de configurer la nouvelle expérience de webinaire dans le Centre d’administration Teams n’est pas encore disponible.

L’inscription à la réunion doit être activée pour utiliser la nouvelle expérience de webinaire.

### <a name="configure-the-new-webinar-experience-with-powershell"></a>Configurer la nouvelle expérience de webinaire avec PowerShell

Pour configurer la nouvelle expérience de webinaire, utilisez les attributs suivants dans l’applet de commande **Windows PowerShell Set-CsTeamsEventsPolicy**.

|Paramètre|Paramètre par défaut|Description|
|---------|-----------|---------------|
|AllowWebinars|Activé|Ce paramètre détermine si un utilisateur peut créer des webinaires.|
|EventAccessType|Tout le monde|Ce paramètre détermine quels utilisateurs peuvent accéder à la page d’inscription d’événement ou au site d’événements à inscrire, ainsi que le type d’utilisateur autorisé à rejoindre la ou les sessions de l’événement.|

Avant de pouvoir exécuter ces applets de commande, vous devez être connecté à Microsoft Teams PowerShell. Pour plus d’informations, consultez [Gérer Teams avec Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

1. Activez l’inscription aux réunions.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. Activez la nouvelle expérience de webinaire.

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. Configurez les personnes autorisées à s’inscrire aux webinaires et aux réunions.

    - **Autoriser **_uniquement_* _ les utilisateurs de votre organisation à s’inscrire aux webinaires et aux meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **Autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire aux webinaires et aux réunions**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> Si **les utilisateurs anonymes peuvent participer à une réunion** sont désactivés dans **les paramètres de réunion**, les utilisateurs anonymes ne peuvent pas participer à des webinaires. Pour en savoir plus et activer ce paramètre, consultez [Paramètres de réunion dans Teams](meeting-settings-in-teams.md).

## <a name="configure-meeting-registration"></a>Configurer l’inscription à une réunion

Si vous souhaitez utiliser des webinaires, l’inscription aux réunions doit être activée.

Vous pouvez utiliser le Centre d’administration Teams sous **Stratégies de réunion de réunions** >  pour configurer l’inscription aux réunions et les webinaires.

### <a name="meeting-registration"></a>Inscription à une réunion

Si vous activez **l’inscription aux réunions**, les utilisateurs de votre organisation peuvent planifier des webinaires et des réunions nécessitant une inscription. Par défaut, ce paramètre est activé. Si vous souhaitez désactiver l’inscription aux réunions et les webinaires, définissez cette stratégie sur **Désactivé**.

**La planification des réunions privées** doit être activée pour que l’inscription à la réunion fonctionne. En savoir plus sur [la planification de réunions privées](meeting-policies-in-teams-general.md).

Pour les étudiants des locataires éducation, cette stratégie est désactivée par défaut. Pour plus d’informations sur l’activation de la planification de réunions privées pour les étudiants, consultez [Teams pour l'éducation stratégies et packages de stratégie](policy-packages-edu.md).

#### <a name="who-can-register"></a>Qui peut s’inscrire

> [!NOTE]
> Cette stratégie ne s’applique pas à la nouvelle expérience de webinaire. Pour configurer les personnes autorisées à s’inscrire à la nouvelle expérience de webinaire, utilisez `Set-CsTeamsEventsPolicy -EventAccessType`, comme indiqué dans [Configurer la nouvelle expérience de webinaire avec PowerShell](#configure-the-new-webinar-experience-with-powershell).

Cette stratégie contrôle les utilisateurs qui peuvent s’inscrire et participer à des webinaires avec inscription à une réunion uniquement. Cette stratégie comporte deux options, qui ne sont disponibles que si **l’inscription à la réunion** est activée. Par défaut, **Qui peut s’inscrire** est défini sur **Tout le monde**.

Si vous sélectionnez **Tout le monde**, tous les utilisateurs, y compris les utilisateurs anonymes, peuvent s’inscrire aux webinaires et y participer. Si vous sélectionnez **Tout le monde dans l’organisation**, seuls les utilisateurs de votre organisation peuvent s’inscrire aux webinaires et y participer. Si l’inscription à une réunion est désactivée, le paramètre **Qui peut s’inscrire** n’est pas disponible et personne ne peut s’inscrire aux webinaires.

La valeur par défaut pour **Qui peut s’inscrire** est **Tout le monde dans l’organisation** dans les locataires éducation. Pour plus d’informations, consultez [Teams pour l'éducation Assistant Stratégie](easy-policy-setup-edu.md).

## <a name="collect-webinar-and-meeting-registration-attendance"></a>Collecter la participation au webinaire et à l’inscription aux réunions

Vous pouvez utiliser le Centre d’administration Teams sous **Stratégies de réunion de réunions** >  pour activer le **rapport d’engagement**.

Lorsque ce paramètre est activé, les organisateurs peuvent voir les rapports de qui s’est inscrit et a participé aux webinaires ou aux réunions qu’ils ont configurés. Cette stratégie est activée par défaut. Pour plus d’informations, consultez [Stratégies de réunion dans Teams - Rapport d’engagement](meeting-policies-in-teams-general.md#engagement-report). Pour plus d’informations sur l’expérience de l’utilisateur final, consultez [Afficher et télécharger les rapports de présence aux réunions](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

Dans PowerShell, le paramètre **AllowEngagementReport** peut être utilisé pour activer cette option. Cette stratégie est activée par défaut. Pour la désactiver, exécutez la commande suivante dans PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

Pour plus d’informations sur l’applet de commande [, consultez Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

## <a name="turn-off-webinars"></a>Désactiver les webinaires

Vous pouvez désactiver les webinaires à l’aide de PowerShell. Cela désactive la nouvelle expérience de webinaire, ainsi que les webinaires avec inscription à la réunion uniquement.

Utilisez le script PowerShell suivant pour désactiver les webinaires :

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>Rubriques connexes

- [Stratégies de réunion dans Teams - Général](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
