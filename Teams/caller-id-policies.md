---
title: Gérer les stratégies d’ID d’appelant dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser et gérer les stratégies d’ID d’appelant dans Microsoft Teams pour modifier ou bloquer l’ID d’appelant des utilisateurs de Teams dans votre organisation.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255527"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’ID d’appelant dans Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

En tant qu’administrateur, vous pouvez utiliser les stratégies d’ID d’appelant dans Microsoft Teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Par défaut, le numéro de téléphone des utilisateurs de Teams est visible lorsqu’ils appelez un téléphone RSTN, et le numéro de téléphone des appelants PSTN est visible lorsqu’ils appellent un utilisateur de Teams. Vous pouvez utiliser des stratégies d’ID d’appelant pour afficher un autre numéro de téléphone pour les utilisateurs de Teams dans votre organisation ou bloquer l’affichage d’un numéro entrant.

Par exemple, lorsque les utilisateurs font un appel, vous pouvez modifier l’ID de l’appelant pour afficher le numéro de téléphone principal de votre organisation plutôt que les numéros de téléphone des utilisateurs.

Pour gérer les stratégies d’ID d’appelant, vous devez vous rendre sur stratégies d’ID d’appelant vocal   >   dans le Centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

## <a name="create-a-custom-caller-id-policy"></a>Créer une stratégie d’ID d’appelant personnalisée

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez **aux** stratégies  >  **d’ID d’appelant vocal.**
2. Cliquez sur **Ajouter**. <br>
![Capture d’écran de la page de stratégie d’ID d’appelant dans le Centre d’administration](media/caller-id-policies-add-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. À partir de là, choisissez les paramètres de votre choix :

    - **Bloquer l’ID d’appelant** entrant : activer ce paramètre pour empêcher l’affichage de l’ID d’appelant des appels entrants.
    - Remplacer la stratégie **d’ID** d’appelant : activer ce paramètre pour que les utilisateurs remplacent les paramètres de la stratégie concernant l’affichage de leur numéro pour les appelants ou non. Cela signifie que les utilisateurs peuvent choisir d’afficher ou non leur ID d’appelant. Pour plus d’informations, voir [Contrôle de l’ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)d’appelant sortant par l’utilisateur final.
    - **Remplacez l’ID d’appelant** par : Définissez l’ID d’appelant à afficher pour les utilisateurs en sélectionnant l’une des sélections suivantes :

        - **Numéro de l’utilisateur**: affiche le numéro de l’utilisateur. 
        - **Numéro de service**: vous permet de définir un numéro de téléphone de service à afficher en tant qu’ID d’appelant.
        - **Anonyme**: affiche l’ID de l’appelant comme anonyme.

    - **Remplacez l’ID d’appelant par ce numéro de service**: sélectionnez un numéro de service pour remplacer l’ID d’appelant des utilisateurs. Cette option est disponible si vous avez sélectionné le numéro **de service** dans **Remplacer l’ID d’appelant par**.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-caller-id-policy"></a>Modifier une stratégie d’ID d’appelant

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez. 

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez **aux** stratégies  >  **d’ID d’appelant vocal.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Modifiez les paramètres de votre souhaitez, puis cliquez sur **Enregistrer.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Affecter une stratégie d’ID d’appelant personnalisé aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Sujets associés

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
