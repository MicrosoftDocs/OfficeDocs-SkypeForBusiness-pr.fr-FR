---
title: Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envoyez à vos utilisateurs un courrier électronique qui contient leurs informations d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892091"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams

Parfois, les utilisateurs de Microsoft Teams peuvent avoir besoin que vous leur envoyiez leurs informations d’audioconférence. Vous pouvez le faire en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** sous les propriétés d'un utilisateur. Le courrier électronique que vous envoyez contiendra toutes les informations d’audioconférence, dont :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L’ID de conférence de l’utilisateur.
    
   
Voici un exemple de courrier électronique envoyé :
  
![Courrier électronique de conférence rendez-vous](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer à un utilisateur un courrier électronique qui contient les informations d’audioconférence

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Envoyer les informations de la conférence dans un courrier électronique**.


## <a name="what-else-should-you-know-about-this-email"></a>Informations supplémentaires sur ce courrier électronique

- Plusieurs courriers électroniques sont envoyés aux utilisateurs lorsqu'ils sont activés pour l’audioconférence :
    
  - Lorsqu'une licence pour l’**Audioconférence** leur est attribuée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel d’audioconférence de l'utilisateur.
    
  - Lorsque vous réinitialisez manuellement l’ID de conférence de l'utilisateur.
    
  - Lorsqu'une licence pour l’**Audioconférence** leur est retirée.
    
  - Lorsque le fournisseur d’audioconférence passe de Microsoft à un autre fournisseur ou à **Aucun** fournisseur.
    
  - Lorsque le fournisseur d’audioconférence d’un utilisateur est remplacé par Microsoft.
    
- Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell. Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
