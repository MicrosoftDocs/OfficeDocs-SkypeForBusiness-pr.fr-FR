---
title: "Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Services d'audioconférence dans Office 365 permet aux utilisateurs de votre organisation créer un Skype pour les réunions d'entreprise et Teams Microsoft et puis permettre aux utilisateurs de se connecter à l'aide d'un téléphone. Dans Office 365, vous avez la possibilité de l'utilisation d'un pont de conférence audio Microsoft ou utiliser un pont de services d'audioconférence tiers qui est hébergé par un fournisseur de services agréés (ACP).
  
Un pont de conférence fournit à votre organisation un ensemble de numéros de téléphone à composer. Ils peuvent tous être utilisés pour rejoindre les réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui seront inclus dans les invitations aux réunions.
  
> [!NOTE]
> Il peut y avoir un maximum d'un numéro payant et un numéro de téléphone gratuit sur l'invitation à la réunion pour l'organisateur d'une réunion, mais il est également un lien situé en bas de chaque invitation à une réunion qui permet d'afficher la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion. 
  
## Définition du numéro de téléphone à composer pour un organisateur de la réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**. 
    
3. Sélectionnez **Utilisateurs**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier : 
    
  - Pour sélectionner un seul utilisateur, sélectionnez son nom.
    
  - Pour sélectionner tous les utilisateurs sur la page, activez la case à côté de **Nom d'affichage** en haut de la liste.
    
  - Pour sélectionner plusieurs utilisateurs, appuyez sur la touche Ctrl et maintenez-la enfoncée tout en cliquant sur les utilisateurs souhaités.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Dans la liste déroulante **fournisseur**, sélectionnez le fournisseur pour l'utilisateur. En fonction du fournisseur, complétez les zones suivantes.
    
  - **Microsoft est le fournisseur**: utiliser le **numéro payant par défaut** et **numéro gratuit par défaut** des listes pour sélectionner les numéros par défaut pour l'utilisateur.
    
    > [!NOTE]
    > Au moins un numéro gratuit doit être attribué à votre pont de conférence avant de pouvoir être défini comme numéro gratuit par défaut d'un utilisateur. Pour obtenir un numéro gratuit, consultez la rubrique [Obtention des numéros de téléphone des services Skype Entreprise](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). 
  
  - **Un tiers est le fournisseur**: utilisez les champs **Numéro payant** et **Numéro gratuit** pour entrer les numéros de l'utilisateur.
    
## Réinitialiser les numéros de téléphone des services d'audioconférence

1. Dans la **Centre d'administration Skype Entreprise**, choisissez **audioconférence**.
    
2. En haut de la page, cliquez sur **utilisateurs d'appels entrants**.
    
3. Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis cliquez sur **Effacer**. 
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
Par défaut, lorsque vous modifiez les paramètres de conférence d'un utilisateur, les messages électroniques sont envoyés aux utilisateurs. Pour résoudre ce problème, voir [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
  
> [!IMPORTANT]
> Lorsque vous modifiez les paramètres de services d'audioconférence d'un utilisateur, Skype périodique et à venir pour les réunions d'entreprise et Teams Microsoft doit être mis à jour et envoyée aux participants. 
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688) .
    
- Utiliser l'applet de commande [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant par défaut ou un numéro gratuit pour des utilisateurs spécifiques.
    
    Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour rechercher le BridgeID, utilisez l'applet de commande **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Pour définir le numéro gratuit par défaut pour tous les utilisateurs sans un à +18005551234, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui ont +18005551234 comme leur numéro gratuit par défaut à +18005551239, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis pour +18005551234, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui ont +18005551234 comme leur numéro gratuit par défaut à +18005551239 et reprogrammer toutes les réunions avec un nouveau numéro gratuit, exécutez :
    
  -     > [!NOTE]
    > L'emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le Centre d'administration Office 365. 
  
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

