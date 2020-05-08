---
title: Envoi d’un courrier électronique à un utilisateur avec ses conférences audio dans Skype entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Envoyez à vos utilisateurs un message électronique contenant leurs informations de conférence audio dans Skype entreprise online.
ms.openlocfilehash: f2137d05ebe588a316704fabf4c8878910a40bc0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163896"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Envoi d’un courrier électronique à un utilisateur avec ses informations de conférence audio dans Skype entreprise Online

> [!Note]
> Pour plus d’informations sur l’envoi d’informations sur l’audioconférence aux utilisateurs de Microsoft Teams, voir [Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio dans Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Les utilisateurs de Skype entreprise peuvent parfois avoir besoin de leur envoyer leurs informations de conférence audio. Pour cela, vous pouvez utiliser le **Centre d’administration Skype entreprise** et cliquer sur **Envoyer les informations sur la Conférence par courrier électronique** sous les propriétés d’un utilisateur. Lorsque vous envoyez ce message électronique, celui-ci contient toutes les informations sur les conférences audio, notamment :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L'ID de conférence de l'utilisateur.
    
   
Voici un exemple du courrier électronique envoyé :
  
![Courrier électronique de conférence rendez-vous](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **audioconférence**, cliquez sur **Envoyer les informations sur la Conférence par courrier électronique**.

1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Accédez au centre d’administration > **Skype entreprise**, puis, dans le volet de navigation de gauche, cliquez sur **audioconférence**.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
> [!TIP]
> Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres de l’audioconférence en modifiant les propriétés de l’utilisateur, puis en cliquant sur **audioconférence** > **Envoyer les informations sur la Conférence par courrier électronique**. 

## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation après leur activation pour l’audioconférence :
    
  - Lorsqu’une licence de **conférence audio** leur est affectée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lors de la suppression d’une licence de **conférence audio** .
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est passé de Microsoft à un autre fournisseur ou à **aucun**.
    
  - Lorsque Microsoft devient le fournisseur de services d’audioconférence pour un utilisateur.
    
- Par défaut, l’expéditeur des messages électroniques provient de Microsoft 365 ou d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de l’applet [de passe Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Pour modifier l’adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez :
    
  - Entrez l’adresse de messagerie dans le paramètre À sendemailfromaddress ;.
    
  - Définissez le paramètre SendEmailOverride à True.
    
  - Entrez le nom d’affichage du courrier électronique dans le paramètre SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse personnalisée définie. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Pour envoyer à l’utilisateur un message électronique contenant ses informations de conférence audio, exécutez la commande suivante :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Voir aussi

[Essayez ou achetez une audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
