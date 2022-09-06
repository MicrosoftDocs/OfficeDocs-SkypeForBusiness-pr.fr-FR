---
title: Attribuer ou modifier des emplacements pour les emplacements d’urgence pour les utilisateurs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Dans cet article, vous allez apprendre à attribuer ou à modifier l’emplacement d’un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 749093e532dec92f8bf9788cc43fd0f052c461a4
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606593"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Affecter ou modifier l’emplacement d’un emplacement d’urgence pour un utilisateur

Quelle que soit [l’option de connectivité RTC](pstn-connectivity.md), vous choisissez&mdash;Plans d’appel Microsoft, Opérateur Connect, Fournisseur de connectivité mobile (préversion publique) ou Routage&mdash;direct, un emplacement d’urgence doit être affecté à chaque numéro de téléphone ou utilisateur.

Toutefois, selon votre option de connectivité RTC, la façon dont vous gérez et affectez des emplacements d’urgence pour un utilisateur peut varier. Pour plus d’informations, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).

Cet article explique comment attribuer ou modifier *l’emplacement* d’un emplacement d’urgence pour un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

Cet article s’applique aux forfaits d’appels, à Operator Connect et Fournisseur de connectivité mobile (préversion publique).

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **les numéros de téléphone** **vocal** > .

2. Dans la page **Numéros de téléphone** , cliquez sur l’onglet **Nombres** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier**.

3. Dans le volet **Modifier** , sous **Emplacement d’urgence**, effectuez l’une des opérations suivantes :

    - Pour attribuer un emplacement, recherchez l’emplacement ou l’emplacement, puis sélectionnez l’emplacement dans les résultats de la recherche.

    - Pour modifier l’emplacement déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement et l’emplacement existants, recherchez, puis sélectionnez l’emplacement que vous souhaitez attribuer.

4. Selon que vous souhaitez envoyer un e-mail à l’utilisateur avec ses informations de numéro de téléphone, désactivez ou activez **Email utilisateur avec les informations de numéro de téléphone**. Par défaut, cette option est activée.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)