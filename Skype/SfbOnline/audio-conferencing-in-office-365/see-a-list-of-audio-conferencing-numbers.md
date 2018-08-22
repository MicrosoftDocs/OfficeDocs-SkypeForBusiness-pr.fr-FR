---
title: Voir la liste des numéros d’audioconférence dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Découvrez comment rechercher vos numéros de conférence rendez-vous à partir de Skype pour Business Online. '
ms.openlocfilehash: 84d6f4d1d1d1358a62ec8d0eb2334c92c416adea
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490594"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Voir la liste des numéros d’audioconférence dans Skype pour Business Online

> [!NOTE]
> Pour plus d’informations sur les numéros de conférence Audio dans Microsoft Teams, voir [Afficher la liste des numéros de conférence Audio dans les équipes Microsoft](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Lorsque vous définissez des services d’audioconférence pour Skype pour les utilisateurs professionnels, vous pouvez afficher les numéros de téléphone qui sont disponibles pour l’audioconférence. Cette liste auront tous les numéros de téléphone de conférence audio sont disponibles pour votre organisation.
  
 **Vous recherchez des prix ?** Consultez [tarification pour l’audioconférence](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Il n'existe pas de ressource qui rassemble tous les numéros de connexion pour l'audioconférence.** Si vous souhaitez pour voir s’il existe des numéros de téléphone entrant dans votre région ou le pays/région, accédez à **Skype pour le centre d’administration de Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **nouveau Service Numéros**. Utilisez les listes **Pays/Région**, **État/Région** et **Ville** pour filtrer votre recherche. En outre, si vous recherchez des numéros gratuits service, sélectionnez **numéro gratuit** à partir de **Dép./région** liste.
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut figurera dans Skype pour les invitations à une réunion Business.
  
Vous pouvez voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md) pour modifier le numéro de téléphone pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone des services d’audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **Microsoft bridge**, puis :
    
  - Vous pouvez afficher les numéros de téléphone qui sont disponibles pour l’audioconférence.
    
  - Vous pouvez également afficher l’emplacement et les langues principales et secondaires qui seront utilisés par les services d’audioconférence standard automatiquement.
    
> [!NOTE]
> Vous pouvez passer à la **conférence Audio** > **utilisateurs** et sélectionnez nombre de propriétés de l’utilisateur à modifier la valeur par défaut en sélectionnant un nouveau numéro dans la liste des numéros disponibles dans votre organisation. Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
