---
title: Affecter, modifier ou supprimer un numéro de téléphone d’un utilisateur
ms.author: tonysmit
author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez comment attribuer, modifier ou supprimer le numéro de téléphone professionnel de vos utilisateurs Skype Entreprise pour que les entreprises et les clients extérieurs puissent appeler.
ms.openlocfilehash: 40c067657132781d29b8f20a3738d6d28ce36331
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374657"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Affecter, modifier ou supprimer un numéro de téléphone d’un utilisateur

Lorsque vous configurez des Plans de l’appel dans Office 365, vous assignez les numéros de téléphone à vos utilisateurs. 

Dans le client Microsoft Teams, le numéro de téléphone que vous assignez apparaît lorsqu’ils cliquent sur **Appels**.

![Le numéro de téléphone de l’utilisateur affiché dans Microsoft Teams.](../images/teams-phone-number.png)

Dans Skype pour client d’entreprise, le numéro de téléphone que vous assignez est répertorié dans la zone **Téléphone professionnel** et ne peut pas être modifié par un utilisateur.
  
![Work Phone Number is Greyed Out.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Si un utilisateur souhaite [modifier son numéro de téléphone pour Skype pour les entreprises](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) et le numéro de téléphone dans la Skype pour l’application de gestion ne peut pas être modifié ou est grisée, ce que signifie un administrateur a configuré et il ne peut pas être modifiée par les.
  


Lorsque vous configurez les utilisateurs afin qu’ils peuvent émettre et recevoir des appels téléphoniques, vous devez tout d’abord utiliser le Skype entreprise centre d’administration et affecter un numéro de téléphone, mais vous pouvez modifier ou supprimer le numéro de téléphone si vous avez besoin.
  
Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Attribution d'un numéro de téléphone à un utilisateur
 
![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez à des **équipes Microsoft et Skype pour le centre d’administration Business** > **portail hérité**.
    
3. Dans la navigation de gauche, cliquez sur **voix** > **utilisateurs Enterprise Voice**.
   > [!NOTE]
   > Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.
 
   
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs auxquels vous souhaitez affecter un numéro de téléphone.
    
5. Dans le volet Action, cliquez sur **Affecter un numéro**.
    
6. Dans la page **attribuer le numéro** dans la liste **Sélectionnez le numéro à attribuer** , sélectionnez le numéro de téléphone de l’utilisateur.
    
    > [!TIP]
    > Si vous ne voyez pas les numéros de téléphone répertoriés, vous devez tout d’abord pour [obtenir les numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md) . Ou, si vous utilisez le **centre d’administration Skype Entreprise** > **Voix** > page **Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **Nouveaux numéros utilisateur**. 
  
7. Pour affecter ou modifier l’adresse d’urgence associée, sous **Sélectionnez validé emplacement en cas d’urgence**, sélectionnez l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, cliquez sur **Rechercher**.
    
8. Après avoir choisi le numéro de téléphone et l'adresse de secours, cliquez sur **Enregistrer**.
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Modifier un numéro de téléphone d’un utilisateur
 
![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez à des **équipes Microsoft et Skype pour le centre d’administration Business** > **portail hérité**.
    
3. Dans la navigation de gauche, cliquez sur **voix** > **utilisateurs Enterprise Voice**.
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez changer le numéro de téléphone.
    
5. Dans le volet Actions, sous **numéro assigné**, cliquez sur **Modifier**. 
    
6. Sur la page **Attribuer un numéro**, cliquez sur **Changer le numéro**.
    
7. Sur la page **Attribuer un numéro**, dans le menu **Sélectionner le numéro à attribuer**, sélectionnez le nouveau numéro de téléphone dans la liste déroulante. 
    
8. Pour modifier l’adresse d’urgence associée, cliquez sur **Modifier l’emplacement**, puis sous **Modifier l’adresse d’urgence à**, sélectionnez soit l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, cliquez sur **Recherche**.
    
9. Cliquez sur **Enregistrer**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Supprimer un numéro de téléphone d’un utilisateur
 
![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez à des **équipes Microsoft et Skype pour le centre d’administration Business** > **portail hérité**.
    
3. Dans la navigation de gauche, cliquez sur **voix** > **utilisateurs Enterprise Voice**.
    
4. Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs dont vous souhaitez supprimer le numéro de téléphone.
    
5. Dans le volet Actions, sous **numéro assigné**, cliquez sur **Supprimer**. 
    
6. Dans la page **Supprimer le numéro sélectionné attribué ?**, cliquez sur **Oui**.
    

## <a name="related-topics"></a>Rubriques connexes
[Qu’est-ce que la validation d’adresse ?](what-is-address-validation.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 