---
title: Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019043"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams

Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions ainsi que les numéros de téléphone utilisable par les appelants à appeler dans une réunion. Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion vous demande de l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.
  
> [!NOTE]
> Si votre fournisseur de conférence est Microsoft, ID de conférence des utilisateurs est définis sur dynamique uniquement par défaut. Malheureusement, il n’existe aucune possibilité de modifier celui-ci statique, comme cela est désormais non prises en charge. ID de conférence est uniquement automatiquement définie pour les utilisateurs Microsoft Teams activés pour une audioconférence. 


## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialiser l'ID de conférence d'un utilisateur

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) À l’aide de Skype les équipes Microsoft Business centre d’administration

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **Modifier**.

3. Sous **Conférence Audio** , cliquez sur **Réinitialiser l’ID de conférence**.

2. Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.   

    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le courrier électronique contient le nouvel ID de conférence, ou les numéros de téléphone par défaut et des instructions pour mettre à jour des réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence dans le message électronique** de l’utilisateur dans la section de **Conférence Audio** . Le code confidentiel n'est pas envoyé.
    
- Contient un ID de conférence 7 chiffres, et vous ne pouvez pas modifier sa longueur.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin-in-teams.md)
