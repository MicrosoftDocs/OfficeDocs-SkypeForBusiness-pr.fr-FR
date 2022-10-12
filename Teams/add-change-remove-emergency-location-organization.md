---
title: Ajouter, modifier, supprimer des emplacements d’urgence
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
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23eb549592c8ead6983253d1a228020f3851e1a7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551488"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence

Quelle que soit [l’option de connectivité RTC](pstn-connectivity.md) que vous choisissez&mdash;, les plans d’appel Microsoft, Operator Connect, Teams Phone Mobile ou les emplacements d’urgence de routage&mdash;direct peuvent être associés à un numéro de téléphone.

Toutefois, selon votre option de connectivité RTC, la façon dont vous gérez les emplacements d’urgence et les exigences d’emplacement peut varier. Pour plus d’informations, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).

Cet article explique comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation. 

Cet article s’applique aux forfaits d’appels Microsoft, à Operator Connect, à Teams Phone Mobile et au routage direct.

Vous gérez les emplacements d’urgence de votre organisation dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

Pour affecter un emplacement d’urgence, les utilisateurs, les numéros de téléphone et les emplacements d’urgence doivent tous se trouver dans le même pays. Pour plus d’informations, consultez [Affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Ajouter un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Cliquez sur **Ajouter**.
3. Entrez un nom et une description pour l’emplacement.
4. Sélectionnez le pays ou la région, puis entrez l’adresse.

   > [!NOTE]
   > En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que pour activer correctement un numéro de téléphone dans Microsoft 365, l’adresse configurée dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’indicatif régional du numéro de téléphone.

5. Si l’adresse est introuvable et que vous souhaitez modifier manuellement l’adresse, **activez l’option Modifier l’adresse manuellement**.
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modification d'un emplacement d'urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Dans la liste, sélectionnez l’emplacement à modifier, puis cliquez sur **Modifier**.
3. Apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous ne pouvez modifier les informations d’adresse d’un emplacement que si l’adresse n’est pas validée. Si l’adresse est déjà validée et que vous devez modifier l’adresse, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Supprimer un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Adresses d’urgence emplacements** > .
2. Dans la liste, sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)