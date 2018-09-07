---
title: Gérer les paramètres d’Audioconférence pour un utilisateur dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'En tant qu’administrateur Office 365, vous pouvez modifier les paramètres de l’audioconférence Skype Entreprise Online — tels que le fournisseur, le numéro payant ou gratuit par défaut, l’identifiant de conférence ou le code confidentiel — pour un utilisateur individuel dans votre organisation. '
ms.openlocfilehash: 34034a74624419b9ac7b18b31b6878c589881e29
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23859590"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gérer les paramètres d’Audioconférence pour un utilisateur dans Skype Entreprise Online

> [!Note]
> Si vous souhaitez gérer les paramètres utilisateur dans Microsoft Teams, consultez la rubrique [Gérer les paramètres d’Audioconférence pour un utilisateur dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

En tant qu’administrateur Office 365, vous pouvez modifier les paramètres d’Audioconférence, tels que le fournisseur, le numéro payant ou gratuit par défaut, l’identifiant de conférence ou le code confidentiel — pour un utilisateur individuel dans votre organisation. Si vous souhaitez modifier les paramètres de votre organisation, consultez la rubrique [Gérer les paramètres d’Audioconférence de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Dans le Centre d’administration de Skype Entreprise, sélectionnez **Utilisateurs**.
    
4. Sélectionnez l’utilisateur pour lequel vous souhaitez gérer les paramètres, puis cliquez, dans le volet Actions, sur **Modifier**![Affiche l’icône Modifier](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Choisissez **Audioconférence** dans le volet de navigation gauche, puis, dans la page **Propriétés** de l’utilisateur, modifiez une des options suivantes :
    
|**Paramètre**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/><br/> **Remarque :** Les paramètres restants dans ce tableau s’appliquent uniquement si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.           |
|**Numéro de téléphone payant par défaut** (obligatoire) <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Présentez les numéros de la manière dont vous voulez qu’ils apparaissent dans les demandes de réunion Skype Entreprise et Microsoft Teams.  <br/> |
|**Numéro gratuit par défaut** <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Présentez les numéros de la manière dont vous voulez qu’ils apparaissent dans les demandes de réunion Skype Entreprise et Microsoft Teams.  <br/> |
|**Autoriser l’utilisation de numéros de téléphone gratuits dans le pont Microsoft de votre organisation pour rejoindre les réunions de cet utilisateur** <br/> |Sélectionnez cette option si vous souhaitez permettre l’utilisation de numéros de téléphone gratuits pour rejoindre des réunions.  <br/> |
|**Envoyer les informations de conférence par courrier électronique** <br/> |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son identifiant de conférence et son numéro de téléphone. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Identifiant de conférence** <br/> |Sélectionnez **Rétablir** si vous avez besoin de réinitialiser l’identifiant de conférence pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser un identifiant de conférence pour un utilisateur](reset-a-conference-id-for-a-user.md).  <br/> |
|**Code confidentiel** <br/> |Sélectionnez **Rétablir** si vous avez besoin de réinitialiser le code confidentiel pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin.md).  <br/> |
|**Autoriser les appelants non authentifiés à être les premiers à une réunion** <br/> |Sélectionnez cette option pour autoriser les appelants non authentifiés à rejoindre des réunions en premier.  <br/> |
|**Restrictions pour les appels sortants depuis les réunions de cet utilisateur** <br/> |Sélectionnez une option dans cette liste si vous souhaitez restreindre les appels sortants aux appels nationaux uniquement, ou si vous souhaitez empêcher tous les appels sortants issus de réunions.  <br/> |
  
![Affiche la page de propriétés Audioconférence d’un utilisateur](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
