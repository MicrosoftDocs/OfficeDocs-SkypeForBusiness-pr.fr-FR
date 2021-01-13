---
title: Affecter ou modifier un emplacement d’urgence pour un utilisateur
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809564"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Affecter ou modifier un emplacement d’urgence pour un utilisateur

Lorsque vous planifiez des forfaits d’appels, vous devez affecter un emplacement d’urgence à chaque numéro de téléphone ou utilisateur. En Europe, l’emplacement d’urgence est associé au numéro de téléphone lorsque vous l’obtenez à partir de Microsoft 365 ou d’Office 365, ou lorsque vous transférez un numéro de téléphone vers Microsoft 365 ou Office 365. Aux États-Unis, l’emplacement d’urgence est associé au numéro de téléphone lorsqu’il est affecté à l’utilisateur. L’adresse de secours peut être modifiée si l’utilisateur à qui elle est affectée change d’emplacement. Pour plus d’informations sur les adresses de secours et les emplacements d’urgence, voir Que sont les emplacements d’urgence, les lieux d’urgence et le [routage des appels](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)?
  
Pour savoir comment obtenir un plan d’appel et combien cela coûte, consultez la gestion des [licences de module supplémentaire Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
Vous pouvez affecter ou modifier un emplacement d’urgence pour un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Numéros de**  >  **téléphone vocal.**

2. Dans la page **Numéros de** téléphone, cliquez sur **l’onglet** Numéros, sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier.**

3. Dans le **volet Édition,** sous Emplacement **d’urgence,** faites l’une des opérations suivantes :

   - Pour affecter un emplacement d’urgence, recherchez et sélectionnez un emplacement d’urgence.

   - Pour modifier l’emplacement d’urgence déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement existant, puis recherchez et sélectionnez l’emplacement que vous voulez affecter.

4. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.** Par défaut, c’est le cas.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Sujets associés

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Affecter ou modifier un lieu pour un emplacement d’urgence pour un utilisateur](assign-change-emergency-place-user.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
