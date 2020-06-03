---
title: Ajout, modification et suppression de lieux pour les emplacements d’urgence
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
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le centre d’administration Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539431"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation

En fonction du nombre d’emplacements physiques au sein de votre organisation, vous pouvez ajouter des emplacements pour les bâtiments, planchers et bureaux pour créer un emplacement d’urgence plus précis. Pour plus d’informations, voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) .
  
Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Vous gérez les emplacements d’urgence de votre organisation dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Ajouter un emplacement à un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un emplacement.
3. Dans l’onglet **emplacements** , cliquez sur **Ajouter**.
4. Entrez un nom de lieu, puis cliquez sur **appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Modification d’un emplacement pour un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.
3. Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez modifier, puis cliquez sur **modifier**.
4. Mettez à jour les informations de lieu, puis cliquez sur **appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Supprimer un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un emplacement.
3. Dans l’onglet **emplacements** , sélectionnez l’emplacement que vous voulez supprimer, puis cliquez sur **supprimer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Voir aussi

- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
