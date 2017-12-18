---
title: "Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Les utilisateurs sont automatiquement avertis par courrier électronique lorsqu'ils sont activés pour les conférences Audio. Il peut arriver, toutefois, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés à Skype pour l'utilisateur d'entreprise et Teams de Microsoft. Dans ce cas, vous pouvez désactiver l'envoi de courrier électronique.
  
Si vous désactivez l'envoi de messages électroniques, messages électroniques de services d'audioconférence ne seront pas envoyées à vos utilisateurs, y compris les messages électroniques pour lorsque les utilisateurs sont activées ou désactivées pour les services d'audioconférence, lorsque son code confidentiel est réinitialisé, et lorsque l'ID de conférence et les conférences par défaut modifications numéros de téléphone .
  
Voici un exemple du courrier électronique qui est envoyé aux utilisateurs lorsqu'ils sont activés pour les conférences Audio :
  
![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Il existe plusieurs messages électroniques qui sont envoyés aux utilisateurs de votre organisation une fois qu'elles sont activées pour les conférences audio :
    
  - Lorsqu'une licence de **Conférence Audio** leur est attribuée.
    
  - Lorsque vous effectuez manuellement les services d'audioconférence de l'utilisateur code confidentiel.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la licence de **Conférence Audio** est supprimée à partir de ceux-ci.
    
  - Lorsque le fournisseur de services d'audioconférence d'un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de services d'audioconférence d'un utilisateur est modifié à Microsoft.
    
## Activer ou désactiver la messagerie à partir d'envoyé aux utilisateurs

Vous pouvez utiliser la Skype centre d'administration Business ou Windows PowerShell pour activer ou désactiver les messages envoyés aux utilisateurs.
  
 **À l'aide de la Skype centre d'administration Business**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise**, dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Dans la page **paramètres du pont Microsoft**, activez ou désactivez **Envoyer automatiquement les messages électroniques pour les utilisateurs si leurs paramètres de services d'audioconférence sont modifiés**.
    
4. Cliquez sur **Enregistrer**.
    
    > [!TIP]
    > Vous pouvez également envoyer des e-mails à un utilisateur avec les paramètres de services d'audioconférence en accédant à **audioconférence** > **utilisateurs**, sélectionnez l'utilisateur, puis cliquez sur **Envoyer les informations de conférence par courrier électronique**. > Si vous procédez ainsi, un message électronique est envoyé qui inclut uniquement les ID de conférence et numéro de téléphone de conférence, mais pas le code confidentiel. > Pour plus d'informations, voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) .
  
 **Utilisation de Windows PowerShell**
  
- Pour désactiver l'envoi de courriers électroniques, exécutez la commande suivante : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Pour obtenir de l'aide cette applet de commande, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## Informations supplémentaires

- Lorsque les messages électroniques automatiques sont désactivées, vous pouvez manuellement déclencher envoyant un courrier électronique avec la conférence ID et numéro de téléphone à l'aide de la Skype centre d'administration entreprise. Toutefois, si vous procédez ainsi, le code confidentiel n'est inclus. Si vous voulez réinitialiser le code confidentiel audioconférence et l'envoi d'e-mails est désactivé, vous devrez envoyer à l'utilisateur d'une autre façon.
    
- Par défaut, l'expéditeur des e-mails sera d'Office 365, mais vous pouvez modifier l'adresse de messagerie et afficher le nom à l'aide de Windows PowerShell et également utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les messages électroniques provenant de l'adresse personnalisée de l'expéditeur indiquée. 
  
  - entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
  - entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
  - définir le paramètre  _SendEmailOverride_ sur _True_;
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Vous pouvez utiliser ces applets de commande pour gagner du temps ou automatiser ce processus.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Supprimer CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Conférence rendez-vous dans Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

