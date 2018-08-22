---
title: Gérer les paramètres de conférence Audio pour un utilisateur dans Skype pour Business en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'En tant qu’un administrateur Office 365, vous pouvez modifier le Skype pour les paramètres de conférence en ligne professionnels — telles que le fournisseur, numéro payant par défaut ou numéro gratuit, ID de conférence ou code confidentiel — pour un utilisateur individuel dans votre organisation. '
ms.openlocfilehash: ed8038955174a19e7861c872e1a095644288e6c2
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490524"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gérer les paramètres de conférence Audio pour un utilisateur dans Skype pour Business en ligne

> [!Note]
> Si vous souhaitez gérer les paramètres utilisateur dans Microsoft Teams, voir [Gérer les paramètres de conférence Audio pour un utilisateur dans les équipes Microsoft](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

En tant qu’un administrateur Office 365, vous pouvez modifier les paramètres de conférence Audio, tels que le fournisseur, numéro payant par défaut ou numéro gratuit, ID de conférence ou code confidentiel — pour un utilisateur individuel dans votre organisation. Si vous souhaitez modifier les paramètres de votre organisation, voir [Gérer les paramètres de conférence Audio de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Dans Skype entreprise centre d’administration, choisissez **utilisateurs**.
    
4. Sélectionnez l’utilisateur pour lequel vous souhaitez gérer les paramètres, puis cliquez sur **Modifier**dans le volet Actions,![affiche l’icône Modifier](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Choisissez **d’audioconférence** dans le volet de navigation gauche, puis, dans la page **Propriétés** de l’utilisateur, modifiez une des options suivantes :
    
|**Paramètre**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/><br/> **Remarque :** Les paramètres restants dans ce tableau s’appliquent uniquement si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.           |
|**Numéro de téléphone payant par défaut** (requis) <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera numéros qui sont définies sur le pont de conférence audio. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Bre gratuit par défaut** <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence. Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera numéros qui sont définies sur le pont de conférence audio. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Permettre à l’aide des numéros de téléphone gratuits dans le pont Microsoft de votre organisation à participer à des réunions de cet utilisateur** <br/> |Sélectionnez cette option si vous souhaitez permettre à l’utilisateur de numéros de téléphone gratuits pour participer à des réunions.  <br/> |
|**Envoyer les informations de conférence par courrier électronique** <br/> |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son numéro de téléphone et les ID de conférence. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID de conférence** <br/> |Sélectionnez **Rétablir** si vous avez besoin réinitialiser l’ID de conférence pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser un ID de conférence pour un utilisateur](reset-a-conference-id-for-a-user.md).  <br/> |
|**CODE CONFIDENTIEL** <br/> |Sélectionnez **Rétablir** si vous devez réinitialiser le code confidentiel de l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).  <br/> |
|**Autoriser les appelants non authentifiés à être les premiers à une réunion** <br/> |Sélectionnez cette option pour autoriser les appelants non authentifiés à participer à des réunions en premier.  <br/> |
|**Restrictions pour les sorties de l’accès à des réunions de cet utilisateur** <br/> |Sélectionnez une option dans cette liste si vous souhaitez restreindre l’accès sorties à national uniquement, ou si vous souhaitez empêcher tous les accès issus de réunions.  <br/> |
  
![Affiche la page de propriétés de conférence Audio d’un utilisateur](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
