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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envoyez à vos utilisateurs un courrier électronique qui contient leurs informations d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 9e4508f3907de35ee2752077ac22b5cd8a5e5735
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571314"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams

Parfois, les utilisateurs de Microsoft Teams peuvent avoir besoin que vous leur envoyiez leurs informations d’audioconférence. Vous pouvez le faire en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** sous les propriétés d'un utilisateur. Le courrier électronique que vous envoyez contiendra toutes les informations d’audioconférence, dont :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L’ID de conférence de l’utilisateur.
    
   
Voici un exemple de courrier électronique envoyé :
  
![Exemple de message électronique de conférence rendez-vous](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer à un utilisateur un courrier électronique qui contient les informations d’audioconférence

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **audioconférence**, cliquez sur **Envoyer les informations sur la Conférence par courrier électronique**.


## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation après leur activation pour l’audioconférence :
    
  - Lorsqu’une licence de **conférence audio** leur est affectée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lors de la suppression d’une licence de **conférence audio** .
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est passé de Microsoft à un autre fournisseur ou à **aucun**.
    
  - Lorsque Microsoft devient le fournisseur de services d’audioconférence pour un utilisateur.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
