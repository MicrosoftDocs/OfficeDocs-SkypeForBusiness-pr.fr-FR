---
title: Ajout, modification, suppression d’emplacements d’urgence
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
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Microsoft Teams d’administration.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121502"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation

Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez ajouter des bâtiments, des étages et des bureaux pour créer un emplacement d’urgence plus spécifique. Pour plus [d’informations, voir](what-are-emergency-locations-addresses-and-call-routing.md) Gérer les appels d’urgence.
  
Pour savoir comment obtenir un forfait d’appels et connaître son prix, consultez Teams [licences de module supplémentaire.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Vous gérez les emplacements d’urgence pour votre organisation dans le Microsoft Teams d’administration de l’entreprise ou à l’aide de PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Ajout d’un emplacement à un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un lieu.
3. Sous **l’onglet** Espaces, cliquez sur **Ajouter.**
4. Entrez un nom d’lieu, puis cliquez sur **Appliquer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisLocation.](/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>Modification d’un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.
3. Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez modifier, puis cliquez sur **Modifier.**
4. Mettez à jour les informations sur l’endroit, puis cliquez sur **Appliquer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>Supprimer un emplacement d’un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un lieu.
3. Sous **l’onglet** Espaces, sélectionnez l’endroit que vous voulez supprimer, puis cliquez sur **Supprimer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisLocation.](/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>Sujets associés

- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)