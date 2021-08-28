---
title: Gérer les paramètres d’audioconférence d’un utilisateur dans Skype Entreprise Online
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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'En tant qu’administrateur Microsoft 365 ou Office 365, vous pouvez modifier les paramètres d’audioconférence Skype Entreprise Online (fournisseur, numéro gratuit ou gratuit par défaut, ID de conférence ou code confidentiel) pour un utilisateur de votre organisation. '
ms.openlocfilehash: 7f25df3c9f395583273a4bf8ce68f3c93699a41d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614946"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gérer les paramètres d’audioconférence d’un utilisateur dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si vous voulez gérer les paramètres utilisateur dans Microsoft Teams, consultez Gérer les paramètres d’audioconférence d’un utilisateur [dans Microsoft Teams.](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)

En tant qu’administrateur Microsoft 365 ou Office 365, vous pouvez modifier les paramètres d’audioconférence (fournisseur, numéro gratuit ou gratuit par défaut, ID de conférence ou code confidentiel) pour un utilisateur de votre organisation. Si vous voulez modifier les paramètres de votre organisation, consultez Gérer les [paramètres d’audioconférence pour mon organisation.](manage-the-audio-conferencing-settings-for-my-organization.md)

 
1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Dans le Skype Entreprise d’administration, sélectionnez **Utilisateurs.**
    
4. Sélectionnez l’utilisateur pour lequel vous souhaitez gérer les paramètres, puis cliquez, dans le volet Actions, sur **Modifier**![Affiche l’icône Modifier](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Choisissez **Audioconférence** dans le volet de navigation gauche, puis, dans la page **Propriétés** de l’utilisateur, modifiez une des options suivantes :
    
|**Paramètres**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Choisissez votre fournisseur dans la liste.  <br/><br/> **Remarque :** Les paramètres restants dans ce tableau s’appliquent uniquement si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.           |
|**Numéro de téléphone payant par défaut** (obligatoire) <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les nombres de la même forme que vous voulez qu’ils apparaissent Skype Entreprise et Microsoft Teams des réunions.  <br/> |
|**Numéro gratuit par défaut** <br/> |Pour des fournisseurs tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur d’audioconférence. Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence. Mettre en forme les nombres de la même forme que vous voulez qu’ils apparaissent Skype Entreprise et Microsoft Teams des réunions.  <br/> |
|**Autoriser l’utilisation de numéros de téléphone gratuits dans le pont Microsoft de votre organisation pour rejoindre les réunions de cet utilisateur** <br/> |Sélectionnez cette option si vous souhaitez permettre l’utilisation de numéros de téléphone gratuits pour rejoindre des réunions.  <br/> |
|**Envoyer les informations sur la conférence par courrier électronique** <br/> |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son identifiant de conférence et son numéro de téléphone. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
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
