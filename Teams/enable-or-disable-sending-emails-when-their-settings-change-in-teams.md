---
title: Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
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
description: 'Cette section explique comment activer ou désactiver dans Skype l’option d’envoi de courriers électroniques lorsque des paramètres tels que le code confidentiel ou le numéro de conférence par défaut sont modifiés. '
ms.openlocfilehash: 2c082410f7acf000473e001f46587025edd6e9c7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015540"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams

Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour une audioconférence. Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés aux utilisateurs Microsoft Teams. Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.
  
Si vous désactivez l'envoi de courriers électroniques, aucun message d’audioconférence n'est envoyé à vos utilisateurs, dont les messages relatifs à l'activation et la désactivation des utilisateurs pour l’audioconférence, la réinitialisation de leur code confidentiel ou la modification de l'ID de conférence ou du numéro de téléphone de conférence par défaut.
  
Voici un exemple de courrier électronique envoyé aux utilisateurs activés pour l’audioconférence :
  
![Courrier électronique d’audioconférence](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand des messages électroniques sont-ils envoyés à vos utilisateurs ?

- Plusieurs courriers électroniques sont envoyés aux utilisateurs lorsqu'ils sont activés pour l’audioconférence :
    
  - Lorsqu'une licence pour l’**Audioconférence** leur est attribuée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel d’audioconférence de l'utilisateur.
    
  - Lorsque vous réinitialisez manuellement l’ID de conférence de l'utilisateur.
    
  - Lorsque la licence pour l’**Audioconférence** leur est retirée.
    
  - Lorsque le fournisseur d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun** fournisseur.
    
  - Lorsque le fournisseur d’audioconférence d’un utilisateur est remplacé par Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs

Pour activer ou désactiver l’envoi de courriers électroniques aux utilisateurs, vous pouvez utiliser Microsoft Teams ou Windows PowerShell.

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**
1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.

4. Cliquez sur **Enregistrer**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser Windows PowerShell**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres d’audioconférence sont modifiés](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


