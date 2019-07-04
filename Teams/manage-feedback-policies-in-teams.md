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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs teams de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540952"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gérer les stratégies de commentaires dans Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Les utilisateurs peuvent envoyer des commentaires et des suggestions concernant teams à **** > **** Microsoft en accédant à des commentaires dans les clients Teams. Nous cherchons constamment à améliorer l’expérience d’équipe et nous utilisons ces commentaires pour améliorer les équipes.

![Capture d’écran de l’option envoyer des commentaires dans Microsoft teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Les données envoyées par le biais de **Commentaires** sont considérées comme des «données de support» dans votre contrat 365 Office, y compris des informations qui seraient considérées comme «données client» ou «données personnelles».

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Définir si les utilisateurs peuvent envoyer des commentaires sur teams à Microsoft

En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft. Par défaut, tous les utilisateurs de votre organisation reçoivent automatiquement la stratégie globale par défaut de l’organisation et la fonctionnalité est activée dans la stratégie. L’exception est teams pour l’éducation, où la fonctionnalité est activée pour les enseignants et désactivée pour les étudiants.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur. Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur. Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.

Par exemple, supposons que vous souhaitiez permettre à tous les utilisateurs de votre organisation d’envoyer des commentaires à l’exception des nouvelles recrues dans la formation. Dans ce scénario, vous créez une stratégie personnalisée pour désactiver cette fonctionnalité et l’affecter aux nouvelles recrues. Tous les autres utilisateurs de votre organisation obtiennent la politique globale avec la fonction activée.  

Vous pouvez utiliser l’applet de nouvelle applet de **nouveau-CsTeamsFeedbackPolicy** pour créer une stratégie personnalisée et l’applet de passe **Grant-CsTeamsFeedbackPolicy** pour l’attribuer à un ou plusieurs utilisateurs ou groupes d’utilisateurs, par exemple un groupe de sécurité ou un groupe de distribution. 

Définissez le paramètre **userInitiatedMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée pour formuler des commentaires. Le fait de définir **** le paramètre sur Disabled désactive la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne peuvent pas envoyer de commentaires.

## <a name="create-a-custom-feedback-policy"></a>Créer une stratégie de commentaires personnalisée

Dans cet exemple, nous créons une stratégie de commentaires appelée nouvelle politique de commentaires sur les employés et nous désactivons la possibilité d’envoyer des commentaires.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Assigner une stratégie de commentaires personnalisée

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Assigner une stratégie de commentaires personnalisée à un utilisateur

Dans cet exemple, nous affectons une stratégie personnalisée nommée nouvelle stratégie de commentaires d’embauche à un utilisateur nommé User1.

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Assigner une stratégie de commentaires personnalisée aux utilisateurs d’un groupe

Vous pouvez assigner une stratégie de commentaires personnalisée à plusieurs utilisateurs que vous avez déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.

Dans cet exemple, nous affectons un exemple de stratégie de commentaires personnalisé appelé nouvelle stratégie de commentaires d’embauche à tous les utilisateurs du groupe contoso New HiRes.  

Obtenez la GroupObjectId du groupe en particulier.
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Obtenez les membres du groupe spécifié.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie de commentaires particulière. Dans cet exemple, il s’agit de la nouvelle politique de commentaires sur les employés.
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="related-topics"></a>Voir aussi

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)