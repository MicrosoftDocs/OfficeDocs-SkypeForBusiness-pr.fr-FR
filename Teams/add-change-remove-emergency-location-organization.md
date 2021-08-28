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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation dans le Microsoft Teams d’administration. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62604fc26f91baa77bd205869bbe4251d1a46a8a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602299"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence

Un emplacement d’urgence doit être associé à un numéro de téléphone, mais lorsque cela se produit, cette situation peut varier d’un pays ou d’une région à l’autre. Par exemple, aux États-Unis, vous devez associer un emplacement d’urgence lorsque vous attribuez le numéro de téléphone à l’utilisateur. Au Royaume-Uni, vous devez associer un emplacement d’urgence au numéro de téléphone lorsque vous obtenez les numéros de téléphone à partir d’Microsoft 365 ou Office 365 ou transférez des numéros de téléphone à partir de votre fournisseur de services actuel.

Quel que soit le pays ou la région dans lesquels vous vous trouvez, vous pouvez ajouter un ou plusieurs emplacements à un emplacement d’urgence et supprimer un emplacement d’urgence. Selon le nombre d’emplacements physiques existant dans votre organisation, vous pouvez créer des bâtiments, des étages et des bureaux. Voir [Gérer les appels d’urgence.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Pour savoir comment obtenir un forfait d’appels et connaître son prix, consultez Teams [licences de module supplémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Vous gérez les emplacements d’urgence pour votre organisation dans le Microsoft Teams d’administration de l’entreprise ou à l’aide de PowerShell.
  
## <a name="add-an-emergency-location"></a>Ajouter un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Cliquez sur **Ajouter**.
3. Entrez un nom et une description pour l’emplacement.
4. Sélectionnez le pays ou la région, puis entrez l’adresse.

   > [!NOTE]
   > En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que, pour activer correctement un numéro de téléphone à Microsoft 365 ou Office 365, l’adresse définie dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’code de la zone du numéro de téléphone.

5. Si l’adresse est in trouvée et que vous voulez la modifier manuellement, vous pouvez activer modifier l’adresse **manuellement.**
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisCivicAddress.](/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Modification d'un emplacement d'urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Dans la liste, sélectionnez l’emplacement à modifier, puis cliquez sur **Modifier.**
3. A apporter les modifications de votre souhaitez.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous ne pouvez modifier les informations d’adresse d’un emplacement que si l’adresse n’est pas validée. Si l’adresse est déjà validée et que vous devez la modifier, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisCivicAddress.](/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Supprimer un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Dans la liste, sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisCivicAddress.](/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Rubriques connexes

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)