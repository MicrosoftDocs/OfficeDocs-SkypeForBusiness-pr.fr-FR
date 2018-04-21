---
title: Réinitialiser l'ID de conférence d'un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 3c40c4bb59dd6628730542f73d8bdbddae7b9ad7
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>Réinitialiser l'ID de conférence d'un utilisateur

Un ID de conférence dynamique est inclus au bas des invitations à ainsi que les numéros de téléphone qui peuvent être utilisés par les appelants pour appeler à une réunion. Lorsque l’utilisateur compose le numéro de téléphone, la surveillance automatique pour la réunion demandera à l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.
  
> [!NOTE]
> Si votre fournisseur de conférence est Microsoft, ID de conférence de vos utilisateurs sont définis uniquement dynamique par défaut. Malheureusement, il n’existe aucune possibilité de le modifier dans le Skype pour Business Admin Center ou à l’aide de Windows Powershell pour deviennent statiques, comme il s’agit désormais non pris en charge.
ID de conférence sont uniquement automatiquement définies uniquement pour Skype pour les utilisateurs professionnels et Microsoft Teams activé pour les conférences Audio. 
  
## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence pour un utilisateur

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Réinitialiser l’id de la conférence** dans la liste déroulante.

2. Dans la fenêtre **Réinitialiser l’id de la conférence** , cliquez sur **Ok**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les e-mails sont envoyés aux utilisateurs, mais cela peut être désactivée.   

Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
    
1. Dans le **Skype pour Business admin center**, cliquez sur **les conférences Audio** > **les utilisateurs**, sélectionnez un utilisateur, puis cliquez sur **Réinitialiser**dans le volet Actions, sous **ID de conférence** .
    
2. Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les e-mails sont envoyés aux utilisateurs, mais cela peut être désactivée.
    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes. 
  
## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations de la conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence par courrier électronique** de l’utilisateur dans le volet Actions. Le code confidentiel n'est pas envoyé.
    
- Un ID de conférence contient 7 chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype pour Business admin center ou à l’aide de Windows PowerShell.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- L’ID d’un utilisateur pour la conférence audio de conférence sont consultables en bas du volet Office sous **les conférences Audio** lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** .
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser Skype pour outil de travail réunion mise à jour de leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, voir :
    
  - [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Outil de migration de réunions Skype Entreprise Online (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Outil de migration de réunions Skype Entreprise Online (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel d'audioconférence d'un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md)
