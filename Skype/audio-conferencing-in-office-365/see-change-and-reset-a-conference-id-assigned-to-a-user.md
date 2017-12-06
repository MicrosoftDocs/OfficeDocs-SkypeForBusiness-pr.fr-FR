---
title: "Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur"
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
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](77d36233-2aab-4802-ba9c-e9a8885ea643.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/77d36233-2aab-4802-ba9c-e9a8885ea643). 
  
Un ID de conférence est automatiquement affecté à un Skype pour entreprise ou Microsoft Teams utilisateur lorsqu'ils sont configurés pour les services d'audioconférence dans Office 365 et utilisent Microsoft comme fournisseur de services d'audioconférence. L'ID de conférence affectée peut être statique ou dynamique et est envoyé dans l'invitation à la réunion lors de la planification de la réunion.
  
ID statique est utilisés lorsque les personnes de votre organisation ne voulez pas n'oubliez pas d'un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utilisez celui qui est facile à mémoriser. Lors de l'ID de conférence dynamique sont utilisés, chaque réunion qui une planification de l'utilisateur doivent obtenir affectées un ID de conférence unique. Si vous voulez affecter les dynamique plutôt que de conférence statique ID, [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Bien qu'un ID de conférence statique est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu'un utilisateur ne souhaite pas utiliser celle-ci et que vous voulez définir à un certain nombre, ou lorsque vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. Vous pouvez utiliser la **Skype centre d'administration Business** et Windows PowerShell pour afficher, modifier et réinitialiser leur ID de conférence.
  
Un message électronique sera envoyé à l'utilisateur avec l'ID de conférence et les numéros de téléphone de conférence audio par défaut, ou si vous réinitialisez l'ID de conférence une autre adresse de messagerie est envoyée qui inclut l'ID de conférence, mais pas un code confidentiel.
  
## Afficher et modifier les identifiants de conférence

### Pour afficher l'ID de conférence

Vous pouvez afficher leur ID de conférence et envoyez-le aux utilisateurs.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**> **audioconférence** > **utilisateurs**, sélectionnez l'utilisateur qui doit être la conférence identifiant.
    
4. Dans la page Action, regardez sous **ID de conférence**.
    
    > [!TIP]
    > Vous pouvez envoyer toutes les informations de conférence à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par courrier électronique** après avoir sélectionné l'utilisateur dans la page **utilisateurs**. 
  
    Vous pouvez utiliser Windows PowerShell pour afficher l'ID de conférence pour un utilisateur. Pour ce faire, exécutez :
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Voir [Get-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617693 ) pour en savoir plus sur l'applet de commande.
    
### Pour attribuer ou modifier l'ID de conférence

Vous pouvez attribuer ou modifier un ID de conférence pour un utilisateur si, par exemple, une personne souhaite un ID de conférence et facile à retenir.
  
> [!NOTE]
> La Skype centre d'administration professionnels ne peut pas être utilisé pour modifier un ID de conférence qui a été créé automatiquement, mais vous pouvez utiliser Windows PowerShell pour modifier ou changer un ID de conférence que vous avez défini. 
  
> Pour modifier ou changer l'ID de conférence d'un utilisateur, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

    > [!TIP]
    > Un ID de conférence doit contenir 7 chiffres, et vous ne pouvez pas le modifier dans le Skype centre d'administration entreprise ou à l'aide de Windows PowerShell. 
  
### Pour réinitialiser l'ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur (par exemple, s'il l'a oublié).
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**> **audioconférence** > **utilisateurs**, dans le volet Action sous **ID de conférence**, cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l'ID de conférence ?** fenêtre, cliquez sur **Oui**. Une conférence QU'ID est automatiquement créée et un message électronique envoyé à l'utilisateur avec le nouvel ID de conférence.
    
    Vous pouvez réinitialiser l'ID de conférence d'un utilisateur à l'aide de Windows PowerShell. À cet effet, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## Informations supplémentaires

-     > [!IMPORTANT]
    >  Une fois un nouvel ID de conférence est créé ou une réinitialisation, l'ID de conférence ancien ne peuvent pas utilisé par les appelants. Vous recommandons d'informer les utilisateurs à reprogrammer son existant invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté aux invitations aux réunions. Les utilisateurs peuvent utiliser l'outil de Migration de réunion Skype Entreprise pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l'outil, voir :> [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Outil de migration de réunions Skype Entreprise Online (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype entreprise Online, outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
  
- Voir [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688 ) pour en savoir plus sur l'applet de commande.
    
- L'ID de conférence doit respecter la longueur en chiffres définis sur le pont de conférence audio. Vous ne pouvez pas utiliser caractères alphabétiques ou spéciales dans conférence ID ; Seuls les nombres peuvent être utilisés.
    
- L'ID de conférence pour l'ensemble de vos utilisateurs de services d'audioconférence sera 7 chiffres par défaut, et le nombre de chiffres ne peuvent pas être modifié.
    
- Si l'utilisateur est déplacé de Microsoft comme fournisseur de services d'audioconférence à un fournisseur de services d'audioconférence tiers ou le fournisseur de services d'audioconférence est défini sur **Aucun**, l'ID de conférence ne fonctionneront plus. Voir [Affecter un tiers comme fournisseur de services d'audioconférence](assign-a-third-party-as-the-audio-conferencing-provider.md) ou[Déplacement de fournisseur de services d'audioconférence d'un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

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
  

