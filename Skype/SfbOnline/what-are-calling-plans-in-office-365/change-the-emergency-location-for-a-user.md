---
title: Affectation ou modification d’un emplacement d’urgence pour un utilisateur
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Découvrez comment modifier l’emplacement d’urgence pour vos utilisateurs. Avec un nombre illimité d’emplacements, vous pouvez modifier les emplacements d’urgence quand les employés se déplacement dans les étages ou les bâtiments. '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303833"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>Affectation ou modification d’un emplacement d’urgence pour un utilisateur

Chaque numéro de téléphone actif doit avoir une adresse de secours associée lorsque vous attribuez le numéro de téléphone à un utilisateur. (Vous associez l’adresse lorsque vous recevez un numéro de téléphone dans Office 365 ou lorsque vous transférez un numéro de téléphone.) Lorsque vous associez le numéro à une adresse de secours, vous pouvez également ajouter un emplacement d’urgence pour fournir un emplacement plus précis au sein d’un emplacement physique. Un emplacement d'urgence peut être l'étage, l'aile d'un bâtiment ou le numéro du bureau où se trouve l'utilisateur. Vous pouvez avoir un nombre illimité d’emplacements pour une adresse donnée en cas d’urgence, et vous pouvez modifier l’emplacement d’urgence si l’utilisateur se déplace vers une autre bureau ou bâtiment — par exemple, si l’utilisateur se déplace de l’étage 34 à l’étage 35.
  
Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="assign-or-change-the-emergency-location"></a>Affectation ou modification de l’emplacement d’urgence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de **** > gauche, accédez à**utilisateurs**vocaux vocaux.
    
    > [!IMPORTANT]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .
    
4. Dans la page **utilisateurs voix** , recherchez et sélectionnez l’utilisateur pour lequel vous souhaitez modifier l’emplacement d’urgence.
    
5. Dans le volet Action, sous **Emplacement d'urgence**, cliquez sur **Modifier**.
    
6. Dans la page **Attribuer un numéro**, cliquez sur **Changer l'emplacement**. 
    
7. Sous **changer l’adresse de secours en**, entrez le nom de la ville dans la zone, puis cliquez sur **Rechercher**.

8. Sélectionnez **Rechercher par emplacement** dans la liste déroulante, entrez une partie du nom de l’emplacement (par exemple, entrer **étage**), puis cliquez sur **Rechercher**. 
    
8. Sélectionnez l’emplacement d’urgence dans la liste, puis cliquez sur **Enregistrer**.
    
    Si vous voulez ajouter un nouvel emplacement d’urgence qui s’affichera dans la liste, voir [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-or-remove-an-emergency-location-for-your-organization.md).
    
## <a name="related-topics"></a>Voir aussi

[Affectation d’emplacements de réponse d’urgence via PowerShell](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[Ajout ou suppression d'une adresse d'urgence pour votre organisation](add-or-remove-an-emergency-address-for-your-organization.md)

[Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence](add-change-or-remove-an-emergency-location-for-your-organization.md)

[Qu’est-ce que la validation d’adresse ?](what-is-address-validation.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Cmdlet Set-CsOnlineVoiceUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
