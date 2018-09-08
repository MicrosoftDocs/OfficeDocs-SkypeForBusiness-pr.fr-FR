---
title: Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment activer ou désactiver Skype d’envoyer des messages électroniques aux utilisateurs lorsque les paramètres tels que du code confidentiel change ou les modifications de numéro de conférence par défaut dans Microsoft Teams. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892501"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Microsoft Teams

Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour une audioconférence. Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés aux utilisateurs Microsoft Teams. Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.
  
Si vous désactivez envoi de courriers électroniques, messages électroniques de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris pour les messages électroniques lorsque les utilisateurs sont activés ou désactivés pour l’audioconférence, leur code confidentiel est réinitialisé et modifications numéros de téléphone de l’ID de conférence et la conférence par défaut .
  
Voici un exemple du courrier électronique qui est envoyé aux utilisateurs lorsqu’ils sont activés pour une audioconférence :
  
![Conférence audio par courrier électronique](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Il existe plusieurs messages électroniques envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :
    
  - Lorsqu’une licence de **Conférence Audio** est attribuée.
    
  - Lorsque vous réinitialisez manuellement code confidentiel de conférence audio de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la licence de **Conférence Audio** est supprimée à partir de celles-ci.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est remplacé par Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver la messagerie d’être envoyés aux utilisateurs

Vous pouvez utiliser Microsoft Teams ou Windows PowerShell pour activer ou désactiver le courrier envoyé aux utilisateurs.

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**
1. Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**. 

2. En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres de connexion à modifient**.

4. Cliquez sur **Enregistrer**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utilisation de Windows PowerShell**
  
Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.

    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
    
  
## <a name="related-topics"></a>Rubriques connexes

[Messages électroniques envoyés aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


