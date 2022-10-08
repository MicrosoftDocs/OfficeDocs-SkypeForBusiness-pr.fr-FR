---
title: Gérer les stratégies de commentaires dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: heprecel
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser des stratégies de commentaires pour contrôler si les utilisateurs Teams de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft.
ms.openlocfilehash: 9510a94a60a79a36292011fdcdad6afa97e6f56f
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494657"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gérer les stratégies de commentaires dans Microsoft Teams

Les utilisateurs de votre organisation peuvent envoyer des commentaires sur Microsoft Teams pour nous faire savoir comment nous procédons directement à partir du bureau Teams, des clients web et des appareils mobiles. Nous améliorons continuellement l’expérience Teams et nous utilisons ces commentaires pour améliorer Teams.

> [!NOTE]
> Les stratégies de commentaires ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD.

**Fonctionnalité **Envoyer des commentaires****

Les utilisateurs peuvent nous envoyer des commentaires et des suggestions sur Teams en allant à **Help** > **Give feedback** in Teams desktop and web.


![Option Envoyer des commentaires dans Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Accédez aux commentaires sur les appareils mobiles à l’aide **de l’aide paramètres** > **& commentaires** > **Envoyer des commentaires**.

![Option Envoyer des commentaires dans Teams sur mobile](media/feedback3.jpg)

 Les données envoyées via **Envoyer des commentaires** et **Envoyer des commentaires** sont considérées comme des « données de support » dans le cadre de votre contrat Microsoft 365 ou Office 365, y compris les informations qui seraient autrement considérées comme « Données client » ou « Données personnelles ».



**Enquêtes**

Les utilisateurs peuvent également évaluer leur expérience avec Teams et nous envoyer des détails sur l’évaluation qu’ils donnent. Cette enquête contextuelle s’affiche de temps à autre pour les utilisateurs dans Teams. Lorsqu’un utilisateur sélectionne **Fournir des commentaires** dans la notification, l’enquête s’affiche pour qu’il se termine.

![la notification et le formulaire d’enquête dans Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Définir si les utilisateurs peuvent envoyer des commentaires sur Teams à Microsoft

En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft et s’ils reçoivent l’enquête. Par défaut, la stratégie globale (par défaut à l’échelle de l’organisation) est automatiquement affectée à tous les utilisateurs de votre organisation, et la fonctionnalité de commentaires et l’enquête sont activées dans la stratégie. L’exception est Teams pour l'éducation, où les fonctionnalités sont activées pour les enseignants et désactivées pour les étudiants.

Vous pouvez modifier la stratégie globale ou créer et affecter une stratégie personnalisée. Après avoir modifié la stratégie globale ou affecté une stratégie personnalisée, quelques heures peuvent être nécessaires pour que les modifications prennent effet.

Par exemple, vous souhaitez autoriser tous les utilisateurs de votre organisation à envoyer des commentaires et à recevoir des enquêtes, à l’exception des nouveaux employés en formation. Dans ce scénario, vous créez une stratégie personnalisée pour désactiver les deux fonctionnalités et l’affecter à de nouveaux employés. Tous les autres utilisateurs de votre organisation obtiennent la stratégie globale avec les fonctionnalités activées.  

Vous gérez les stratégies de commentaires à l’aide de PowerShell. Utilisez l’applet [**de commande New-CsTeamsFeedbackPolicy**](/powershell/module/skype/new-csteamsfeedbackpolicy) pour créer une stratégie personnalisée. Utilisez l’applet de commande **Grant-CsTeamsFeedbackPolicy** pour l’affecter à un ou plusieurs utilisateurs ou groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution. Utilisez **Set-CsTeamsFeedbackPolicy** pour définir des indicateurs spécifiques.

Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :

 - **Envoyer des commentaires** : définissez le paramètre **userInitiatedMode** sur **activé** pour autoriser les utilisateurs auxquels la stratégie est affectée à donner des commentaires. Si vous définissez le paramètre sur **désactivé** , la fonctionnalité est désactivée et les utilisateurs auxquels la stratégie est affectée n’ont pas la possibilité de donner des commentaires.

 - **Enquêtes** : définissez le paramètre **receiveSurveysMode** sur **activé** pour autoriser les utilisateurs auxquels la stratégie est affectée à recevoir l’enquête. Pour que les utilisateurs reçoivent l’enquête et leur permettent de refuser, définissez le paramètre sur **enabledUserOverride**. Dans Teams, les utilisateurs peuvent ensuite accéder à **Paramètres** > **de confidentialité** et choisir s’ils souhaitent participer à des enquêtes. La définition du **paramètre désactivé** désactive la fonctionnalité et les utilisateurs auxquels la stratégie est affectée ne recevront pas l’enquête.

 - **Captures d’écran** : utilisez l’indicateur **AllowScreenshotCollection** pour ajouter l’option d’adhésion à la collection de captures d’écran pour les utilisateurs.
 - **Email** : Utilisez l’indicateur **AllowEmailCollection** pour ajouter un champ de messagerie.
 - **Collection de journaux** : utilisez l’indicateur **AllowLogCollection** pour ajouter l’option d’adhésion à la collecte des journaux pour les utilisateurs. La collecte des journaux est actuellement activée uniquement sur les appareils mobiles. Pour plus d’informations sur les données partagées via les journaux [d’activité, en savoir plus](https://go.microsoft.com/fwlink/?linkid=2168178).
 - **Suggérer une fonctionnalité** : définissez le paramètre **EnableFeatureSuggestions sur** True pour permettre aux utilisateurs auxquels la stratégie est affectée de suggérer une fonctionnalité. Si vous définissez le paramètre sur désactivé, la fonctionnalité est désactivée et les utilisateurs auxquels la stratégie est affectée n’ont pas la possibilité de donner des commentaires. Le paramètre par défaut est extrait de votre paramètre de stratégie d’expériences connectées facultatives Microsoft 365. Pour en savoir plus sur ce paramètre, consultez [Vue d’ensemble des expériences connectées facultatives dans Office](/deployoffice/privacy/optional-connected-experiences).

## <a name="create-a-custom-feedback-policy"></a>Créer une stratégie de commentaires personnalisée

Dans cet exemple, nous créons une stratégie de commentaires appelée Nouvelle stratégie de commentaires d’embauche et nous désactivons la possibilité de donner des commentaires par le biais **de Donner des commentaires** et de l’enquête.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Affecter une stratégie de commentaires personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Dans cet exemple, nous affectons une stratégie personnalisée nommée Nouvelle stratégie de commentaires d’embauche à un utilisateur nommé user1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Rubriques connexes

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
