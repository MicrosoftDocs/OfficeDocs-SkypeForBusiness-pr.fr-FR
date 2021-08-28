---
title: Gérer les stratégies d’ID d’appelant dans Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft Teams modifier ou bloquer l’ID d’appelant des Teams utilisateurs dans votre organisation.
ms.openlocfilehash: ee663a627e89d7ea2a569496a899d2d68b8366ef
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619630"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’ID d’appelant dans Microsoft Teams

> [!NOTE]
> Pour définir l’ID d’appelant sur un numéro de téléphone de compte de ressource et définir le nom de l’appelant, utilisez les cmdlets PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity dans le module Teams PowerShell 2.3.1 ou une ultérieure. (Ces options ne sont actuellement pas disponibles dans le Microsoft Teams d’administration.) 

Par défaut, lorsqu’Teams un utilisateur appelle un téléphone PSTN, le numéro de téléphone de l’Teams est visible. De même, lorsqu’un appelant PSTN appelle un Teams, le numéro de téléphone de l’appelant PSTN est visible.

En tant qu’administrateur, vous pouvez utiliser les stratégies d’ID d’appelant pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Vous pouvez utiliser les stratégies d’ID d’appelant pour afficher un autre numéro de téléphone pour les Teams utilisateurs de votre organisation, bloquer l’affichage du numéro de téléphone sortant, bloquer l’affichage d’un numéro entrant ou définir le nom de l’appelant (CNAM). Par exemple, lorsqu’un utilisateur passe un appel, vous pouvez modifier l’ID de l’appelant pour afficher le numéro de téléphone principal et le nom de la société de votre organisation à la place du numéro de téléphone de l’utilisateur.

Pour gérer les stratégies d’ID d’appelant, vous devez vous rendre sur les stratégies d’ID d’appelant vocal dans le   >   Microsoft Teams d’administration. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

## <a name="create-a-custom-caller-id-policy"></a>Créer une stratégie d’ID d’appelant personnalisée

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez **aux** stratégies  >  **d’ID d’appelant vocal.**
2. Cliquez sur **Ajouter**. <br>
![Capture d’écran de la page de stratégie d’ID d’appelant dans le Centre d’administration](media/caller-id-policies-add-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. À partir de là, choisissez les paramètres de votre choix :

    - **Bloquer l’ID d’appelant** entrant : activer ce paramètre pour empêcher l’affichage de l’ID d’appelant des appels entrants.
    - Remplacer la stratégie **d’ID** d’appelant : activer ce paramètre pour que les utilisateurs remplacent les paramètres de la stratégie concernant l’affichage de leur numéro à des appelants ou non. Cela signifie que les utilisateurs peuvent choisir d’afficher ou non leur ID d’appelant. Pour plus d’informations, voir [Contrôle de l’ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)d’appelant sortant par l’utilisateur final.
    - **Remplacez l’ID d’appelant** par : Définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des sélections suivantes :

        - **Numéro de l’utilisateur**: affiche le numéro de l’utilisateur. 
        - **Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’ID d’appelant.
        - **Anonyme**: affiche l’ID de l’appelant comme anonyme.

    - **Remplacez l’ID d’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’ID d’appelant des utilisateurs. Cette option est disponible si vous avez sélectionné le numéro **de service** dans **Remplacer l’ID d’appelant par**.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-caller-id-policy"></a>Modifier une stratégie d’ID d’appelant

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez. 

1. Dans le navigation gauche du centre Microsoft Teams d’administration, allez **aux** stratégies  >  **d’ID d’appelant vocal.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Modifiez les paramètres de votre souhaitez, puis cliquez sur **Enregistrer.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Affecter une stratégie d’ID d’appelant personnalisé aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Rubriques connexes

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)