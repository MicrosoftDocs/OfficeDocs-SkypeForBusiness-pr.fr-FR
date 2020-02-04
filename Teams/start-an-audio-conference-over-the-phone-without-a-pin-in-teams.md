---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment empêcher ou autoriser ou empêcher les appelants anonymes à participer à une réunion depuis le Centre d’administration de Teams. '
ms.openlocfilehash: c971b73aade62c0ef9e34c0467a956477e80ca7c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707559"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams

Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d'une réunion d'être placés dans la salle d'attente de la réunion car l'organisateur de la réunion Microsoft Teams ne l’a pas encore commencée. 
  
Si l'organisateur d’une réunion appelle la réunion, un code confidentiel lui est demandé par défaut pour que la réunion puisse commencer. Vous pouvez modifier ce paramètre pour que n'importe qui puisse composer le numéro de téléphone de la réunion et y puisse y participer sans avoir à composer de code confidentiel. Le Centre d'administration permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.
  
Un code confidentiel n'est pas nécessaire pour l'organisateur de la réunion si quelqu'un a commencé la réunion à partir de l’application Microsoft Teams. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel des réunions est envoyé aux utilisateurs téléphoniques qui possèdent une licence pour l’**Audioconférence** ou pour lesquels la fonction d’audioconférence est activée. Reportez-vous aux sections [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) et [Courriers électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Empêcher ou autoriser les appelants anonymes à participer à une réunion

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**. 

2. Sélectionnez un utilisateur dans la liste et cliquez sur **Modifier** en haut de la page. 

3. En regard de l’option **Audioconférence**, cliquez sur **Modifier**.

4. Dans le volet **audioconférence Conferencing** , vous pouvez activer ou désactiver **les appelants**rendez-vous dans une réunion.
    
4. Cliquez sur **Appliquer**. 

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la section [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
    
- Si l’accès anonyme ou ne nécessite pas un code confidentiel pour démarrer une réunion, est désactivé :
    
  - Si la réunion n’a pas commencé (personne n’a encore rejoint la réunion) : un appelant sera invité à indiquer s’il est l’organisateur et, s’il répond oui, il sera invité à saisir son code confidentiel. Une fois qu’il aura saisi son code confidentiel, la réunion commencera et l’utilisateur pourra y participer.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
- Si vous avez accès anonyme ou si vous n’avez pas besoin d’un code confidentiel pour démarrer une réunion, est activé :
    
  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel. Étant donné que le paramètre de l'organisateur est défini sur Désactivé, la réunion commence et les appelants anonymes peuvent y participer.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
