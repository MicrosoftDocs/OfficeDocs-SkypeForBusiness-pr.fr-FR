---
title: Affecter ou modifier un emplacement d’urgence pour un utilisateur
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Dans cet article, vous allez découvrir comment affecter ou modifier un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232475"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Affecter ou modifier un emplacement d’urgence pour un utilisateur

Lorsque vous configurez des plans d’appel, vous devez attribuer un emplacement d’urgence à chaque numéro de téléphone ou utilisateur. Dans les pays d’Europe, l’emplacement d’urgence est associé au numéro de téléphone lorsque vous l’obtenez d’Office 365 ou lorsque vous transférez un numéro de téléphone vers Office 365. Aux États-Unis, l’emplacement d’urgence est associé au numéro de téléphone attribué à l’utilisateur. L’adresse de secours peut être changée si l’utilisateur auquel elle est affectée se déplace vers un nouvel emplacement. Pour en savoir plus sur les adresses de secours et les emplacements d’urgence, voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).
  
Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Vous pouvez attribuer ou modifier un emplacement d’urgence pour un utilisateur dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de **Voice**Microsoft Teams, cliquez sur  >  **numéros de téléphone**vocaux.

2. Dans la page **numéros de téléphone** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **modifier**.

3. Dans le volet **édition** , sous **emplacement d’urgence**, effectuez l’une des opérations suivantes :

   - Pour attribuer un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.

   - Pour modifier l’emplacement d’urgence qui est déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous voulez attribuer.

4. Cliquez sur **Enregistrer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Sujets associés

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur](assign-change-emergency-place-user.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
