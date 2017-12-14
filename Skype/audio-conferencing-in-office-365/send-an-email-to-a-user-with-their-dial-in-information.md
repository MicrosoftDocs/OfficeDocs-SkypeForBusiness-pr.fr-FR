---
title: "Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](7440d3e2-1b49-4258-bd2c-79e9072f8c8d.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/7440d3e2-1b49-4258-bd2c-79e9072f8c8d). 
  
Parfois Skype pour les utilisateurs d'entreprise ou Microsoft Teams avoir besoin de vous leur envoyer leurs informations de conférence Audio. Vous pouvez le faire en utilisant **Skype centre d'administration entreprise** en cliquant sur **Envoyer les informations de conférence par courrier électronique** sous les propriétés d'un utilisateur. Lorsque vous communiquez, elle contient toutes les informations de services d'audioconférence, y compris :
  
- Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.
    
- L'ID de conférence de l'utilisateur.
    
    > [!NOTE]
    > ID statique est utilisés lorsque les personnes de votre organisation ne voulez pas n'oubliez pas d'un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utilisez celui qui est facile à mémoriser. Lors de l'ID de conférence dynamique sont utilisés, chaque réunion qui une planification de l'utilisateur doivent obtenir affectées un ID de conférence unique. Si vous voulez affecter les dynamique plutôt que de conférence statique ID, [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Voici un exemple du message est envoyé :
  
![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Envoyer un message électronique avec les informations de services d'audioconférence à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise**, dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Cliquez sur **utilisateurs** et sélectionnez l'utilisateur.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
> [!TIP]
> Vous pouvez également envoyer des e-mails à l'utilisateur avec les paramètres de services d'audioconférence par la modification des propriétés de l'utilisateur, puis en cliquant sur **les conférences Audio** > **Envoyer les informations de conférence par courrier électronique**. 
  
## Que devez-vous savoir d'autre sur les courriers électroniques ?

- Il existe plusieurs messages électroniques qui sont envoyés aux utilisateurs de votre organisation une fois qu'elles sont activées pour les conférences audio :
    
  - Lorsqu'une licence de **Conférence Audio** leur est attribuée.
    
  - Lorsque vous effectuez manuellement les services d'audioconférence de l'utilisateur code confidentiel.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsqu'une licence de **Conférence Audio** est supprimée à partir de ceux-ci.
    
  - Lorsque le fournisseur de services d'audioconférence pour un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de services d'audioconférence pour un utilisateur est modifié à Microsoft.
    
- Par défaut, l'expéditeur des e-mails sera d'Office 365, mais vous pouvez modifier l'adresse de messagerie et nom complet à l'aide de Windows PowerShell et l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Pour apporter des modifications à l'adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez :
    
  - Entrez l'adresse de messagerie dans le paramètre SendEmailFromAddress.
    
  - Définissez le paramètre SendEmailOverride sur True.
    
  - Entrez le nom d'affichage courrier dans le paramètre SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse personnalisée définie. 
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
    Pour envoyer un message électronique à l'utilisateur avec leurs informations de services d'audioconférence, exécutez la commande suivante :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Lorsqu'il s'agit de Windows PowerShell, Skype Entreprise Online est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

