---
title: Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: f99c99fc291a2df71a3e47448e3cc8fcf01e371f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370914"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels

Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs. Pour effectuer ces étapes en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.
  
Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :
  
- [Autoriser les utilisateurs à contacts Skype externe pour les utilisateurs professionnels](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez permettent à votre organisation d’utiliser avancée Skype pour les fonctionnalités d’entreprise (partage de postes de travail, recherchez qui est en ligne, etc.) pour communiquer avec des personnes dans une spécifique (fédérés) business approuvés. Cet article explique comment empêcher la communication avec des domaines spécifiques.
    
- [Laisser les Skype pour les utilisateurs professionnels Ajouter contacts Skype](let-skype-for-business-users-add-skype-contacts.md). Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.
    
## <a name="configure-general-settings-for-one-user"></a>Configurer les paramètres généraux pour un utilisateur
<a name="__toc325019204"> </a>

Vous devez disposer des [autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
  
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
|Enregistrer les conversations et les réunions  <br/> |Sélectionnez les éléments que cette personne est autorisée à enregistrer.  <br/> Cette option n’est pas disponible avec Skype pour Business Basic.  <br/> |
|À des fins de conformité, désactivez les fonctions non archivées.  <br/> | Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement. <br/>  Cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez un [Blocage sur Place](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configuré le centre d’administration Exchange. Elle désactive les fonctions suivantes : <br/>  transfert de fichiers avec la messagerie instantanée <br/>  Pages OneNote partagées <br/>  Annotations PowerPoint <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Consultez [Gestion des stratégies dans Skype Entreprise Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloquer les communications externes
<a name="__toc325019206"> </a>

Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.
  
1. Sélectionnez **les utilisateurs**, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :
    
   - **Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.
    
   - **Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.
    
3. Cliquez sur **Enregistrer**.
    
Pour configurer ces paramètres en bloc, utilisez PowerShell. Consultez [Gestion des communications dans Skype Entreprise Online avec des utilisateurs et des organisations externes](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modifier les paramètres de conférence audio pour un utilisateur
<a name="__toc314837483"> </a>

1. **Les utilisateurs**, sélectionnez l’utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Choisissez **l’audioconférence**, sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifier les informations demandées, puis cliquez sur **Enregistrer**.
    
|**Configuration de l'audioconférence**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/> |
|**Numéro payant** (obligatoire) <br/> |Pour un fournisseur tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Numéro gratuit** <br/> |Pour un fournisseur tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Code confidentiel et ID de conférence** (requis) <br/> |Le code participant code confidentiel, ou une conférence, utilisé pour participer à des réunions sont planifiées par cet utilisateur et sont fournies à partir d’un fournisseur de services d’audioconférence tiers. Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera requis.  <br/> |
   
Pour configurer ces paramètres en bloc, utilisez PowerShell. Voir [l’invite inclus sur les numéros de téléphone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Rubriques connexes 

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 