---
title: "Démarrer une conférence Audio par téléphone sans code confidentiel"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# Démarrer une conférence Audio par téléphone sans code confidentiel

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Il peut être frustrant pour les utilisateurs qui se connectent à une réunion à conserver dans la salle d'attente de la réunion à l'écoute de la musique, car la Skype pour les entreprises ou Microsoft Teams organisateur de la réunion n'a pas commencé la réunion.
  
Si l'organisateur d'une réunion appelle la réunion, par défaut, un code confidentiel est nécessaire pour démarrer une réunion. Vous pouvez le configurer l'afin que tout le monde peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel pour commencer la réunion. Vous pouvez utiliser la Skype centre d'administration Business pour activer ou désactiver ce paramètre pour un seul utilisateur.
  
Un code confidentiel n'est pas nécessaire pour l'organisateur de la réunion si quelqu'un a commencé à la réunion à partir d'un Skype entreprise ou Microsoft Teams application. Un code confidentiel n'est requis lors de l'organisateur d'une réunion joint à leur réunion via un téléphone. Le code confidentiel pour les réunions est envoyé à l'utilisateur audio lorsqu'ils sont voient attribuer la licence de **Services d'audioconférence** et sont activées pour les services d'audioconférence. Voir[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) et des[Messages électroniques qui sont envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence Audio modifier](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Autorisation ou refus des appelants anonymes à participer à une réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **utilisateurs**.
    
4. Dans la liste, sélectionnez l'utilisateur, dans le volet Action, cliquez sur **Modifier**.
    
5. Sur la page de propriétés de l'utilisateur, sous **options de la réunion**, activez ou désactivez **permettre non authentifié aux appelants pour sont les premiers dans une réunion. Si pas, puis ils attend dans la salle d'attente jusqu'à ce qu'un utilisateur authentifié joint**.
    
6. Cliquez sur **Enregistrer**.
    
 **Pour activer ou désactiver les appelants anonymes à toutes les réunions de vos utilisateurs à l'aide de Windows Powershell**
  
- Exécutez la commande suivante : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## Informations supplémentaires

- Si vous voulez réinitialiser le code confidentiel, voir [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Si l'accès anonyme ou non nécessitant un code confidentiel démarrer une réunion est activé :
    
  - Si la réunion n'a pas commencé (il n'existe pas dans la réunion encore) : un appelant devra s'il est l'organisateur ; Si il indique Oui, il serez invité pour son code confidentiel et une fois qu'il est une entrée du code confidentiel, la réunion démarre et l'utilisateur sera rejoindre la réunion.
    
  - Si la réunion déjà commencé (quelqu'un est déjà dans la réunion) : un appelant ne vous y êtes invité si il est l'organisateur et il serez jamais invité pour le code confidentiel ; la réunion est déjà commencée, et l'appelant joint.
    
- Si l'accès anonyme, ou ne pas nécessitant un code confidentiel démarrer une réunion est désactivée :
    
  - Si la réunion n'a pas commencé (il n'existe pas dans la réunion encore) : un appelant ne vous y êtes invité si elle est l'organisateur, et elle ne serez jamais invitée pour le code confidentiel. Étant donné que le paramètre de l'organisateur est défini sur désactivé, la réunion démarre et les appelants anonymes rejoindront la réunion.
    
  - Si la réunion déjà commencé (quelqu'un est déjà dans la réunion) : un appelant ne vous y êtes invité si elle est l'organisateur, et elle ne serez jamais invitée pour le code confidentiel, la réunion est déjà démarrée et il rejoindront l'appelant.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Lorsqu'il s'agit de Windows PowerShell, Skype Entreprise Online est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
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
  

