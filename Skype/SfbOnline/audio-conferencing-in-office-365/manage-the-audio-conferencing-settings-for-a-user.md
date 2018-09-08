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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'En tant qu’administrateur Office 365, vous pouvez modifier les paramètres de l’audioconférence Skype Entreprise Online — tels que le fournisseur, le numéro payant ou gratuit par défaut, l’identifiant de conférence ou le code confidentiel — pour un utilisateur individuel dans votre organisation. '
ms.openlocfilehash: 06fd99987df725e235f308af20542fa45b0286fd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886400"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gérer les paramètres de conférence Audio pour un utilisateur dans Skype pour Business en ligne

> [!Note]
> Si vous souhaitez gérer les paramètres utilisateur dans Microsoft Teams, voir [Gérer les paramètres de conférence Audio pour un utilisateur dans les équipes Microsoft](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

En tant qu’administrateur Office 365, vous pouvez modifier les paramètres d’Audioconférence, tels que le fournisseur, le numéro payant ou gratuit par défaut, l’identifiant de conférence ou le code confidentiel — pour un utilisateur individuel dans votre organisation. Si vous souhaitez modifier les paramètres de votre organisation, voir [Gérer les paramètres de conférence Audio de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Dans Skype entreprise centre d’administration, choisissez **utilisateurs**.
    
4. Sélectionnez l’utilisateur pour lequel vous souhaitez gérer les paramètres, puis cliquez, dans le volet Actions, sur **Modifier**![Affiche l’icône Modifier](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Choisissez **Audioconférence** dans le volet de navigation gauche, puis, dans la page **Propriétés** de l’utilisateur, modifiez une des options suivantes :
    
|**Paramètre**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/><br/> **Remarque :** Les paramètres restants dans ce tableau s’appliquent uniquement si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.           |
|**Numéro de téléphone payant par défaut** (obligatoire) <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Numéro gratuit par défaut** <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.  <br/> |
|**Autoriser l’utilisation de numéros de téléphone gratuits dans le pont Microsoft de votre organisation pour rejoindre les réunions de cet utilisateur** <br/> |Sélectionnez cette option si vous souhaitez permettre l’utilisation de numéros de téléphone gratuits pour rejoindre des réunions.  <br/> |
|**Envoyer les informations de conférence par courrier électronique** <br/> |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son identifiant de conférence et son numéro de téléphone. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID de conférence** <br/> |Sélectionnez **Rétablir** si vous avez besoin de réinitialiser l’identifiant de conférence pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser un identifiant de conférence pour un utilisateur](reset-a-conference-id-for-a-user.md).  <br/> |
|**CODE CONFIDENTIEL** <br/> |Sélectionnez **Rétablir** si vous avez besoin de réinitialiser le code confidentiel pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin.md).  <br/> |
|**Autoriser les appelants non authentifiés à être les premiers à une réunion** <br/> |Sélectionnez cette option pour autoriser les appelants non authentifiés à rejoindre des réunions en premier.  <br/> |
|**Restrictions pour les appels sortants depuis les réunions de cet utilisateur** <br/> |Sélectionnez une option dans cette liste si vous souhaitez restreindre les appels sortants aux appels nationaux uniquement, ou si vous souhaitez empêcher tous les appels sortants issus de réunions.  <br/> |
  
![Affiche la page de propriétés Audioconférence d’un utilisateur](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
