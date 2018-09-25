---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment empêcher ou autoriser ou empêcher les appelants anonymes à participer à une réunion depuis le Centre d’administration de Teams. '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014106"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams

Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d'une réunion d'être placés dans la salle d'attente de la réunion car l'organisateur de la réunion Microsoft Teams ne l’a pas encore commencée. 
  
Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est requis pour démarrer une réunion. Vous pouvez configurer il afin que tout le monde peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel démarrer la réunion. Vous pouvez utiliser le centre d’administration pour activer ou désactiver ce paramètre pour un utilisateur unique.
  
Un code confidentiel n’est pas requis pour l’organisateur de la réunion si une personne a démarré la réunion à partir de l’application Microsoft Teams. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel pour les réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Services d’audioconférence** et sont activés pour l’audioconférence. Voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) et [messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Empêcher ou autoriser les appelants anonymes à participer à une réunion

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

1. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**. 

2. Sélectionnez un utilisateur dans la liste et cliquez sur **Modifier** en haut de la page. 

3. En regard de l’option **Audioconférence**, cliquez sur **Modifier**.

4. Dans le volet **Audioconférence**, activez ou désactivez l’option **Unauthenticated callers can be the first person in a meeting** (Les appelants non authentifiés peuvent être la première personne dans une réunion).
    
4. Cliquez sur **Enregistrer**. 

**Utiliser Windows PowerShell**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la section [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
    
- Si l'accès est anonyme ou si la saisie facultative d'un code confidentiel pour commencer une réunion est activée :
    
  - Si la réunion n’a pas commencé (personne n’a encore rejoint la réunion) : un appelant sera invité à indiquer s’il est l’organisateur et, s’il répond oui, il sera invité à saisir son code confidentiel. Une fois qu’il aura saisi son code confidentiel, la réunion commencera et l’utilisateur pourra y participer.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
- Si l'accès est anonyme ou si la saisie facultative d'un code confidentiel pour commencer une réunion est désactivée :
    
  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel. Étant donné que le paramètre de l’organisateur est défini sur désactivé, la réunion démarre et les appelants anonymes participerez à la réunion.
    
  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
