---
title: "Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion"
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
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
description: "Learn how to enable or disable whether your users can record their names when they join a meeting "
---

# Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Lorsque vous configurez des services d'audioconférence dans Office 365, vous recevrez les numéros de téléphone et ce que l'on appelle un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone peuvent être un numéro de téléphone dédiés ou partagés.
  
Le pont de conférence répond à un appel d'un utilisateur qui est se connectant à une réunion à l'aide d'un téléphone. Le pont de conférence répond à l'appelant avec invites vocales à partir d'un standard automatique et puis, selon les paramètres, peut lire les notifications, demander aux appelants d'enregistrer leur nom, puis configurez la sécurité de code confidentiel pour les organisateurs de réunion. Codes confidentiels sont accordées aux organisateurs de réunion pour lui permettre de démarrer une réunion. Toutefois, vous pouvez le configurer vers le haut pour un code confidentiel n'est pas obligatoire pour démarrer une réunion.
  
## Définir si les appelants doivent enregistrer leur nom

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Sous **expérience de participer à une réunion**, reportez-vous à la case à cocher intitulée **Activer l'accès à la réunion et quitter notifications pour être activée**.
    
  - **Sélectionnée** Les appelants seront invités à enregistrer leur nom avant d'assister à la réunion. Cette option est sélectionnée par défaut.
    
  - **Désactivée** Les appelants ne seront pas invités à enregistrer leur nom avant d'assister à la réunion.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Windows PowerShell est tout sur la gestion des utilisateurs et les utilisateurs autorisés à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
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

