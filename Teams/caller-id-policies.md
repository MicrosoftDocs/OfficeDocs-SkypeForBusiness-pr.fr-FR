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
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938463"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gérer les stratégies d’identification d’appelant dans Microsoft teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

En tant qu’administrateur, vous pouvez utiliser les stratégies d’identification d’appelant dans Microsoft teams pour modifier ou bloquer l’ID de l’appelant (également appelé ID de ligne d’appel). Par défaut, le nombre de numéros de téléphone des utilisateurs de teams est visible lors d’un appel vers un téléphone RTC et le numéro de téléphone des appelants PSTN peut être affiché lorsqu’ils appellent un utilisateur de teams. Vous pouvez utiliser les stratégies d’identification de l’appelant pour afficher un autre numéro de téléphone pour les utilisateurs teams de votre organisation ou bloquer l’affichage d’un numéro entrant.

Par exemple, lorsque les utilisateurs effectuent un appel, vous pouvez modifier l’identification de l’appelant pour afficher le numéro de téléphone principal de votre organisation à la place des numéros de téléphone des utilisateurs.

Vous gérez les stratégies d’identification de l' **Voice**appelant en accédant à  >  **stratégies d’identification** de l’appelant vocal dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

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

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Sujets associés

[Nouveau-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
