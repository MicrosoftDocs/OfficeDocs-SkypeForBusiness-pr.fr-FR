---
title: Envoyer un courrier électronique à un utilisateur avec son audioconférence dans Skype Entreprise Online
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
description: Envoyez à vos utilisateurs un courrier électronique avec leurs informations d’audioconférence dans Skype Entreprise Online.
ms.openlocfilehash: f070353069c937a62935e1cc570ebae6c0e981db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109991"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Envoyer un courrier électronique à un utilisateur avec ses informations d’audioconférence dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur l’envoi d’informations sur l’audioconférence à des utilisateurs dans Microsoft Teams, consultez l’occasion d’envoyer un courrier électronique à un utilisateur avec ses informations d’audioconférence dans [Les thés Microsoft.](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)

Parfois, les utilisateurs de Skype Entreprise peuvent avoir besoin que vous leur envoyiez leurs informations d’audioconférence. Pour ce faire, utilisez le Centre d’administration **Skype** Entreprise et cliquez sur Envoyer les informations sur la conférence **par** courrier électronique sous les propriétés d’un utilisateur. Lorsque vous envoyez ce message électronique, il contient toutes les informations sur l’audioconférence, notamment :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L'ID de conférence de l'utilisateur.
    
   
Voici un exemple du message électronique envoyé :
  
![Courrier électronique de conférence rendez-vous](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courrier électronique avec des informations d’audioconférence à un utilisateur

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence,** cliquez sur Envoyer les informations sur **la conférence par courrier électronique.**

1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Dans le panneau de > **de Skype** Entreprise, dans le panneau de navigation de gauche, cliquez sur **Audioconférence.**
    
3. Cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
> [!TIP]
> Vous pouvez également envoyer un courrier électronique à l’utilisateur avec les paramètres de conférence audio en modifier les propriétés, puis en cliquant sur Audioconférence Envoyer les informations sur la conférence  >  **par courrier électronique.** 

## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Après avoir activé l’audioconférence, plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation :
    
  - **Lorsqu’une licence d’audioconférence** leur est affectée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel de l’utilisateur pour l’audioconférence.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - **Lorsqu’une licence d’audioconférence** leur est supprimée.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun.**
    
  - Lorsque Microsoft est le fournisseur de services d’audioconférence d’un utilisateur.
    
- Par défaut, l’expéditeur des courriers électroniques est Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide d’Windows PowerShell et de la [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier aux utilisateurs, vous devez :
    
  - Entrez l’adresse de courrier dans le paramètre SendEmailFromAddress.
    
  - Définissez le paramètre SendEmailOverride à True.
    
  - Entrez le nom d’affichage de l’e-mail dans le paramètre SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse personnalisée définie. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
    Pour envoyer un courrier électronique à l’utilisateur avec ses informations d’audioconférence, exécutez ce qui suit :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)