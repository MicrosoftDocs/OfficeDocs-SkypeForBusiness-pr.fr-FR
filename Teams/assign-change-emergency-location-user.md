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
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788658"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Affecter ou modifier un emplacement d’urgence pour un utilisateur

Lorsque vous configurez des plans d’appel, vous devez attribuer un emplacement d’urgence à chaque numéro de téléphone ou utilisateur. Dans les pays d’Europe, l’emplacement d’urgence est associé au numéro de téléphone lorsque vous l’obtenez de Microsoft 365 ou d’Office 365 ou lorsque vous transférez un numéro de téléphone vers Microsoft 365 ou Office 365. Aux États-Unis, l’emplacement d’urgence est associé au numéro de téléphone attribué à l’utilisateur. L’adresse de secours peut être changée si l’utilisateur auquel elle est affectée se déplace vers un nouvel emplacement. Pour en savoir plus sur les adresses de secours et les emplacements d’urgence, voir [que sont les emplacements d’urgence, les emplacements d’urgence et le routage des appels ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).
  
Pour plus d’informations sur la façon d’obtenir des offres d’appels et leur coût, voir [licences de complément d’équipes](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
  
Vous pouvez attribuer ou modifier un emplacement d’urgence pour un utilisateur dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de **Voice**Microsoft Teams, cliquez sur  >  **numéros de téléphone**vocaux.

2. Dans la page **numéros de téléphone** , cliquez sur l’onglet **numéros** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **modifier**.

3. Dans le volet **édition** , sous **emplacement d’urgence**, effectuez l’une des opérations suivantes :

   - Pour attribuer un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.

   - Pour modifier l’emplacement d’urgence qui est déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous voulez attribuer.

4. Si vous souhaitez envoyer à l’utilisateur un message électronique contenant son numéro de téléphone, désactivez ou activez l’option **courrier électronique avec les informations**sur le numéro de téléphone. Par défaut, ce paramètre est activé.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Voir aussi

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur](assign-change-emergency-place-user.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
