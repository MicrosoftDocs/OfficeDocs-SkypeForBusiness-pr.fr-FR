---
title: Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
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
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887851"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams

Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions avec les numéros de téléphone qui peuvent être utilisés par les appelants pour accéder à une réunion. Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion lui demande de saisir cet ID de conférence pour pouvoir assister à la réunion.
  
> [!NOTE]
> Si votre fournisseur de service de conférence est Microsoft, les ID de conférence de vos utilisateurs sont définis par défaut sur Dynamique uniquement. Il n’est malheureusement pas possible de définir des ID statiques, car cette option n’est pas prise en charge actuellement. Les ID de conférence sont définis automatiquement uniquement pour les utilisateurs de Microsoft Teams activés pour l’audioconférence. 


## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialiser l'ID de conférence d'un utilisateur

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.

2. Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur. Des courriers électroniques sont envoyés aux utilisateurs par défaut, mais cette option peut être désactivée.   

    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un courrier électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce courrier électronique est envoyé à son adresse électronique principale, généralement sa boîte aux lettres Office 365. Le courrier électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions de mise à jour des réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations sur les conférences à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** pour l’utilisateur dans la section **Audioconférence**. Ce courrier ne contient pas le code confidentiel.
    
- Un ID de conférence contient 7 chiffres, et vous ne pouvez pas modifier sa longueur.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID sous **ID de conférence**.
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md)
