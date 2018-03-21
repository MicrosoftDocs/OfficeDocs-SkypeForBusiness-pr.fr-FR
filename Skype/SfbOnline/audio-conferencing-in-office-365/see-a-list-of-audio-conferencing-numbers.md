---
title: "Afficher la liste des numéros d’audioconférence"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: 75e1d78581585f5c9ce94b78a19191918827dbbf
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>Afficher la liste des numéros d’audioconférence

Lorsque vous configurez une conférence Audio pour Skype pour les utilisateurs professionnels et Teams de Microsoft, vous pouvez afficher les numéros de téléphone qui sont à leur disposition pour les conférences audio. Cette liste offre tous les numéros de téléphone de conférence audio sont disponibles pour votre organisation.
  
 **La recherche de prix ?** Consultez la [tarification pour les conférences Audio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Il n’existe pas une ressource qui contient une liste de tous les numéros d’appel à distance pour les conférences Audio.** Si vous souhaitez pour voir s’il existe les numéros de téléphone disponibles dans votre région ou votre pays/région, accédez à **Skype pour le centre d’administration Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **nouveau Service Numéros**. Utilisez les listes **Pays/Région**, **État/Région** et **Ville** pour filtrer votre recherche. En outre, si vous recherchez des numéros de service gratuit, sélectionnez **numéro gratuit** à partir de l’état/région **** liste.
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut figureront dans Skype pour les invitations aux réunions d’entreprise et Teams de Microsoft.
  
Vous pouvez voir [le téléphone numéros inclus sur invite](set-the-phone-numbers-included-on-invites.md) à modifier le numéro de téléphone pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **pont de Microsoft**, puis :
    
  - Vous pouvez afficher les numéros de téléphone qui sont disponibles pour la conférence audio.
    
  - Vous pouvez également afficher l’emplacement et les langues principales et secondaires qui seront utilisés par la fonction d’audioconférence automatiquement surveillance.
    
> [!NOTE]
> Vous pouvez accéder à **l’audioconférence** > **utilisateurs** et sélectionnez nombre de propriétés de l’utilisateur de modifier la valeur par défaut en sélectionnant un nouveau numéro dans la liste des numéros disponibles dans votre organisation. Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md). 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
  
