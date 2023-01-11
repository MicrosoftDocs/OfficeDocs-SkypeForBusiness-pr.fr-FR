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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Découvrez comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 99ab0821b8ccdb14664dc0a2aa37c959499ff8ac
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774739"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence

Quelle que soit [l’option de connectivité RTC](pstn-connectivity.md) , vous pouvez choisir&mdash;des emplacements d’urgence Microsoft Calling Plans, Operator Connect, Teams Phone Mobile ou Direct Routing&mdash;peuvent être associés à un numéro de téléphone.

Toutefois, en fonction de votre option de connectivité RTC, la façon dont vous gérez les emplacements d’urgence et les exigences de localisation peuvent varier. Pour plus d’informations, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md).

Cet article explique comment ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation. 

Cet article s’applique aux forfaits d’appels Microsoft, à Operator Connect, à Teams Phone Mobile et au routage direct.

Vous gérez les emplacements d’urgence de votre organisation dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

Pour attribuer un emplacement d’urgence, les utilisateurs, les numéros de téléphone et les emplacements d’urgence doivent tous se trouver dans le même pays. Pour plus d’informations, consultez [Attribuer ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Ajouter un emplacement d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Emplacements Adresses** > **d’urgence**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom et une description pour l’emplacement.
4. Sélectionnez le pays ou la région, puis entrez l’adresse.

   > [!NOTE]
   > En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que pour activer correctement un numéro de téléphone dans Microsoft 365, l’adresse configurée dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’indicatif régional du numéro de téléphone.

5. Si l’adresse est introuvable et que vous souhaitez la modifier manuellement, activez **Modifier l’adresse manuellement**.
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Consultez [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modification d'un emplacement d'urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Emplacements Adresses** > **d’urgence**.
2. Dans la liste, sélectionnez l’emplacement que vous souhaitez modifier, puis cliquez sur **Modifier**.
3. Apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous pouvez modifier les informations d’adresse d’un emplacement uniquement si l’adresse n’est pas validée. Si l’adresse est déjà validée et que vous devez modifier l’adresse, supprimez l’emplacement, puis créez un nouvel emplacement avec l’adresse correcte.

### <a name="using-powershell"></a>Utiliser PowerShell

Consultez [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Supprimer un emplacement d’urgence

> [!NOTE]
> Vous pouvez supprimer un emplacement uniquement si aucun utilisateur ou numéro de téléphone ne lui est affecté. Si des numéros ou des utilisateurs sont affectés à l’emplacement, vous devez d’abord les supprimer.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Emplacements Adresses** > **d’urgence**.
2. Dans la liste, sélectionnez l’emplacement à supprimer, puis cliquez sur **Supprimer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Consultez [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)
