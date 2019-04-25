---
title: Voir la liste des utilisateurs activés pour une audioconférence dans Skype pour Business Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: 722f9e411e1781529ea68f6995a2109f58d39cb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229260"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Voir la liste des utilisateurs activés pour une audioconférence dans Skype pour Business Online

> [!NOTE]
> Pour plus d’informations sur les utilisateurs actifs dans Microsoft Teams, voir [Afficher la liste des utilisateurs qui sont activées pour une audioconférence dans les équipes Microsoft](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Une fois que vous avez activé Skype pour les utilisateurs professionnels de votre organisation pour une audioconférence, vous pouvez afficher la liste des utilisateurs qui ont été activés. Lorsque vous examinez la liste, vous verrez également pour chaque utilisateur dans la liste le type de fournisseur de conférence audio qu’ils utilisent le numéro de téléphone de rendez-vous par défaut pour l’utilisateur, et si votre organisation n’est pas activée pour l’ID de conférence dynamique, l’ID de conférence statique pour les réunions de conférence audio qu’ils organisent.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Afficher une liste d'utilisateurs

   
- Dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**.

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Lorsque vous affichez la liste des utilisateurs sont activés, vous pouvez sélectionner un utilisateur dans la liste et le volet d’actions permet de modifier les paramètres de conférence audio pour cet utilisateur.
    
- Lorsque vous sélectionnez un utilisateur unique est configuré pour utiliser Microsoft comme fournisseur de services d’audioconférence, vous pouvez afficher le numéro de téléphone par défaut et si votre organisation est activée pour l’ID de conférence dynamique et vous pouvez réinitialiser l’ID de conférence pour les réunions qui le organise les utilisateurs.
    
- Lorsque vous sélectionnez un utilisateur unique qui est configuré pour utiliser un fournisseur de services d’audioconférence tiers, vous pouvez afficher le nom du fournisseur de services d’audioconférence, le numéro de téléphone et le numéro de téléphone gratuit (si elles sont configurées).
    
- Vous pouvez utiliser les options de filtre pour afficher les utilisateurs :
    
  - **Services d’audioconférence sur**
    
  - **Services d’audioconférence désactivé**
    
  - **Fournisseur de services de conférence - Microsoft**
    
  - **Fournisseur de services de conférence - Autres**
    
- Vous pouvez utiliser le bouton Rechercher pour rechercher un utilisateur dans la liste.
    
- Vous pouvez sélectionner plusieurs utilisateurs et effectuer les opérations suivantes :
    
  - Sélectionnez un autre numéro par défaut pour ces utilisateurs.
    
  - Désactiver les services d’audioconférence pour l’utilisateur en modifiant le fournisseur sur **None**.
    
  - Si l’utilisateur a été attribué une licence de **Services d’audioconférence** , basculez vers Microsoft en tant que le fournisseur de services d’audioconférence.
    
  - Autorisez les utilisateurs anonymes à activer les réunions téléphoniques d'utilisateurs sélectionnés ou interdisez-leur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
