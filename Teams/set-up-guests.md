---
title: "Configurer un accès invité dans Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Activez la fonctionnalité d'accès invité dans Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a>Configurer un accès invité dans Teams
======================================

Microsoft Teams est basé sur les groupes Office 365 et sur SharePoint Online. Voilà pourquoi des paramètres spécifiques doivent être activés dans les groupes Office 365 et dans SharePoint Online en plus de la fonctionnalité d'accès invité dans Teams.


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Autoriser l'ajout d'invités dans les groupes Office 365
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.
    
  
3. Sélectionnez **Groupes Office 365**.
    
     ![Groupes Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Sur la page Groupes Office 365, définissez la bascule sur **Activé** ou **Désactivé**, pour autoriser ou non les propriétaires d'équipes et de groupes en dehors de votre organisation à accéder aux groupes Office 365. Définissez la bascule sur **Activé** près de l'option **Autoriser les propriétaires d'équipe à ajouter des personnes en dehors de l'organisation aux groupes**.


![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>Activer le partage dans SharePoint Online

Dans SharePoint Online, l'option de partage permet d'ajouter des invités à votre organisation. Elle est activée par défaut. Pour connaître la procédure de désactivation de l'option de partage, reportez-vous à la rubrique [Activer ou désactiver l'option de partage](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).
  
   Les administrateurs peuvent créer des comptes invités dans Azure Active Directory, indépendamment des paramètres de partage externe. Si le partage externe est désactivé, seul un administrateur peut créer des comptes invités. 
    

> [!IMPORTANT]
> Si vous désactivez l'option de partage, l'accès invité n'est pas disponible. 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Activer ou désactiver l'accès invité de Microsoft Teams
<a name="bkmk_TurnonOrTurnOff"> </a>

En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités. 

Les paramètres d'invité sont définis dans Azure Active Directory. Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365. Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.



1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.
    
     ![Connectez-vous à Office 365, accédez au Centre d'administration d'Office 365, accédez aux Paramètres, puis sélectionnez Services &amp; compléments.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Sélectionnez **Microsoft Teams**.
    
     ![La capture d'écran illustre l'option du complément Microsoft Teams, sélectionnée dans le centre d'administration d'Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. Dans **Sélectionnez le type d'utilisateur/licence que vous souhaitez configurer**, sélectionnez **Invité**.
   
    ![La capture d'écran du complément Microsoft Teams illustre la licence Invité sélectionnée et l'option Microsoft Teams définie sur Activé.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Définissez la bascule près de l'option **Activer/désactiver Microsoft Teams pour tous les utilisateurs de ce type** sur **Activé** pour activer Microsoft Teams et l'accès invité à votre organisation et sélectionnez **Enregistrer**. 
    
  

