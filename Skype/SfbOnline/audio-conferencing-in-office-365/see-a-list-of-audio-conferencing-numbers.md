---
title: Voir la liste des numéros de conférence Audio
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: bccd4a5c02dbb6bc32c27e315b80a39705284429
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>Voir la liste des numéros de conférence Audio

Lorsque vous définissez des services d’audioconférence pour Skype pour les utilisateurs professionnels et Teams Microsoft, vous pouvez afficher les numéros de téléphone qui sont disponibles pour l’audioconférence. Cette liste auront tous les numéros de téléphone de conférence audio sont disponibles pour votre organisation.
  
 **Vous recherchez des prix ?** Consultez [tarification pour l’audioconférence](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Il n’est pas une ressource qui contient une liste de tous les numéros de téléphone pour une audioconférence.** Si vous souhaitez pour voir s’il existe des numéros de téléphone entrant dans votre région ou le pays/région, accédez à **Skype pour le centre d’administration de Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **nouveau Service Numéros**. Utilisez les listes **Pays/Région**, **État/Région** et **Ville** pour filtrer votre recherche. En outre, si vous recherchez des numéros gratuits service, sélectionnez **numéro gratuit** à partir de **Dép./région** liste.
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut vont être inclus dans Skype pour des invitations aux réunions d’entreprise et Teams Microsoft.
  
Vous pouvez voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md) pour modifier le numéro de téléphone pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone des services d’audioconférence

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, accédez à des **réunions** > **ponts de conférence**. 
2.  Afficher les numéros de téléphone qui sont disponibles pour l’audioconférence.

- Vous pouvez également afficher l’emplacement et la langue principale qui sera utilisé par le standard automatique de conférence audio.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

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
  
