---
title: Affectation, modification des emplacements d’urgence pour les utilisateurs
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
description: Dans cet article, vous allez découvrir comment affecter ou modifier l’emplacement d’urgence d’un emplacement pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809524"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Affectation ou modification de l’emplacement d’urgence d’un utilisateur

Chaque numéro de téléphone actif doit avoir un emplacement d’urgence associé lorsque vous attribuez le numéro de téléphone à un utilisateur. (Vous associez l’adresse lorsque vous obtenez un numéro de téléphone dans Office 365 ou lorsque vous transférez un numéro de téléphone.) Lorsque vous associez le numéro à un emplacement d’urgence, vous pouvez également ajouter un emplacement pour fournir un emplacement plus exact dans un emplacement physique. Il peut s’agit de l’étage, de l’aile d’un bâtiment ou du numéro du bureau où se trouve l’utilisateur. Vous pouvez avoir un nombre illimité d’emplacements pour un emplacement d’urgence donné, et vous pouvez changer d’emplacement si l’utilisateur change de bureau ou de bâtiment. Par exemple, si l’utilisateur passe de l’étage 34 au 35e.
  
Pour savoir comment obtenir des forfaits d’appels et leurs tarifs, consultez la gestion des [licences de module supplémentaire Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
Vous pouvez affecter ou modifier l’emplacement d’urgence d’un utilisateur dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Numéros de**  >  **téléphone vocal.**

2. Dans la page **Numéros de** téléphone, cliquez sur **l’onglet** Numéros, sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur **Modifier.**

3. Dans le **volet Édition,** sous Emplacement **d’urgence,** faites l’une des opérations suivantes :

    - Pour attribuer un lieu, recherchez l’emplacement, puis sélectionnez-le dans les résultats de la recherche.

    - Pour modifier l’emplacement déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement et l’emplacement existants, recherchez et sélectionnez l’emplacement à affecter.

4. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.** Par défaut, c’est le cas.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>Sujets associés

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
