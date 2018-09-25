---
title: Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012320"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams

Parfois les utilisateurs Microsoft Teams deviez vous permet de les envoyer à leurs informations de conférence Audio. Vous pouvez procéder en cliquant sur **Envoyer les informations de conférence par courrier électronique** sous les propriétés d’un utilisateur. Lorsque vous envoyez ce message, il contient toutes les informations de conférence audio, y compris :
  
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
    
- Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell. Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
