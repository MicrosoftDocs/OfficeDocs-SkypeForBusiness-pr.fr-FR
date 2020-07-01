---
title: Gérer les stratégies de commentaires dans Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs teams de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.
ms.openlocfilehash: b489e574a1d1c2a2b1ac5faf69626e997dbbfaa9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938483"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gérer les stratégies de commentaires dans Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft pour nous faire savoir ce que nous faisons, directement à partir du bureau et des clients Web Teams. Nous cherchons constamment à améliorer l’expérience d’équipe et nous utilisons ces commentaires pour améliorer les équipes.

**Fonctionnalité envoyer des commentaires**

Les utilisateurs peuvent **vous**envoyer des commentaires et des suggestions aux équipes pour nous en accédant aux  >  **Commentaires** dans Teams. Les données envoyées par le biais de **Commentaires** sont considérées comme des « données de support » dans votre contrat Microsoft 365 ou Office 365, y compris des informations qui seraient considérées comme « données client » ou « données personnelles ».

![Capture d’écran de l’option envoyer des commentaires dans Microsoft teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Recherches**

Les utilisateurs peuvent également évaluer leur connaissance de Team et nous envoyer des informations sur leur évaluation. Cette enquête contextuelle s’affiche lorsque les utilisateurs sont en phase d’exécution dans Teams. Lorsqu’un utilisateur clique sur **Envoyer un commentaire** dans la notification, l’enquête s’affiche pour qu’il soit terminé.

![Capture d’écran de la notification de l’enquête et du formulaire dans teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Définir si les utilisateurs peuvent envoyer des commentaires sur teams à Microsoft

En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft par le biais de **Commentaires** et s’ils reçoivent l’enquête. Par défaut, tous les utilisateurs de votre organisation disposent automatiquement de la stratégie globale (par défaut de l’organisation par défaut), et la fonctionnalité d' **attribution de commentaires** est activée dans la stratégie. L’exception est teams pour l’éducation, qui est activée pour les enseignants et désactivée pour les étudiants.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Après avoir modifié la stratégie globale ou affecté une stratégie personnalisée, il est possible que les modifications soient prises en compte.

Par exemple, supposons que vous souhaitiez permettre à tous les utilisateurs de votre organisation d’envoyer des commentaires par le biais de **Commentaires** et de recevoir des enquêtes à l’exception des nouvelles recrues dans la formation. Dans ce scénario, vous créez une stratégie personnalisée pour désactiver les deux fonctions et les attribuer aux nouvelles recrues. Tous les autres utilisateurs de votre organisation obtiennent la politique globale avec les fonctionnalités activées.  

Vous pouvez gérer les stratégies de commentaires à l’aide de PowerShell. Utilisez l’applet **de nouvelle applet de nouveau-CsTeamsFeedbackPolicy** , *qui se [trouve ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, pour créer une stratégie personnalisée et l’applet de passe **Grant-CsTeamsFeedbackPolicy** pour l’attribuer à un ou plusieurs utilisateurs ou groupes d’utilisateurs, comme un groupe de sécurité ou un groupe de distribution.

Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :

 - **Envoyer des commentaires**: définissez le paramètre **userInitiatedMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée pour formuler des commentaires. Le fait de définir le paramètre sur **Disabled** désactive la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne peuvent pas envoyer de commentaires.
 - **Enquêtes**: définissez le paramètre **receiveSurveysMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée à la réception de l’enquête. Pour que les utilisateurs reçoivent l’enquête et leur permettent de les refuser, définissez le paramètre sur **enabledUserOverride**. Dans Microsoft Teams, les utilisateurs peuvent accéder aux **paramètres**  >  de**confidentialité** et décider s’ils souhaitent participer aux enquêtes. La définition du paramètre sur **Disabled** entraîne la désactivation de la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne recevront pas l’enquête.

## <a name="create-a-custom-feedback-policy"></a>Créer une stratégie de commentaires personnalisée

Dans cet exemple, nous créons une stratégie de commentaires appelée nouvelle politique de commentaires sur les employés et nous désactivons la possibilité de faire part **de vos commentaires et de** l’enquête.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Assigner une stratégie de commentaires personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Dans cet exemple, nous affectons une stratégie personnalisée nommée nouvelle stratégie de commentaires d’embauche à un utilisateur nommé User1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Sujets associés

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)