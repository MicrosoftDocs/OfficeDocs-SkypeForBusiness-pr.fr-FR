---
title: Ajout, modification, suppression d’emplacements d’urgence
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
description: 'Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634853"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence

Quelle que soit l’option de connectivité [RST que](pstn-connectivity.md) vous choisissez, les plans d’appel Microsoft, les Connecter d’opérateur ou les emplacements d’urgence de routage direct peuvent être associés à &mdash; un numéro de &mdash; téléphone.

Toutefois, en fonction de l’option de connectivité PSTN, la façon dont vous gérez les emplacements d’urgence et les exigences d’emplacement peut varier. Pour plus d’informations, voir [Gérer les appels d’urgence.](what-are-emergency-locations-addresses-and-call-routing.md)

Cet article décrit comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation. 

Cet article s’applique aux plans d’appel Microsoft, aux Connecter opérateurs et au routage direct.

Vous gérez les emplacements d’urgence pour votre organisation via le Microsoft Teams d’administration de l’entreprise ou à l’aide de PowerShell.

Pour affecter un emplacement d’urgence, les utilisateurs, les numéros de téléphone et les emplacements d’urgence doivent tous se trouver dans le même pays. Pour plus d’informations, [voir Affecter ou modifier un emplacement d’urgence pour un utilisateur.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>Ajouter un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, cliquez sur   >  **Adresses d’urgence d’emplacements.**
2. Cliquez sur **Ajouter**.
3. Entrez un nom et une description pour l’emplacement.
4. Sélectionnez le pays ou la région, puis entrez l’adresse.

   > [!NOTE]
   > En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que, pour activer correctement un numéro de téléphone dans Microsoft 365, l’adresse définie dans l’emplacement d’urgence, qui est utilisée pour acquérir le numéro, doit correspondre à l’code de la zone du numéro de téléphone.

5. Si l’adresse est in trouvée et que vous voulez la modifier manuellement, activer la modification **manuelle de l’adresse.**
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

## <a name="related-topics"></a>Sujets associés

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)