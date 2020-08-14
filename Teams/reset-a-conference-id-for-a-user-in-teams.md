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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662124"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams

Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions avec les numéros de téléphone qui peuvent être utilisés par les appelants pour accéder à une réunion. Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion lui demande de saisir cet ID de conférence pour pouvoir assister à la réunion.
  
> [!NOTE]
> Les ID de conférence sont générés automatiquement, vont de 7-9 chiffres et sont définis lorsque vous activez l’audioconférence pour un utilisateur. **Les ID de conférence statiques ne sont pas pris en charge.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence d’un utilisateur

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.

2. Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur. Des courriers électroniques sont envoyés aux utilisateurs par défaut, mais cette option peut être désactivée.   

    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un courrier électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message est envoyé à l’adresse de messagerie principale, dans de nombreux cas, la boîte aux lettres Microsoft 365 ou Office 365. Le courrier électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions de mise à jour des réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations sur les conférences à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** pour l’utilisateur dans la section **Audioconférence**. Ce courrier ne contient pas le code confidentiel.
    
- Un ID de conférence à 7-9 chiffres est créé par le service Teams. Vous ne pouvez pas modifier sa longueur.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md)
