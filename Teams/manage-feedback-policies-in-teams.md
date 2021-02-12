---
title: Gérer les stratégies de commentaires dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs de Teams dans votre organisation peuvent envoyer des commentaires sur Teams à Microsoft.
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804694"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gérer les stratégies de commentaires dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Les utilisateurs de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft pour nous faire part de nos interventions, directement à partir des clients de bureau et web Teams. Nous améliorons continuellement l’expérience Teams et nous utilisons ces commentaires pour améliorer Teams.

> [!NOTE]
> Les stratégies de commentaires ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD.

**La fonctionnalité Donner des commentaires**

Les utilisateurs peuvent nous envoyer des commentaires et des suggestions concernant Teams en nous aident  >  **à envoyer des commentaires** dans Teams. Les données  envoyées via l’envoi de commentaires sont considérées comme des « données de support » dans le cadre de votre contrat Microsoft 365 ou Office 365, y compris les informations qui seraient autrement considérées comme « Données client » ou « Données personnelles ».

![Capture d’écran de l’option Donner des commentaires dans Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Enquêtes**

Les utilisateurs peuvent également évaluer leur expérience avec Teams et nous envoyer des détails sur l’évaluation qu’ils donnent. Cette enquête pop-up est affichée aux utilisateurs de temps à temps dans Teams. Lorsqu’un utilisateur clique sur **Fournir des commentaires** dans la notification, l’enquête est affichée pour lui.

![Capture d’écran de la notification et du formulaire d’enquête dans Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Définir si les utilisateurs peuvent envoyer des commentaires sur Teams à Microsoft

En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft via l’envoi de commentaires et s’ils reçoivent l’enquête.  Par défaut, tous les utilisateurs de votre organisation se voit automatiquement  attribuer la stratégie globale (à l’échelle de l’organisation par défaut) et la fonctionnalité Donner des commentaires et l’enquête sont activées dans la stratégie. Teams pour l’éducation fait exception, où les fonctionnalités sont activées pour les enseignants et désactivées pour les étudiants.

Vous pouvez modifier la stratégie globale ou créer et affecter une stratégie personnalisée. Une fois que vous avez modifié la stratégie globale ou attribué une stratégie personnalisée, l’application des modifications peut prendre quelques heures.

Par exemple, vous voulez autoriser tous les utilisateurs  de votre organisation à envoyer des commentaires via l’envoi de commentaires et la réception d’enquêtes, à l’exception des nouvelles recrues en formation. Dans ce scénario, vous créez une stratégie personnalisée pour désactiver à la fois les fonctionnalités et l’affecter à de nouvelles recrues. Tous les autres utilisateurs de votre organisation obtiennent la stratégie globale avec les fonctionnalités désactivées.  

Vous gérez les stratégies de commentaires à l’aide de PowerShell. Utilisez l’cmdlet **New-CsTeamsFeedbackPolicy,** qui est possible *ici, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* pour créer une stratégie personnalisée et l’cmdlet **Grant-CsTeamsFeedbackPolicy** pour l’affecter à un ou plusieurs utilisateurs ou groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.

Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :

 - **Donnez des** commentaires : Définissez le  **paramètre userInitiatedMode** pour permettre aux utilisateurs affectés à la stratégie de faire part de leurs commentaires. La désactivation du paramètre **désactive** la fonctionnalité et les utilisateurs à qui la stratégie est attribuée n’ont pas la possibilité d’apporter des commentaires.
 - **Enquêtes**: définissez le **paramètre ReceiveSurveysMode** pour permettre aux utilisateurs affectés à la stratégie de recevoir l’enquête.  Pour que les utilisateurs reçoivent l’enquête et les autorisent à se désavertr, définissez le paramètre sur **enabledUserOverride.** Dans Teams, les utilisateurs peuvent ensuite se rendre dans **Paramètres** de confidentialité et choisir  >   s’ils souhaitent participer à des enquêtes. La désactivation du paramètre **désactive** la fonctionnalité et les utilisateurs à qui la stratégie est attribuée ne recevront pas l’enquête.

## <a name="create-a-custom-feedback-policy"></a>Créer une stratégie de commentaires personnalisée

Dans cet exemple, nous créons une stratégie de commentaires appelée Stratégie de commentaires sur les nouvelles recrues et nous cessons la possibilité de fournir des commentaires via l’envoi de **commentaires** et l’enquête.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Attribuer une stratégie de commentaires personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Dans cet exemple, nous affectons une stratégie personnalisée nommée Stratégie de commentaires sur les nouvelles recrues à un utilisateur nommé utilisateur1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Sujets associés

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](assign-policies.md)