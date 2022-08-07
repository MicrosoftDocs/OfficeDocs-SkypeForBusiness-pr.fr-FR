---
title: Ajouter, modifier, supprimer des emplacements pour les emplacements d’urgence
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Découvrez comment ajouter, modifier ou supprimer un emplacement pour un emplacement d’urgence pour votre organisation.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1f142d7053a8254446d76dfab276baf9f6f12363
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269271"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation

Selon le nombre d’emplacements physiques dans votre organisation, vous pouvez ajouter *des emplacements pour les bâtiments* , les étages et les bureaux afin de créer un emplacement d’urgence plus spécifique.

Toutefois, selon votre option de connectivité RTC, la façon dont vous gérez les emplacements d’urgence et les exigences d’emplacement peut varier. Pour plus d’informations, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).

Cet article explique comment ajouter, modifier ou supprimer un *emplacement* d’urgence pour votre organisation.

Cet article s’applique aux plans d’appel Microsoft, à Operator Connect et au routage direct.

Vous gérez les emplacements d’urgence de votre organisation dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Ajouter un emplacement à un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez ajouter un emplacement.
3. Sous l’onglet **Emplacements** , cliquez sur **Ajouter**.
4. Entrez un nom de lieu, puis cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Modifier un emplacement pour un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez modifier un emplacement.
3. Sous l’onglet **Emplacements** , sélectionnez l’emplacement à modifier, puis cliquez sur **Modifier**.
4. Mettez à jour les informations d’emplacement, puis cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Supprimer un endroit d’un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Dans la liste, cliquez sur le nom de l’emplacement pour lequel vous souhaitez supprimer un emplacement.
3. Sous l’onglet **Emplacements** , sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Voir aussi

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)