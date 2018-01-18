---
title: "Afficher la liste des numéros d’audioconférence"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Découvrez comment rechercher vos numéros de conférence à distance à partir de Skype pour les entreprises. "
ms.openlocfilehash: 45e4dd113845c9c565162c4ef3047df83e1aeb43
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>Afficher la liste des numéros d’audioconférence

Lorsque vous configurez une conférence Audio pour Skype pour les utilisateurs professionnels et Teams de Microsoft, vous pouvez afficher les numéros de téléphone qui sont à leur disposition pour les conférences audio. Cette liste offre tous les numéros de téléphone de conférence audio sont disponibles pour votre organisation.
  
 **La recherche de prix ?** Consultez la [tarification pour les conférences Audio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Il n’existe pas une ressource qui contient une liste de tous les numéros d’appel à distance pour les conférences Audio.** Si vous souhaitez pour voir s’il existe les numéros de téléphone disponibles dans votre région ou votre pays/région, accédez à **Skype pour le centre d’administration Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **nouveau Service Numéros**. Utilisez les listes de **Pays/région**, état/région de ****et **Ville** pour filtrer votre recherche. En outre, si vous recherchez des numéros de service gratuit, sélectionnez **numéro gratuit** à partir de l’état/région **** liste.
  
Si uniquement un numéro de téléphone est disponible dans votre organisation, il sera utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut figureront dans Skype pour les invitations aux réunions d’entreprise et Teams de Microsoft.
  
Vous pouvez voir [le téléphone numéros inclus sur invite](set-the-phone-numbers-included-on-invites.md) à modifier le numéro de téléphone pour un seul utilisateur.
  
> [!NOTE]
> Numéros d’accès nationaux sont dédiées à votre entreprise et sont les seules qui peuvent être définies sous la forme d’un numéro de téléphone par défaut. Toutefois, les numéros d’accès internationales peuvent être partagés par plusieurs organisations. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **pont de Microsoft**, puis :
    
  - Vous pouvez afficher les numéros de téléphone qui sont disponibles pour la conférence audio.
    
  - Vous pouvez également afficher l’emplacement et les langues principales et secondaires qui seront utilisés par la fonction d’audioconférence automatiquement surveillance.
    
> [!NOTE]
> Vous pouvez accéder à **l’audioconférence** > **utilisateurs** et sélectionnez nombre de propriétés de l’utilisateur de modifier la valeur par défaut en sélectionnant un nouveau numéro dans la liste des numéros disponibles dans votre organisation. Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md). 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) .
    
- Windows PowerShell est la gestion des utilisateurs et les utilisateurs qui sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams](set-up-audio-conferencing.md)
  

