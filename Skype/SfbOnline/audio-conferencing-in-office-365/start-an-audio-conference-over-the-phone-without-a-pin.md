---
title: Démarrer une conférence Audio par téléphone sans code confidentiel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 7c6f0e70780b04e75be52ead1eaf08602bcba003
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>Démarrer une conférence Audio par téléphone sans code confidentiel

Il peut être frustrant pour les utilisateurs qui se connectent à une réunion qui se tiendra dans la salle d’attente de la réunion à l’écoute de musique car le Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft n’a pas démarré la réunion. 
  
Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est nécessaire pour démarrer une réunion. Vous pouvez configurer afin que toute personne peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel pour démarrer la réunion. Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.
  
Un code confidentiel n’est pas obligatoire pour l’organisateur de la réunion si quelqu'un a démarré la réunion à partir d’un Skype pour application métier ou Teams de Microsoft. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel de réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Conférence Audio** et sont activées pour la conférence Audio. Reportez-vous à la section [Envoyer un courrier électronique à un utilisateur avec les informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) et dans les [courriels qui sont automatiquement envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Autorisation ou refus des appelants anonymes à participer à une réunion

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**. 

2. Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** en haut de la page. 

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier**.

4. Dans le volet de **fournisseur de pont de conférence** , activer ou désactiver les appelants d’autoriser non authentifié **pour être les premiers dans une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié de jointures**.
    
4. Cliquez sur **Appliquer**. 

Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
    
1. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**. 
    
2. Dans la liste, sélectionnez l’utilisateur et dans le volet Actions, cliquez sur **Modifier**. 
    
3. Sur la page de propriétés de l’utilisateur, sous **options de la réunion**, activez ou désactivez les appelants d’autoriser non authentifié **pour être les premiers dans une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié de jointures**.
    
4. Cliquez sur **Enregistrer**. 
    
 **Utilisation de Windows Powershell**
  
- Exécutez la commande suivante : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la rubrique [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Si l’accès anonyme, ou un code confidentiel démarrer une réunion, ne nécessitant ne pas est activé :
    
  - Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant demandera s’il est l’organisateur ; Si il répond Oui, il serez invité pour son code confidentiel et une fois qu’il le code PIN est une entrée, la réunion démarre et l’utilisateur doit joindre la réunion.
    
  - Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : un appelant ne sera pas invité si il est l’organisateur et il serez jamais de code confidentiel ; la réunion est déjà démarrée, et l’appelant joint.
    
- Si l’accès anonyme, ou un code confidentiel démarrer une réunion, ne nécessitant ne pas est désactivé :
    
  - Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant ne sera pas invité si elle en est l’organisateur et elle demandera jamais de code confidentiel. Étant donné que le paramètre de l’organisateur est défini sur off, la réunion démarre et les appelants anonymes seront joindre à la réunion.
    
  - Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : un appelant ne sera pas invité si elle en est l’organisateur et elle demandera jamais le PIN, la réunion a déjà démarrée, et l’appelant joint.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Les meilleures façons de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
