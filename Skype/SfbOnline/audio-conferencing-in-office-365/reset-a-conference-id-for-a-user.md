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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: eb827cff5bdfbc86bf85aab63a8f29165a91f034
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>Réinitialiser l'ID de conférence d'un utilisateur

Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions ainsi que les numéros de téléphone utilisable par les appelants à appeler dans une réunion. Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion vous demande de l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.
  
> [!NOTE]
> Si votre fournisseur de conférence est Microsoft, ID de conférence des utilisateurs est définis sur dynamique uniquement par défaut. Malheureusement, il n’existe aucune possibilité de le modifier dans le Skype pour le centre d’administration Business ou à l’aide de Windows Powershell pour devenir statique, comme cela est désormais non prises en charge.
ID de conférence est définies uniquement automatiquement uniquement pour Skype pour les utilisateurs professionnels et Microsoft Teams activé pour une audioconférence. 
  
## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence pour un utilisateur

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Réinitialiser l’id de conférence** dans la liste déroulante.

2. Dans la fenêtre **Réinitialiser l’id de conférence** , cliquez sur **Ok**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.   

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
    
1. Dans la **Skype entreprise centre d’administration**, cliquez sur **conférence** > **les utilisateurs**, sélectionnez un utilisateur, puis, dans le volet Actions, sous **ID de conférence** , cliquez sur **Réinitialiser**.
    
2. Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.
    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence par courrier électronique** pour l’utilisateur dans le volet Actions. Le code confidentiel n'est pas envoyé.
    
- Contient un ID de conférence 7 chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype entreprise centre d’administration ou à l’aide de Windows PowerShell.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- Lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** , l’ID de conférence pour un utilisateur pour la conférence audio peut être affiché en bas du volet Actions, sous **l’audioconférence** .
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser Skype pour l’outil de réunion Business pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter la Skype pour l’outil de mise à jour de réunion Business, voir :
    
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

[Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md)
