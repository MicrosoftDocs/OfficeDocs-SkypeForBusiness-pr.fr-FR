---
title: "Activer ou désactiver les annonces d'entrée et de sortie des réunions"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# Activer ou désactiver les annonces d'entrée et de sortie des réunions

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](f2c7b5ea-07b6-4b77-8023-bec9596fcc32.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/f2c7b5ea-07b6-4b77-8023-bec9596fcc32). 
  
Lorsque vous configurez des services d'audioconférence dans Office 365, vous obtenez un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone personnes utiliseront pour appeler un Skype entreprise ou Microsoft Teams réunion.
  
Le pont de conférence répond à un appel d'un utilisateur qui est se connectant à une réunion à l'aide d'un téléphone. Le pont de conférence répond à l'appelant avec invites vocales à partir d'un standard automatique de conférence et puis, selon les paramètres, peut lire les notifications, demander aux appelants d'enregistrer leur nom, puis configurez la sécurité du code PIN. Un code confidentiel est donné à une Skype pour les entreprises ou Microsoft Teams organisateur de la réunion, et vous permet de démarrer une réunion si elles ne peuvent pas commencer la réunion à l'aide d'un Skype entreprise ou Microsoft Teams application. Vous pouvez, cependant, configurer de manière un code confidentiel n'est pas obligatoire pour démarrer une réunion.
  
## Définir les options de participation à une réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Sous **expérience de participer à une réunion**, activez ou désactivez **Activer l'accès à la réunion et quitter notifications pour être activée**. Cette option est sélectionnée par défaut. Si vous désactivez, les utilisateurs qui ont déjà rejoint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
5. Sous **type d'entrée et de sortie annonce**, sélectionnez les **noms ou les numéros de téléphone** ou **tonalités**.
    
6. Activez ou désactivez les **appelants Ask à enregistrer leur nom avant de rejoindre la réunion**.
    
7. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Lorsqu'il s'agit de Windows PowerShell, Skype Entreprise Online est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365 tels que lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
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

