---
title: Ajout, modification et suppression d’emplacements d’urgence
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
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le centre d’administration Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bed76fdfff2a6af2dabb3eef5c01dcfb39f422a
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539461"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence

Un emplacement d’urgence doit être associé à un numéro de téléphone, mais lorsque cela se produit peut varier d’un pays à l’autre. Par exemple, aux États-Unis, vous devez associer un emplacement d’urgence lorsque vous attribuez le numéro de téléphone à l’utilisateur. Au Royaume-Uni, vous devez associer un emplacement d’urgence au numéro de téléphone lorsque vous recevez les numéros de téléphone d’Office 365 ou que vous transférez des numéros de téléphone de votre fournisseur de services actuel.

Quel que soit le pays ou la région où vous vous trouvez, vous pouvez ajouter un lieu ou des lieux à un emplacement d’urgence et supprimer un emplacement d’urgence. En fonction du nombre d’emplacements physiques au sein de votre organisation, vous pouvez créer des lieux pour les bâtiments, les étages et les bureaux. Voir [gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).
  
Pour plus d’informations sur la façon d’obtenir un plan d’appels et son coût, voir [licences de module complémentaire équipes](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Vous gérez les emplacements d’urgence de votre organisation dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.
  
## <a name="add-an-emergency-location"></a>Ajouter un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom et une description pour l’emplacement.
4. Sélectionnez le pays ou la région, puis entrez l’adresse.

   > [!NOTE]
   > En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre qu’il est nécessaire d’activer un numéro de téléphone dans Office 365, mais que l’adresse définie au lieu d’urgence, qui est utilisée pour acquérir le numéro, doit correspondre à l’indicatif de la région du numéro de téléphone.
5. Si l’adresse est introuvable et que vous voulez modifier manuellement l’adresse, activez **la fonction modifier l’adresse manuellement**.
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modification d'un emplacement d'urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Dans la liste, sélectionnez l’emplacement que vous voulez modifier, puis cliquez sur **modifier**.
3. Apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous pouvez modifier les informations d’adresse d’un emplacement uniquement si l’adresse n’est pas validée. Si l’adresse est déjà validée et que vous devez modifier l’adresse, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Supprimer un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**d'  >  **urgence**.
2. Dans la liste, sélectionnez l’emplacement que vous voulez supprimer, puis cliquez sur **supprimer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Voir aussi

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)
