---
title: Démarrer une conférence Audio par téléphone sans code confidentiel dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: f0e65b3ea4ad5c989137307a1c41bc70bc092086
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490554"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Démarrer une conférence Audio par téléphone sans code confidentiel dans Skype pour Business Online

> [!Note]
> Pour plus d’informations sur le démarrage d’une conférence Audio sans code confidentiel dans Microsoft Teams, voir [Démarrer une conférence Audio par téléphone sans code confidentiel dans les équipes Microsoft](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Il peut être frustrant pour les utilisateurs qui se connectent à une réunion à être conservés dans la salle d’attente de la réunion à l’écoute de la musique, car le Skype pour l’organisateur de la réunion n’a pas démarré la réunion. 
  
Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est requis pour démarrer une réunion. Vous pouvez configurer il afin que tout le monde peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel démarrer la réunion. Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.
  
Un code confidentiel n’est pas requis pour l’organisateur de la réunion si une personne a démarré la réunion à partir de la Skype pour l’application de gestion. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel pour les réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Services d’audioconférence** et sont activés pour l’audioconférence. Voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md) et [messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Autorisation ou refus des appelants anonymes à participer à une réunion
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**. 
    
2. Dans la liste, sélectionnez l’utilisateur, dans le volet Actions, cliquez sur **Modifier**. 
    
3. Sur la page de propriétés de l’utilisateur, sous **options de la réunion**, activez ou désactivez Autoriser non authentifié **appelants sont les premiers à une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié rejoint**.
    
4. Cliquez sur **Enregistrer**. 


    
 **Utilisation de Windows Powershell**
  
- Exécutez la commande suivante : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).
    
- Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est activé :
    
  - Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant est invité s’il est l’organisateur ; Si il indique Oui, il vous demandé pour son code confidentiel et après des entrées le code confidentiel, il démarre la réunion et l’utilisateur sera participer à la réunion.
    
  - Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si il est l’organisateur et il serez jamais pour le code confidentiel ; la réunion est déjà démarrée, et l’appelant joint.
    
- Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est désactivée :
    
  - Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel. Étant donné que le paramètre de l’organisateur est défini sur désactivé, la réunion démarre et les appelants anonymes participerez à la réunion.
    
  - Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel, la réunion est déjà démarrée, et l’appelant joint.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
