---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Découvrez comment activer ou désactiver la possibilité pour des appelants anonymes de se joindre aux réunions dans le centre d’administration Skype entreprise ou à l’aide d’un script PowerShell. '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858704"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Démarrer une audioconférence par téléphone sans code confidentiel dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur le démarrage d’une audioconférence sans code confidentiel dans Microsoft Teams, voir [Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d'une réunion d'être placés en file d'attente de la réunion, car l'organisateur de la réunion Skype Entreprise n'a pas encore lancé l'événement. 
  
L'organisateur doit appeler la réunion et un code confidentiel lui est demandé par défaut pour que la réunion puisse commencer. Vous pouvez modifier ce paramètre pour que n'importe qui puisse composer le numéro de téléphone de la réunion et la commence sans avoir à composer de code confidentiel. Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.
  
Un code confidentiel n'est pas nécessaire pour l'organisateur de la réunion si quelqu'un a commencé la réunion à partir de l'application Skype Entreprise. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion rejoint sa réunion par téléphone. Le code confidentiel des réunions est envoyé aux utilisateurs audio qui possèdent une **licence de réunion audio** ou pour lesquels la fonction d'audioconférence est activée. Reportez-vous aux rubriques[Envoyer un message électronique à un utilisateur avec leurs informations d'audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) et[Courriers électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs paramètres d'audioconférence](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Autorisation ou refus des appelants anonymes à participer à une réunion
    
1. Dans le **centre d'administration Skype Entreprise**, au sein du menu de navigation de gauche, accédez à **Audioconférence** > **Utilisateurs** . 
    
2. Dans la liste, sélectionnez l'utilisateur et, dans le volet Action, cliquez sur **Modifier**. 
    
3. Dans la page Propriétés de l'utilisateur, sous **Options de réunion**, activez ou désactivez la case à cocher **Autoriser les appelants non authentifiés à être les premiers participants d'une réunion. Si ce n'est pas le cas, ils se trouveront en file d'attente jusqu'à ce qu'un utilisateur authentifié participe**.
    
4. Cliquez sur **Enregistrer**. 


    
 **Utilisation de Windows PowerShell**
  
- Exécutez la commande suivante : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la rubrique [Réinitialiser le code confidentiel d'audioconférence pour un utilisateur](reset-the-audio-conferencing-pin.md).
    
- Si l'accès anonyme, ou la saisie facultative d'un code confidentiel pour le début d'une réunion, est activé :
    
  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : un appelant est invité s’il est l’organisateur ; s'il indique Oui, il lui est demandé de saisir son code confidentiel et une fois le code confidentiel saisi, la réunion sera démarrée et l’utilisateur y participera.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
- Si l'accès anonyme, ou la saisie facultative d'un code confidentiel pour le début d'une réunion, est désactivée :
    
  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel. Étant donné que le paramétrage de l'organisateur est défini sur Désactivé, la réunion commence et les appelants anonymes peuvent participer à la réunion.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs façons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous faites des modifications de paramètres pour beaucoup d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
