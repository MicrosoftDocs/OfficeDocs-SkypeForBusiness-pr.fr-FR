---
title: "Modifier les paramètres d'un pont de conférence Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
---

# Modifier les paramètres d'un pont de conférence Audio

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Lorsque vous configurez des services d'audioconférence dans Office 365, vous recevrez les numéros de téléphone pour vos utilisateurs à partir de ce que l'on appelle un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Ces numéros de téléphone sont utilisés lorsque les appelants se connectent à une réunion. Le numéro de téléphone est inclus en bas de la Skype Entreprise ou Teams Microsoft invitation.
  
Le pont de conférence répond à un appel et vous invite de l'appelant avec invites vocales à l'aide d'un automatique de réunion standard, puis, selon les paramètres, il peut lire les notifications, demander aux appelants d'enregistrer leur nom et contrôler les paramètres de code confidentiel. Codes confidentiels sont accordées aux organisateurs de réunion pour lui permettre pour démarrer une réunion lorsqu'ils sont n'utilisez pas un Skype Entreprise ou une application de Teams Microsoft.
  
> [!IMPORTANT]
> Un code confidentiel n'est nécessaire pour l'organisateur de la réunion lorsqu'un utilisateur de l'application Microsoft Teams ou un Skype Entreprise n'a pas déjà commencé la réunion. Si tout le monde est se connectant à la réunion, le code confidentiel est nécessaire pour l'organisateur de la réunion démarrer la réunion. 
  
## Modifier les paramètres d'un pont de conférence audio

 **Configurer l'expérience de réunion lorsque les appelants participer à une réunion**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche atteindre **audioconférence** > **paramètres du pont Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft**, sous **expérience de participer à une réunion**, sélectionnez :
    
  - **Activer l'accès à la réunion et quitter notifications pour être activée** Cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les utilisateurs qui ont déjà rejoint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
    Lorsque vous sélectionnez **Activer l'accès à la réunion et quitter notifications pour être activé**, vous pouvez sélectionner ces options dans la liste **type d'entrée et de sortie annonce**:
    
  - **Noms ou les numéros de téléphone** Lorsque les utilisateurs se connectent à une réunion, son numéro de téléphone est émis lorsqu'ils participent à celui-ci.
    
  - **Tonalités** Lorsque les utilisateurs se connectent à une réunion, un signal audio est émis lorsqu'ils participent à celui-ci.
    
    > [!NOTE]
    > L'utilisation de **sonnerie** comme type d'annonce est actuellement disponible pour tous les clients sous forme de fonctionnalité en préversion.
  
  - **Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion** Cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les appelants ne vous êtes invités à enregistrer leur nom avant de participer à une réunion.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
 **Définir la longueur du code confidentiel pour les réunions**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft**, sous **sécurité**, entrez le nombre de chiffres que vous voulez pour le code confidentiel dans la liste **longueur du code confidentiel**, puis cliquez sur **Enregistrer**.
    
    > [!IMPORTANT]
    > Le code confidentiel doit être comprise entre 4 à 12 chiffres. 
  
 **Indiquez si vous souhaitez envoyer des messages électroniques à vos utilisateurs**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft**, activez ou désactivez **Envoyer automatiquement les messages électroniques pour les utilisateurs si leur configuration des services d'audioconférence change**, puis cliquez sur **Enregistrer**.
    
    Pour plus d'informations, voir [Messages électroniques qui sont envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence Audio modifier](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md) .
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
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

