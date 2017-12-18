---
title: "Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Cet article explique comment les administrateurs configurer Skype entreprise pour un petit nombre d'utilisateurs. Pour effectuer ces étapes en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.
  
Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :
  
- [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md) : vous pouvez permettre à votre organisation d'utiliser des fonctionnalités Skype Entreprise avancées (partager les bureaux, rechercher qui est en ligne) pour communiquer avec des personnes dans une entreprise de confiance (fédérée) spécifique. Explique également comment bloquer les communications pour certains domaines.
    
- [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) . Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.
    
## Configurer les paramètres généraux pour un utilisateur
<a name="__toc325019204"> </a>

Vous devez avoir [À propos des rôles d'administrateur Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**. 
    
3. Sélectionnez **Utilisateurs**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier. 
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.
    
|**Option**|**Détails**|
|:-----|:-----|
|Appels audio et vidéo HD  <br/> |Autorisez cette personne à enregistrer les réunions audio et les réunions audio et vidéo ou ne lʼautorisez pas à planifier des réunions (aucune).  <br/> |
|Enregistrer les conversations et les réunions  <br/> |Sélectionnez les éléments que cette personne est autorisée à enregistrer.  <br/> Cette option n'est pas disponible avec Skype Entreprise Basic.  <br/> |
|À des fins de conformité, désactivez les fonctions non archivées.  <br/> | Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement. <br/>  Cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez une[Archive permanente](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) défini le centre d'administration Exchange. Comment désactiver les fonctionnalités suivantes : <br/>  transfert de fichier avec la messagerie instantanée <br/>  Pages OneNote partagées <br/>  Annotations PowerPoint <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [Gestion des stratégies dans Skype entreprise Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## Bloquer les communications externes
<a name="__toc325019206"> </a>

Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.
  
1. Sélectionnez **les utilisateurs**, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis **Modifier**![Modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :
    
  - **Skype externes pour les utilisateurs professionnels**: désactivez cette case si vous ne voulez pas l'utilisateur à être en mesure de communiquer avec des utilisateurs Skype Entreprise dans les domaines fédérés.
    
  - **Les utilisateurs externes Skype**: désactivez cette case si vous ne voulez pas l'utilisateur à être en mesure de communiquer avec des personnes qui utilisent l'application gratuiteSkype.
    
3. Cliquez sur **Enregistrer**.
    
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [Gestion des communications dans Skype entreprise Online avec les utilisateurs extérieurs et des organisations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## Modifier les paramètres de conférence audio pour un utilisateur
<a name="__toc314837483"> </a>

1. Sélectionnez **utilisateurs**, sélectionnez l'utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis cliquez sur **Modifier**![Modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Sélectionnez **conférence Audio**, sélectionnez votre fournisseur de services d'audioconférence, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.
    
|**Paramètre de services d'audioconférence**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/> |
|**Numéro payant** (obligatoire) <br/> |Pour un fournisseur tiers, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de services d'audioconférence. Si l'utilisateur utilise Microsoft comme fournisseur de services d'audioconférence, ces seront nombres qui sont définis sur le pont de conférence audio. Mettre en forme les nombres que vous souhaitez les voir apparaître dans Skype Entreprise et Teams Microsoft demandes de réunion.  <br/> |
|**Numéro gratuit** <br/> |Pour un fournisseur tiers, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de services d'audioconférence. Si l'utilisateur utilise Microsoft comme fournisseur de services d'audioconférence, ces seront nombres qui sont définis sur le pont de conférence audio. Mettre en forme les nombres que vous souhaitez les voir apparaître dans Skype Entreprise et Teams Microsoft demandes de réunion.  <br/> |
|**ID de conférence et code PIN** (obligatoire) <br/> |Le code PIN participant, ou d'une conférence, utilisé pour participer aux réunions planifiées par cet utilisateur et sont fournies à partir d'un fournisseur de services d'audioconférence tiers. Si l'utilisateur utilise Microsoft comme fournisseur de services d'audioconférence, cela n'est pas requis.  <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![Petit icône de LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Vous débutez dans Office 365 ?**         Découvrez les cours vidéo gratuits destinés aux administrateurs **Office 365 et aux professionnels de l'informatique**, proposés par LinkedIn Learning. |
   
## Rubriques connexes
<a name="__toc314837483"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

