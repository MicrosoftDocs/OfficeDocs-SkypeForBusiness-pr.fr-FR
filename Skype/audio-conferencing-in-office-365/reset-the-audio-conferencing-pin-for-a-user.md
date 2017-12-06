---
title: "Réinitialiser le code confidentiel conférence Audio pour un utilisateur"
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# Réinitialiser le code confidentiel conférence Audio pour un utilisateur

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](67866a47-89c1-4593-8766-3a68777e2be6.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/67866a47-89c1-4593-8766-3a68777e2be6). 
  
Un code confidentiel est un code composé de nombres est créé pour chaque Skype pour entreprises et Microsoft Teams utilisateur qui est activé pour les services d'audioconférence. Services d'audioconférence des codes confidentiels sont utilisés par les organisateurs de réunion pour identifier qu'ils sont l'organisateur de la réunion et de démarrer une réunion par téléphone. S'ils utilisent le Skype entreprise ou Microsoft Teams application pour commencer la réunion, un code confidentiel n'est pas obligatoire. Si les utilisateurs oublient son code confidentiel et qu'ils ne la trouve pas dans le message électronique qui a été envoyé lorsqu'ils ont été activés pour les services d'audioconférence, un administrateur devra réinitialiser son code confidentiel. Un utilisateur ne peuvent pas réinitialiser leur propre code confidentiel.
  
Réunions peuvent être démarrées lorsqu'un utilisateur authentifié est ajouté à l'aide d'un Skype entreprise ou Microsoft Teams application ou lorsque l'organisateur rejoigne avec son code confidentiel par téléphone. Lorsqu'une réunion nécessite un code confidentiel pour démarrer, les utilisateurs qui participer par téléphone sera placé dans la salle d'attente et écouter de la musique pendant l'attente jusqu'à la réunion démarre. Si l'organisateur d'une réunion ne nécessite pas un code confidentiel démarrer la réunion par téléphone, puis les appelants n'invités à fournir un code confidentiel lorsqu'ils participent à la réunion.
  
## Réinitialisation du code confidentiel d'un organisateur de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise**, dans le volet de navigation gauche, cliquez sur **conférence Audio**
    
3. Cliquez sur **utilisateurs**, sélectionnez l'utilisateur que vous voulez réinitialiser le code confidentiel pour.
    
4. Dans le volet Action, sous **code confidentiel**, cliquez sur **Réinitialiser**.
    
## Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel ne s'affiche à un administrateur sur une seule fois, lorsque le code confidentiel est remis. Une fois que le code confidentiel est réinitialisé par un administrateur, le code confidentiel est répertorié comme ***** dans **Skype centre d'administration Business** et dans les résultats lorsqu'ils utilisent Get-CsCsOnlineDialInConfencingUser dans Windows PowerShell.
    
- Envoyer automatiquement les messages électroniques à des utilisateurs est activée par défaut et les utilisateurs recevront un message électronique avec son code confidentiel quand elles sont activées pour les services d'audioconférence ou lorsque le code confidentiel est remis. Mais si vous avez désactivé automatiquement l'envoi d'e-mails, un message de réinitialisation du code confidentiel ne seront pas envoyé à un utilisateur et vous devrez manuellement envoyer les informations de code confidentiel à l'utilisateur.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Le paramètre par défaut pour ne pas autoriser une réunion pour qu'il démarre par les appelants anonymes.
    
- Lorsque vous activez un utilisateur pour les services d'audioconférence, elles sont envoyées par défaut messages électroniques qui incluent des services d'audioconférence et son code confidentiel. L'utilisateur doit avoir une boîte aux lettres Office 365, étant donné que lorsqu'un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l'utilisateur dans un courrier électronique à leur adresse SMTP principale (alias) est défini pour l'utilisateur.
    
- Lorsque vous définissez des services d'audioconférence, vous définissez les chiffres requis pour les coins de votre organisation. Codes confidentiels peuvent comporter de 4 à 12 chiffres - la valeur par défaut est 5. Si vous changez le paramètre de longueur du code confidentiel, le paramètre est appliqué uniquement sur les codes confidentiels nouvellement créés et n'est pas appliqué au paramètre code confidentiel pour les utilisateurs existants qui sont activées pour les services d'audioconférence. Voir [Définir la longueur du code confidentiel pour les réunions d'audioconférence](set-the-length-of-the-pin-for-audio-conferencing-meetings.md).
    
- Le message électronique par défaut est fixé à l'adresse SMTP principale Office 365 de l'utilisateur. Vous pouvez envoyer un message électronique à une adresse non - Office 365 tels que Hotmail ou MSN. Vous pouvez ignorer l'adresse de messagerie par défaut à l'aide de Windows PowerShell. Ceci est utile si les utilisateurs ne rencontrent une boîte aux lettres Exchange dans Office 365.
    
- Pour ignorer l'adresse utilisateur par défaut dans lequel le message électronique est envoyé, l'administrateur client peut utiliser l'applet de commande suivante : Set-csonlinedialinconferencinguser n'affiche-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress « u@hotmail.com ». Le paramètre SendEmail est nécessaire pour ignorer l'adresse de messagerie de l'utilisateur.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

