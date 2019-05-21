---
title: Affectation, modification ou suppression du numéro de téléphone d’un utilisateur
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
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
description: Découvrez comment affecter, modifier ou supprimer un numéro de téléphone professionnel pour vos équipes ou les utilisateurs Skype entreprise de sorte que les entreprises et les clients externes puissent appeler.
ms.openlocfilehash: f9792edf76d5d86a562516aa620bfbb62d26fdd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286284"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur

Lorsque vous configurez des forfaits d’appels dans Office 365, vous attribuez des numéros de téléphone à vos utilisateurs. 

Dans le client Microsoft Teams, le numéro de téléphone que vous assignez apparaît lorsqu’ils cliquent sur **Appels**.

![Le numéro de téléphone de l’utilisateur affiché dans Microsoft Teams.](media/teams-phone-number.png)

Dans le client Skype entreprise, le numéro de téléphone que vous attribuez figurera dans la zone **téléphone professionnel** et ne peut pas être modifié par un utilisateur.
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Si un utilisateur souhaite [changer son numéro de téléphone pour Skype entreprise](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) et si le numéro de téléphone dans l’application Skype entreprise ne peut pas être modifié ou s’il est grisé, cela signifie qu’un administrateur l’a configuré pour eux et qu’il ne peut pas être modifié.
  


Lorsque vous configurez les utilisateurs pour qu’ils puissent passer et recevoir des appels téléphoniques, vous devez d’abord utiliser le centre d’administration Skype entreprise et attribuer un numéro de téléphone, mais vous pouvez modifier ou supprimer le numéro de téléphone le cas échéant.
  
Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Affectation d’un numéro de téléphone à un utilisateur
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .
   > [!NOTE]
   > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .
 
   
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs auxquels vous souhaitez affecter un numéro de téléphone.
    
5. Dans le volet Action, cliquez sur **Affecter un numéro**.
    
6. Dans la page **attribuer un numéro** , dans la liste Sélectionner le **numéro à attribuer** , sélectionnez le numéro de téléphone de l’utilisateur.
    
    > [!TIP]
    > Si vous ne voyez aucun numéro de téléphone dans la liste, vous devez d’abord [obtenir des numéros de téléphone pour vos utilisateurs](/microsoftteams/getting-phone-numbers-for-your-users) . Ou, si vous utilisez le **centre d’administration Skype Entreprise** > **Voix** > page **Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **Nouveaux numéros utilisateur**. 
  
7. Pour attribuer ou modifier l’adresse d’urgence associée, sous **Sélectionner l’emplacement d’urgence validée**, sélectionnez l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, puis cliquez sur **Rechercher**.
    
8. Après avoir choisi le numéro de téléphone et l'adresse de secours, cliquez sur **Enregistrer**.
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Changer le numéro de téléphone d’un utilisateur
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez changer le numéro de téléphone.
    
5. Dans le volet action, sous **numéro attribué**, cliquez sur **modifier**. 
    
6. Sur la page **Attribuer un numéro**, cliquez sur **Changer le numéro**.
    
7. Sur la page **Attribuer un numéro**, dans le menu **Sélectionner le numéro à attribuer**, sélectionnez le nouveau numéro de téléphone dans la liste déroulante. 
    
8. Pour modifier l’adresse de secours associée, cliquez sur **changer l’emplacement**, puis sous **changer l’adresse de secours en**, sélectionnez l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, puis cliquez sur **Recherchez**.
    
9. Cliquez sur **Enregistrer**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Supprimer le numéro de téléphone d’un utilisateur
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs dont vous souhaitez supprimer le numéro de téléphone.
    
5. Dans le volet action, sous **numéro attribué**, cliquez sur **supprimer**. 
    
6. Dans la page **Supprimer le numéro sélectionné attribué ?**, cliquez sur **Oui**.
    

## <a name="related-topics"></a>Voir aussi
[Qu’est-ce que la validation d’adresse ?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 