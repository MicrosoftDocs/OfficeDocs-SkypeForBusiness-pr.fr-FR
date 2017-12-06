---
title: "Réinitialiser l'ID de conférence d'un utilisateur"
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
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# Réinitialiser l'ID de conférence d'un utilisateur

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](6e12242c-55f7-4bf4-90d7-0f36c0326b8e.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/6e12242c-55f7-4bf4-90d7-0f36c0326b8e). 
  
Lorsque votre organisation n'a pas été activé pour les identifiants de conférence dynamique, un ID de conférence statique est automatiquement créé lorsqu'un Skype pour l'utilisateur d'entreprise ou Microsoft Teams est activé pour les conférences Audio à l'aide de Microsoft comme fournisseur. Cet ID de conférence est inclus en bas de la réunion invitations ainsi que les numéros de téléphone de connexion qui peuvent être utilisées par les appelants à participer à une réunion. Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion demandera de l'appelant d'entrer cette ID de conférence afin qu'ils peuvent participer à la réunion.
  
> [!NOTE]
> Si votre fournisseur de conférence est Microsoft, ID de conférence de vos utilisateurs est définis sur dynamique uniquement par défaut. Malheureusement, vous ne pourrez pas modifier dans le Skype pour le centre d'administration entreprise ou à l'aide de Windows Powershell. Vous devrez contacter le support technique Microsoft. 
  
ID statique est utilisés lorsque les personnes de votre organisation ne voulez pas n'oubliez pas d'un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utilisez celui qui est facile à mémoriser. Lors de l'ID de conférence dynamique sont utilisés, chaque réunion qui une planification de l'utilisateur doivent obtenir affectées un ID de conférence unique. Si vous voulez affecter les dynamique plutôt que de conférence statique ID, [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
ID de conférence est définies uniquement automatiquement uniquement pour Skype pour les utilisateurs d'entreprise et Teams Microsoft activé pour les conférences Audio à l'aide de Microsoft en tant que leur fournisseur de services d'audioconférence. Si vous avez besoin réinitialiser l'ID de conférence pour un utilisateur qui utilise un fournisseur de services d'audioconférence tiers (ACP), vous devrez entrer manuellement un ID de conférence dans la page Propriétés de l'utilisateur.
  
## La réinitialisation de l'ID de conférence pour un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, cliquez sur **conférence Audio** > **utilisateurs**, sélectionnez un utilisateur, puis dans le volet Action sous **ID de conférence** cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l'ID de conférence ?** fenêtre, cliquez sur **Oui**. Une conférence QU'ID est automatiquement créée et un message électronique envoyé à l'utilisateur avec le nouvel ID de conférence. Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.
    
    > [!NOTE]
    > Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes. 
  
## Informations supplémentaires

- Vous pouvez envoyer toutes les informations de conférence à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence par courrier électronique** pour l'utilisateur dans le volet Action. Il n'envoie le code confidentiel.
    
- Un ID de conférence contiendra 7 chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype centre d'administration entreprise ou à l'aide de Windows PowerShell.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- L'ID de conférence pour un utilisateur pour les conférences audio peut être affiché en bas du volet Actions sous **conférence Audio** lorsque vous sélectionnez l'utilisateur dans la page **utilisateurs**.
    
- Après la création d'un nouvel ID de conférence, l'ID de conférence ancien ne peuvent pas utilisé par les appelants. Vous recommandons d'informer les utilisateurs à reprogrammer son existant invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté aux invitations aux réunions. Les utilisateurs peuvent utiliser Skype Entreprise Meeting Tool pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter la Skype pour les entreprises Meeting Update Tool, voir :
    
  - [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype entreprise Online, outil de Migration de réunion (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype entreprise Online, outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

