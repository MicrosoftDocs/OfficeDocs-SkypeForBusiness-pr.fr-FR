---
title: "Administrateurs de configurer de Skype pour les paramètres d’entreprise pour les utilisateurs individuels"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: "Apprenez à modifier la Skype pour les paramètres d’entreprise pour les utilisateurs individuels tels que : conférence Audio et vidéo, des réunions et enregistrement des appels. "
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administrateurs : Configurer Skype pour les paramètres d’entreprise pour les utilisateurs individuels

Cet article explique comment les administrateurs configurer Skype pour l’entreprise pour un petit nombre d’utilisateurs. Pour effectuer ces opérations en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.
  
Pour autoriser (ou bloquer) tout le monde dans votre entreprise pour communiquer avec des utilisateurs externes, voir :
  
- [Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez permettent à votre organisation d’utiliser avancée Skype pour les fonctionnalités d’entreprise (partage de bureaux, recherchez qui est en ligne, etc.) pour communiquer avec des personnes spécifiques approuvés business (fédérées). L’article explique également comment bloquer les communications avec des domaines spécifiques.
    
- [Laisser les Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md). Vous pouvez laisser à votre organisation d’utiliser Skype pour les entreprises à rechercher et de messagerie instantanée utilisateurs de Skype, l’application gratuite.
    
## <a name="configure-general-settings-for-one-user"></a>Configurer les paramètres généraux pour un utilisateur
<a name="__toc325019204"> </a>

Vous devez disposer [des autorisations d’administration](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Choisissez le **Centre d’administration** > **Skype pour les entreprises**.
    
3. Choisissez **les utilisateurs**.
    
    ![Dans le Skype pour le centre d’administration Business, choisissez les utilisateurs.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Choisir les utilisateurs auxquels vous souhaitez modifier.
    
5. Dans le volet droit, cliquez **sur Modifier**.
    
    ![Cliquez sur l’icône Modifier.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Dans la page options **générales** , sélectionnez ou désactivez la case à cocher près des fonctionnalités que vous souhaitez modifier et puis cliquez sur **Enregistrer**.
    
|**Option**|**Détails**|
|:-----|:-----|
|Audio et vidéo HD  <br/> |Autoriser cette personne à des réunions audio enregistrements, réunions audio et vidéo, ou ne leur permettre de planifier les meeetings (aucun).  <br/> |
|Les réunions et les conversations de l’enregistrements  <br/> |Choisissez ce que cette personne est autorisée à enregistrer.  <br/> Cette option n’est pas disponible avec Skype pour Business Basic.  <br/> |
|Pour la conformité, désactivez les fonctionnalités de non archivées  <br/> | Choisissez cette option si vous êtes tenu de conserver des informations stockées par voie électronique. <br/>  La sélection de cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez une [Place maintenez](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) paramétré dans le centre d’administration Exchange. Il désactive les fonctionnalités suivantes : <br/>  transfert de fichier avec la messagerie instantanée <br/>  Pages OneNote partagées <br/>  Annotations PowerPoint <br/> |
   
Pour configurer ces paramètres en vrac, utilisez PowerShell. Reportez-vous à la section [Gestion des stratégies dans Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloquer les communications externes
<a name="__toc325019206"> </a>

Après vous [permettent de Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre société, vous pouvez bloquer de façon sélective les communications externes pour des utilisateurs spécifiques à l’aide de ces étapes.
  
1. Choisissez **les utilisateurs**et sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Choisissez la **communication externe**et puis désactivez les options appropriées :
    
  - **Skype externe pour les utilisateurs professionnels**: désactivez cette case si vous ne souhaitez pas que l’utilisateur soit en mesure de communiquer avec Skype pour les utilisateurs de domaines fédérés.
    
  - **Les utilisateurs de Skype externe**: désactivez cette case si vous ne souhaitez pas que l’utilisateur soit en mesure de communiquer avec des personnes qui sont à l’aide de l’application freeSkype.
    
3. Cliquez sur **Enregistrer**.
    
Pour configurer ces paramètres en vrac, utilisez PowerShell. Reportez-vous à la section [Gestion des communications dans Skype pour entreprise en ligne avec des utilisateurs et des organisations à l’extérieur](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modifier les paramètres de conférence audio d’un utilisateur
<a name="__toc314837483"> </a>

1. Choisissez **les utilisateurs**, sélectionnez l’utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Choisissez **audioconférence**Sélectionnez votre fournisseur de conférence audio, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.
    
|**Configuration de l'audioconférence**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/> |
|**Numéro payant** (obligatoire) <br/> |Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio. Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.  <br/> |
|**Numéro gratuit** <br/> |Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio. Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.  <br/> |
|**ID de conférence et code PIN** (obligatoire) <br/> |Le code PIN de participant, ou d’une conférence, utilisé pour participer à des conférences qui sont prévues par cet utilisateur et sont fournis à partir d’un fournisseur de conférence audio de tiers. Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, ce ne sera pas obligatoire.  <br/> |
   
Pour configurer ces paramètres en vrac, utilisez PowerShell. Voir [invite les inclure sur des numéros de téléphone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Rubriques connexes 

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

Pour en savoir plus, reportez-vous à la rubrique [Conférence rendez-vous dans Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
