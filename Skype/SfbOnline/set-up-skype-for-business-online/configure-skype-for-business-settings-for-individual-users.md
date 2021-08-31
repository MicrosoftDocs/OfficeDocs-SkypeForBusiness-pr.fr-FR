---
title: Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: e96e33f5a83030f187c6e6c3caaee197c2d81a2f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731823"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Le Microsoft Teams d’administration a remplacé Skype Entreprise centre d’administration principal (portail hérité). Tous les paramètres de gestion des Skype Entreprise sont désormais dans le Centre Teams’administration. Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise vous doit être attribué pour gérer les fonctionnalités de gestion des Skype Entreprise dans le Teams d’administration. Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs. Pour suivre ces étapes en bloc, nous avons inclus des liens vers les Windows PowerShell cmdlets que vous pouvez utiliser.
  
Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :
  
- Autoriser les utilisateurs à contacter des utilisateurs [Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md)externes : vous pouvez permettre à votre organisation d’utiliser des fonctionnalités de Skype Entreprise avancées (partager des bureaux, rechercher qui est en ligne, etc.) pour communiquer avec des personnes dans une entreprise de confiance (fédérée) spécifique. Cet article explique également comment bloquer les communications avec des domaines spécifiques.
    
- [Permettez aux Skype Entreprise d’ajouter Skype contacts.](let-skype-for-business-users-add-skype-contacts.md) Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.
    
## <a name="configure-general-settings-for-one-user"></a>Configurer les paramètres généraux pour un utilisateur
<a name="__toc325019204"> </a>

Vous devez avoir des [autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**
  
1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.
    
|**Option**|**Détails**|
|:-----|:-----|
|Appels audio et vidéo HD  <br/> |Autorisez cette personne à enregistrer des réunions audio, audio et vidéo, ou ne l’autorisez pas à planifier des réunions (aucune).  <br/> |
|Enregistrer les conversations et les réunions  <br/> |Sélectionnez les éléments que cette personne est autorisée à enregistrer.  <br/> Cette option n’est pas disponible avec Skype Entreprise Basic.  <br/> |
|À des fins de conformité, désactivez les fonctions non archivées.  <br/> | Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement. <br/>  La sélection de cette option permet de sélectionner [](/exchange/security-and-compliance/in-place-and-litigation-holds) des fonctionnalités qui ne sont pas capturées lors de la mise en place d’une attente sur place dans le Exchange d’administration. Elle désactive les fonctions suivantes : <br/>  transfert de fichiers avec la messagerie instantanée <br/>  Pages OneNote partagées <br/>  Annotations PowerPoint <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Consultez [Configurer votre ordinateur pour Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>Bloquer les communications externes
<a name="__toc325019206"> </a>

Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.
  
1. **Sélectionnez** Utilisateurs, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis **sélectionnez** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifier.
    
2. Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :
    
   - **Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.
    
   - **Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.
    
3. Cliquez sur **Enregistrer**.
    
Pour configurer ces paramètres en bloc, utilisez PowerShell. Consultez [Configurer votre ordinateur pour Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modifier les paramètres d’audioconférence pour un utilisateur
<a name="__toc314837483"> </a>

1. **Sélectionnez** Utilisateurs, sélectionnez l’utilisateur dont vous souhaitez modifier les paramètres d’audioconférence, puis **sélectionnez** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifier.
    
2. Sélectionnez **Audioconférence,** sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer.**
    
|**Configuration de l'audioconférence**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/> |
|**Numéro payant** (obligatoire) <br/> |Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les nombres de la même forme que vous voulez qu’ils apparaissent Skype Entreprise et Microsoft Teams des réunions.  <br/> |
|**Numéro gratuit** <br/> |Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les nombres de la même forme que vous voulez qu’ils apparaissent Skype Entreprise et Microsoft Teams des réunions.  <br/> |
|**ID et code confidentiel** de conférence (obligatoire) <br/> |Code confidentiel du participant, ou code de conférence, utilisé pour participer à des réunions organisées par cet utilisateur et fournies par un fournisseur de services d’audioconférence tiers. Si l’utilisateur utilise Microsoft comme fournisseur de services d’audioconférence, cela ne sera pas obligatoire.  <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Consultez [Définir les numéros de téléphone inclus dans les invitations](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurer votre ordinateur pour [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Rubriques connexes 

[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
