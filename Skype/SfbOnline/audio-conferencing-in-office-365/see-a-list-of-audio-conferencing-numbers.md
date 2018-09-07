---
title: Voir la liste des numéros d’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment rechercher vos numéros d’appel de conférence depuis Skype Entreprise Online. '
ms.openlocfilehash: 118b929f16f0c6edf5c512ddc9b94529a34a8860
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861148"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Voir la liste des numéros d’audioconférence dans Skype Entreprise Online

> [!NOTE]
> Pour plus d’informations sur les numéros d’audioconférence dans Microsoft Teams, voir [Afficher la liste des numéros d’audioconférence dans Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Lorsque vous définissez des services d’audioconférence pour les utilisateurs de Skype Entreprise, vous pouvez afficher les numéros de téléphone disponibles pour l’audioconférence. Cette liste comporte tous les numéros de téléphone d’audioconférence disponibles pour votre organisation.
  
 **Vous recherchez les prix ?** Voir [Tarifs pour l’audioconférence](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
> [!IMPORTANT]
> **Il n’existe pas de ressource qui rassemble tous les numéros de connexion pour l’audioconférence.** Si vous voulez voir si des numéros de téléphone d’appel sont disponibles dans votre zone ou votre pays/région, allez dans le **Centre d’administration Skype Entreprise** > **Voix** > **Numéros de téléphone**, cliquez sur **Ajouter** puis sur **Nouveaux numéros de service**. Utilisez les listes **Pays/Région**, **État/Région** et **Ville** pour filtrer votre recherche. De plus, si vous recherchez des numéros de service gratuits, sélectionnez **Gratuits** dans la liste **État/Région**.
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut sera inclus dans les invitations aux réunions Skype Entreprise Online.
  
Vous pouvez consulter [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md) pour modifier le numéro de téléphone d’appel pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone des services d’audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. |||UNTRANSLATED_CONTENT_START|||Go to the **Office 365 admin center** > **Skype for Business**.|||UNTRANSLATED_CONTENT_END|||
    
3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Pont Microsoft**, puis :
    
  - Vous pouvez afficher les numéros de téléphone disponibles pour les audioconférences.
    
  - Vous pouvez afficher l’emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de l’audioconférence.
    
> [!NOTE]
> Vous pouvez aller dans**Audioconférences** > **Utilisateurs** et sélectionner les propriétés de l’utilisateur pour changer le numéro par défaut en sélectionnant un nouveau numéro dans la liste des numéros disponibles dans votre organisation. Voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
