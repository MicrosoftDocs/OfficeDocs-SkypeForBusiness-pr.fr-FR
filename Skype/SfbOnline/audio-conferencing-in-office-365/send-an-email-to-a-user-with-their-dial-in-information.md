---
title: Envoyer un courrier électronique à un utilisateur avec leurs informations de rendez-vous
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
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envoyer à vos utilisateurs un message électronique avec leurs informations de conférence audio.
ms.openlocfilehash: da006b1e63dd36234acf20bb02fdffba2dc70fa2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio

Parfois Skype pour les utilisateurs d’entreprise ou Microsoft Teams deviez vous permet de les envoyer à leurs informations de conférence Audio. Vous pouvez procéder à l’aide la **Skype entreprise centre d’administration** et cliquez sur **Envoyer les informations de conférence par courrier électronique** sous les propriétés d’un utilisateur. Lorsque vous envoyez ce message, il contient toutes les informations de conférence audio, y compris :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L'ID de conférence de l'utilisateur.
    
   
Voici un exemple du courrier électronique qui est envoyé :
  
![Courrier électronique de conférence rendez-vous](../images/audio-conferencing-info.png)
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-send-an-email-with-audio-conferencing-information-to-a-user"></a>![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) Envoyer un message électronique avec les informations de conférence audio à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration Office 365** > **Skype pour les entreprises**, dans la navigation de gauche, cliquez sur **conférence Audio**.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
> [!TIP]
> Vous pouvez également envoyer des e-mails à l’utilisateur avec les paramètres de conférence audio en modifiant les propriétés de l’utilisateur et puis en cliquant sur **audioconférence** > **Envoyer les informations de conférence par courrier électronique**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Il existe plusieurs messages électroniques envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :
    
  - Lorsqu’une licence de **Conférence Audio** est attribuée.
    
  - Lorsque vous réinitialisez manuellement code confidentiel de conférence audio de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsqu’une licence de **Conférence Audio** est supprimée à partir de celles-ci.
    
  - Lorsque le fournisseur de services d’audioconférence pour un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de services d’audioconférence pour un utilisateur est remplacé par Microsoft.
    
- Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :
    
  - Entrez l’adresse de messagerie dans le paramètre SendEmailFromAddress.
    
  - Le paramètre SendEmailOverride la valeur True.
    
  - Entrez le nom complet de messagerie dans le paramètre SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse personnalisée définie. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Pour envoyer un message électronique à l’utilisateur avec leurs informations de conférence audio, exécutez la commande suivante :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
