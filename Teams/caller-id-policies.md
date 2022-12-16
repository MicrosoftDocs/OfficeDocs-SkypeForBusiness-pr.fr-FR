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
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft Teams pour modifier ou bloquer l’ID d’appelant des utilisateurs Teams de votre organisation.
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414702"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’ID d’appelant dans Microsoft Teams

Par défaut, lorsqu’un utilisateur Teams passe un appel à un téléphone RTC, le numéro de téléphone de l’utilisateur Teams est visible. De même, lorsqu’un appelant RTC passe un appel à un utilisateur Teams, le numéro de téléphone de l’appelant RTC est visible.

En tant qu’administrateur, vous pouvez utiliser des stratégies d’ID d’appelant pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Vous pouvez utiliser des stratégies d’ID d’appelant pour afficher un autre numéro de téléphone pour les utilisateurs Teams de votre organisation, bloquer le numéro de téléphone sortant, empêcher l’affichage d’un numéro entrant ou définir le nom de la partie appelante (CNAM). Par exemple, lorsqu’un utilisateur passe un appel, vous pouvez modifier l’ID de l’appelant pour afficher le numéro de téléphone principal de votre organisation et le nom de l’entreprise au lieu du numéro de téléphone de l’utilisateur.

Vous gérez les stratégies d’ID de l’appelant en accédant à Stratégies **d’ID d’appelant** **vocal** >  dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

## <a name="create-a-custom-caller-id-policy"></a>Créer une stratégie d’ID d’appelant personnalisée

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Stratégies****d’ID de l’appelant vocal** > .
2. Cliquez sur **Ajouter**. <br>
![Capture d’écran de la page nouvelle stratégie d’ID d’appelant dans le Centre d’administration.](media/caller-id-policies-add-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. À partir de là, choisissez les paramètres souhaités :

    - **Bloquer l’ID de l’appelant entrant** : activez ce paramètre pour empêcher l’affichage de l’ID de l’appelant des appels entrants.
    - **Remplacer la stratégie d’ID de l’appelant** : activez ce paramètre pour permettre aux utilisateurs de remplacer les paramètres de la stratégie concernant l’affichage de leur numéro aux appelés ou non. Cela signifie que les utilisateurs peuvent choisir d’afficher ou non leur ID d’appelant. Pour plus d’informations, consultez [Contrôle par l’utilisateur final de l’ID d’appelant sortant](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).
    - **Remplacez l’ID de l’appelant** par : Définissez l’ID de l’appelant à afficher pour les utilisateurs en sélectionnant l’une des options suivantes :

        - **Numéro de l’utilisateur** : affiche le numéro de l’utilisateur. 
        - **Numéro de service** : vous permet de définir un numéro de téléphone de service à afficher en tant qu’ID de l’appelant.
        - **Anonyme** : affiche l’ID de l’appelant comme Anonyme.

    - **Remplacez l’ID de l’appelant par ce numéro de service** : choisissez un numéro de service pour remplacer l’ID de l’appelant des utilisateurs. Cette option est disponible si vous avez sélectionné **Numéro de service** dans **Remplacer l’ID de l’appelant par**.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-caller-id-policy"></a>Modifier une stratégie d’ID d’appelant

Vous pouvez modifier la stratégie globale ou les stratégies personnalisées que vous créez. 

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Stratégies****d’ID de l’appelant vocal** > .
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Modifiez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Affecter une stratégie d’ID d’appelant personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Rubriques connexes

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
