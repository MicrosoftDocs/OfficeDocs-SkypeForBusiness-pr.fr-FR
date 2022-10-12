---
title: Affecter ou modifier un emplacement d’urgence pour un utilisateur
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
description: Dans cet article, vous allez découvrir comment affecter ou modifier un emplacement d’urgence pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a43ca031b8787d62639e141c3f733acdb402f85a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551648"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Affecter ou modifier un emplacement d’urgence pour un utilisateur

Quelle que soit [l’option de connectivité RTC](pstn-connectivity.md) que vous choisissez, vous choisissez&mdash;Plans d’appel Microsoft, Opérateur Connect, Teams Phone Mobile ou Routage&mdash;direct, un emplacement d’urgence doit être attribué à chaque numéro de téléphone ou utilisateur.

Toutefois, selon votre option de connectivité RTC, la façon dont vous gérez et affectez des emplacements d’urgence pour un utilisateur peut varier. Pour plus d’informations, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).

Cet article explique comment affecter ou modifier un emplacement d’urgence pour un utilisateur. 

Cet article s’applique aux forfaits d’appels, à Operator Connect et à Teams Phone Mobile.
  
Vous pouvez affecter ou modifier un emplacement d’urgence pour un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **les numéros de téléphone** **vocal** > .

2. Dans la page **Numéros de téléphone** , cliquez sur l’onglet **Nombres** , sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier**.

3. Dans le volet **Modifier** , sous **Emplacement d’urgence**, effectuez l’une des opérations suivantes :

   - Pour affecter un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.

   - Pour modifier l’emplacement d’urgence déjà affecté à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous souhaitez attribuer.

4. Selon que vous souhaitez envoyer un e-mail à l’utilisateur avec ses informations de numéro de téléphone, désactivez ou activez **Email utilisateur avec les informations de numéro de téléphone**. Par défaut, cette option est activée.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur](assign-change-emergency-place-user.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)
