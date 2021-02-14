---
title: Options de messagerie électronique en cas de modification des paramètres d’audioconférence
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Cette section explique comment activer ou désactiver dans Skype l’option d’envoi de courriers électroniques lorsque des paramètres tels que le code confidentiel ou le numéro de conférence par défaut sont modifiés. '
ms.openlocfilehash: 36c7e9dce17de1e6f9bbf8b812d62ddd91bc6ffe
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691600"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams

Lorsque l’audioconférence est activée pour eux, les utilisateurs sont avertis automatiquement par e-mail. Il peut arriver que vous souhaitiez réduire le nombre de courriers électroniques envoyés aux utilisateurs de Microsoft Teams. Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.
  
Si vous désactivez l'envoi de courriers électroniques, aucun message d’audioconférence n'est envoyé à vos utilisateurs, dont les messages relatifs à l'activation et la désactivation des utilisateurs pour l’audioconférence, la réinitialisation de leur code confidentiel ou la modification de l'ID de conférence ou du numéro de téléphone de conférence par défaut.
  
Voici un exemple de courrier électronique envoyé aux utilisateurs activés pour l’audioconférence :
  
![Exemple de message électronique d’audioconférence](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
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

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.

4. Cliquez sur **Enregistrer**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser Windows PowerShell**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell vous permet de gérer les utilisateurs et ce qu’ils sont autorisés ou non à faire. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à Windows PowerShell, consultez les rubriques ci-après :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres d’audioconférence sont modifiés](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


