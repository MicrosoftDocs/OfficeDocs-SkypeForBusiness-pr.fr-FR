---
title: Gérer les stratégies d’identification d’appelant dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de teams au sein de votre organisation.
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992884"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’identification d’appelant dans Microsoft teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams. Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.

Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.

Vous gérez les stratégies d’identification de l’appelant en accédant à**stratégies d’identification** de l’appelant **vocal** > dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer des stratégies personnalisées et les affecter à des utilisateurs. Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur. Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.

## <a name="create-a-custom-caller-id-policy"></a>Créer une stratégie d’ID d’appelant personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’identification**de l’appelant **vocal** > .
2. Cliquez sur **Ajouter**.
![Capture d’écran de la nouvelle page de stratégie d’ID d’appelant dans le centre d’administration](media/caller-id-policies-add-policy.png)
3. Entrez le nom et la description de la stratégie.
4. À partir de cet emplacement, sélectionnez les paramètres de votre choix :

    - **Bloquer l’ID d’appelant entrant**: activez ce paramètre pour bloquer l’identification de l’appelant lors de l’affichage d’appels entrants.
    - **Les utilisateurs peuvent ignorer la stratégie d’ID d’appelant**: activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants. Cela signifie que les utilisateurs peuvent décider d’afficher leur ID d’appelant.
    - **Remplacer l’identification**de l’appelant : définissez l’ID de l’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :

        - **Numéro de**l’utilisateur : affiche le numéro de l’utilisateur. 
        - **Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’identifiant de l’appelant.
        - **Anonyme**: affiche l’ID de l’appelant comme anonyme.

    - **Numéro de service à utiliser pour remplacer l’identifiant de l’appelant**: sélectionnez un numéro de service pour remplacer l’identifiant de l’appelant. Cette option n’est disponible que si vous avez sélectionné **numéro de service** dans **remplacer l’identifiant**de l’appelant.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-caller-id-policy"></a>Modifier une stratégie d’ID d’appelant

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez. 

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies d’identification**de l’appelant **vocal** > .
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Attribuer une stratégie d’ID d’appelant personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>Assigner une stratégie d’ID de ligne d’appelant personnalisée à un utilisateur

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **stratégie d’identification**de l’appelant, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>Assigner une stratégie d’ID de ligne d’appel personnalisée à plusieurs utilisateurs à la fois

Pour assigner une stratégie d’ID de ligne d’appel personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Accédez**** > **** au > Centre d' **administration Microsoft teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Assigner une stratégie d’ID d’appelant personnalisée aux utilisateurs d’un groupe

Vous pouvez assigner une stratégie personnalisée à plusieurs utilisateurs que vous avez déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité. Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).

Dans cet exemple, nous affectons une stratégie de capot d’appelant personnalisé appelée stratégie d’ID d’appelant à tous les utilisateurs du groupe de support technique contoso.  

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Obtenez les membres du groupe spécifié.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie d’ID d’appelant particulière. Dans cet exemple, la stratégie d’ID d’appelant est prise en charge.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

 ## <a name="related-topics"></a>Voir aussi

- [Nouveau-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

