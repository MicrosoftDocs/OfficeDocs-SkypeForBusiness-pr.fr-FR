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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 5247d814429d8d1f62fe9ea963aa76b7aafe40df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776319"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels

Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs. Pour effectuer ces étapes en bloc, nous avons inclus des liens vers les cmdlets Windows PowerShell que vous pouvez utiliser.
  
Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :
  
- [Autorisez les utilisateurs à contacter des utilisateurs Skype entreprise externes](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez faire en sorte que votre organisation utilise les fonctionnalités avancées de Skype entreprise (partage de bureaux, recherchez qui est en ligne, etc.). Cet article explique également comment bloquer des communications avec des domaines spécifiques.
    
- [Autorisez les utilisateurs Skype entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md). Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.
    
## <a name="configure-general-settings-for-one-user"></a>Configurer les paramètres généraux pour un utilisateur
<a name="__toc325019204"> </a>

Vous devez disposer des [autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**
  
1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.
    
|**Option**|**Détails**|
|:-----|:-----|
|Appels audio et vidéo HD  <br/> |Autorisez cette personne à enregistrer les réunions audio et les réunions audio et vidéo ou ne l’autorisez pas à planifier des réunions (aucune).  <br/> |
|Enregistrer les conversations et les réunions  <br/> |Sélectionnez les éléments que cette personne est autorisée à enregistrer.  <br/> Cette option n’est pas disponible dans Skype entreprise Basic.  <br/> |
|À des fins de conformité, désactivez les fonctions non archivées.  <br/> | Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement. <br/>  La sélection de cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous disposez d’une [conservation inaltérable](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) dans le centre d’administration Exchange. Elle désactive les fonctions suivantes : <br/>  transfert de fichiers avec la messagerie instantanée <br/>  Pages OneNote partagées <br/>  Annotations PowerPoint <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloquer les communications externes
<a name="__toc325019206"> </a>

Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.
  
1. Sélectionnez **utilisateurs**, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis sélectionnez **modifier** ![la modification](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :
    
   - **Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.
    
   - **Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.
    
3. Cliquez sur **Enregistrer**.
    
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modifier les paramètres de l’audioconférence pour un utilisateur
<a name="__toc314837483"> </a>

1. Sélectionnez **utilisateurs**, sélectionnez l’utilisateur dont vous souhaitez modifier les paramètres de conférence rendez-vous, **Edit** ![puis sélectionnez](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)modifier la modification.
    
2. Sélectionnez **audioconférence**, sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.
    
|**Configuration de l'audioconférence**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Dans la liste, choisissez votre fournisseur.  <br/> |
|**Numéro payant** (obligatoire) <br/> |Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettez en forme les numéros comme vous voulez qu’ils apparaissent dans les demandes de réunion Skype entreprise et Microsoft Teams.  <br/> |
|**Numéro gratuit** <br/> |Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettez en forme les numéros comme vous voulez qu’ils apparaissent dans les demandes de réunion Skype entreprise et Microsoft Teams.  <br/> |
|**ID de conférence et code confidentiel** (obligatoire) <br/> |Code confidentiel du participant, ou code de conférence, utilisé pour participer aux réunions planifiées par cet utilisateur et fourni par un fournisseur de services d’audioconférence tiers. Si l’utilisateur utilise Microsoft en tant que fournisseur de services d’audioconférence, ce n’est pas obligatoire.  <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Reportez-vous [à la rubrique définition des numéros de téléphone inclus dans les invitations](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Voir aussi 

[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
