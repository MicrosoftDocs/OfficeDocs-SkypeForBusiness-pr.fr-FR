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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de teams au sein de votre organisation.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349778"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’identification d’appelant dans Microsoft teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams. Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.

Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.

Vous gérez les stratégies d’identification de l' **Voice**appelant en accédant à  >  **stratégies d’identification** de l’appelant vocal dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer des stratégies personnalisées et les attribuer à des utilisateurs. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur. Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.

## <a name="create-a-custom-caller-id-policy"></a>Créer une stratégie d’ID d’appelant personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.
2. Cliquez sur **Ajouter**. <br>
![Capture d’écran de la nouvelle page de stratégie d’ID d’appelant dans le centre d’administration](media/caller-id-policies-add-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. À partir de cet emplacement, sélectionnez les paramètres de votre choix :

    - **Bloquer l’ID d’appelant entrant**: activez ce paramètre pour bloquer l’identification de l’appelant lors de l’affichage d’appels entrants.
    - **Remplacer la stratégie d’ID d’appelant**: activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants. Cela signifie que les utilisateurs peuvent décider d’afficher leur ID d’appelant. Pour plus d’informations, reportez-vous à [contrôle de l’ID d’appelant sortant par l’utilisateur final](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Remplacez l’identification de l’appelant**par : définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :

        - **Numéro de**l’utilisateur : affiche le numéro de l’utilisateur. 
        - **Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’identifiant de l’appelant.
        - **Anonyme**: affiche l’ID de l’appelant comme anonyme.

    - **Remplacez l’identification de l’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’identifiant de l’appelant. Cette option n’est disponible que si vous avez sélectionné **numéro de service** dans **remplacer l’identifiant de l’appelant par**.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-caller-id-policy"></a>Modifier une stratégie d’ID d’appelant

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez. 

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à stratégies d’identification de l'  >  **appelant**vocal.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Attribuer une stratégie d’ID d’appelant personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise et attribuer une stratégie personnalisée aux utilisateurs d’un groupe, tels qu’un groupe de sécurité ou un groupe de distribution.

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a>Assigner une stratégie d’ID de ligne d’appelant personnalisée aux utilisateurs

Pour attribuer une stratégie à un utilisateur :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **stratégie d’identification**de l’appelant, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur l' &#x2713; (coche) en haut du tableau.
3. Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **appliquer**.  

Vous pouvez également effectuer les opérations suivantes :

1. Accédez au **Centre d’administration Microsoft teams**  >  **Voice**  >  **Caller ID policies**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
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

 ## <a name="related-topics"></a>Rubriques connexes

- [Nouveau-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
