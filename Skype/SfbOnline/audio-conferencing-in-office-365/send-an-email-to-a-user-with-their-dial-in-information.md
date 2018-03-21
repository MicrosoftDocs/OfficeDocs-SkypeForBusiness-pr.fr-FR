---
title: "Envoyer un e-mail à un utilisateur avec les informations d’accès à distance"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Envoyer à vos utilisateurs un message électronique avec leurs informations de conférence audio."
ms.openlocfilehash: 7ca0a4f00f3a81cd865d65336a8be5702e620639
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio

Skype pour les utilisateurs professionnels ou Teams de Microsoft peut parfois besoin de vous pour leur envoyer leurs informations d’audioconférence. Pour cela, à l’aide de la **Skype pour le centre d’administration Business** et cliquer sur **Envoyer les informations de conférence par courrier électronique** dans les propriétés d’un utilisateur. Lors de l’envoi de cet e-mail, il contient toutes les informations de conférence audio, y compris :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L'ID de conférence de l'utilisateur.
    
    > [!NOTE]
    > ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser. Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique. Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [Cliquez ici](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Voici un exemple de l’e-mail envoyé :
  
![Courrier électronique de conférence rendez-vous](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un e-mail contenant des informations sur la conférence audio à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Office 365** > **Skype pour les entreprises**et de la navigation de gauche, cliquez sur **audioconférence**.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
> [!TIP]
> Vous pouvez également envoyer des e-mail à l’utilisateur avec les paramètres de conférence audio, modification des propriétés de l’utilisateur puis cliquez sur **audioconférence** > **Envoyer par courrier électronique, les informations de conférence**. 
  
## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Il existe plusieurs messages électroniques qui sont envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :
    
  - Lorsqu’une licence **Audioconférence** est attribuée.
    
  - Lorsque vous effectuez manuellement la conférence code PIN de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque une licence **Audioconférence** est supprimée à partir de ceux-ci.
    
  - Lorsque le fournisseur de conférence audio pour un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de conférence audio pour un utilisateur est modifié à Microsoft.
    
- Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :
    
  - Entrez l’adresse e-mail dans le paramètre SendEmailFromAddress.
    
  - Définissez le paramètre SendEmailOverride sur True.
    
  - Entrez le nom complet de courrier électronique dans le paramètre SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse personnalisée définie. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Pour envoyer un e-mail à l’utilisateur avec leurs informations de conférence audio, exécutez la commande suivante :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
