---
title: Consulter la liste des utilisateurs activés pour l’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: 206bd52d1b2e0cfc1a72bb557c5d5dc4c0162534
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163923"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Consulter la liste des utilisateurs activés pour l’audioconférence dans Skype Entreprise Online

> [!NOTE]
> Pour plus d’informations sur les utilisateurs activés dans Microsoft Teams, consultez la liste des utilisateurs activés pour [l’audioconférence dans Microsoft Teams.](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

Une fois que vous avez activé l’audioconférence pour les utilisateurs de Skype Entreprise dans votre organisation, vous pouvez afficher la liste de ces utilisateurs. Lorsque vous consultez la liste, vous voyez également pour chaque utilisateur le type de fournisseur de services d’audioconférence qu’il utilise, le numéro de téléphone à composer par défaut, et si votre organisation n’est pas activée pour les ID de conférence dynamiques, les ID de conférence statiques pour les réunions d’audioconférence qu’il organise.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Afficher une liste d'utilisateurs

   
- Dans le groupe de navigation de gauche, allez à Utilisateurs de **l’audioconférence.**  >  

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Lorsque vous affichez la liste des utilisateurs activés, vous pouvez sélectionner un utilisateur dans la liste et utiliser le volet Action pour modifier les paramètres d’audioconférence de cet utilisateur.
    
- Lorsque vous sélectionnez un utilisateur unique configuré pour utiliser Microsoft comme fournisseur de services d’audioconférence, vous pouvez afficher le numéro de téléphone par défaut et déterminer si votre organisation est activée pour les ID de conférence dynamiques, et vous pouvez réinitialiser l’ID de conférence pour les réunions que l’utilisateur organise.
    
- Lorsque vous sélectionnez un utilisateur unique configuré pour utiliser un fournisseur de services d’audioconférence tiers, vous pouvez afficher le nom du fournisseur de services d’audioconférence, le numéro de téléphone gratuit et le numéro de téléphone gratuit (s’il est configuré).
    
- Vous pouvez utiliser les options de filtre pour afficher les utilisateurs :
    
  - **Audioconférence sur**
    
  - **Audioconférences off**
    
  - **Fournisseur de services de conférence - Microsoft**
    
  - **Fournisseur de services de conférence - Autres**
    
- Vous pouvez utiliser le bouton Rechercher pour rechercher un utilisateur dans la liste.
    
- Vous pouvez sélectionner plusieurs utilisateurs et effectuer les opérations suivantes :
    
  - Sélectionnez un autre numéro par défaut pour ces utilisateurs.
    
  - Pour désactiver l’audioconférence pour l’utilisateur, modifiez le fournisseur en **Fournisseur Aucune.**
    
  - Basculez vers Microsoft comme fournisseur de services d’audioconférence si une licence **d’audioconférence** a été affectée à l’utilisateur.
    
  - Autorisez les utilisateurs anonymes à activer les réunions téléphoniques d'utilisateurs sélectionnés ou interdisez-leur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Sujets associés

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
