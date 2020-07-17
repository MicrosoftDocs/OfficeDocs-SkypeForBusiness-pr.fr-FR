---
title: Gestion des paramètres de conférence audio d’un utilisateur dans Skype entreprise Online
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'En tant qu’administrateur Microsoft 365 ou Office 365, vous pouvez modifier les paramètres de conférence rendez-vous de Skype entreprise Online, tels que le fournisseur, le numéro payant ou le numéro gratuit par défaut, l’ID de conférence ou le code confidentiel, pour un utilisateur individuel au sein de votre organisation. '
ms.openlocfilehash: 47ad2b0d6b5684d2a897055ad43e253e55c67109
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943847"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gestion des paramètres de conférence audio d’un utilisateur dans Skype entreprise Online

> [!Note]
> Pour gérer les paramètres d’utilisateur dans Microsoft Teams, voir [gérer les paramètres d’audioconférence pour un utilisateur de Microsoft teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

En tant qu’administrateur Microsoft 365 ou Office 365, vous pouvez modifier les paramètres de l’audioconférence, tels que le fournisseur, le numéro payant ou le numéro gratuit par défaut, l’ID de conférence ou le code confidentiel, pour un utilisateur individuel de votre organisation. Si vous souhaitez modifier les paramètres de votre organisation, voir [gérer les paramètres d’audioconférence pour ma société](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Dans le centre d’administration de Skype entreprise, sélectionnez **utilisateurs**.
    
4. Sélectionnez l’utilisateur pour lequel vous souhaitez gérer les paramètres, puis cliquez, dans le volet Actions, sur **Modifier**![Affiche l’icône Modifier](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Choisissez **Audioconférence** dans le volet de navigation gauche, puis, dans la page **Propriétés** de l’utilisateur, modifiez une des options suivantes :
    
|**Paramètres**|**Description**|
|:-----|:-----|
|**Nom du fournisseur** <br/> |Dans la liste, choisissez votre fournisseur.  <br/><br/> **Remarque :** Les paramètres restants dans ce tableau s’appliquent uniquement si vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence.           |
|**Numéro de téléphone payant par défaut** (obligatoire) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Numéro gratuit par défaut** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Autoriser l’utilisation de numéros de téléphone gratuits dans le pont Microsoft de votre organisation pour rejoindre les réunions de cet utilisateur** <br/> |Sélectionnez cette option si vous souhaitez permettre l’utilisation de numéros de téléphone gratuits pour rejoindre des réunions.  <br/> |
|**Envoyer les informations sur la Conférence par courrier électronique** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID de conférence** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**ÉPINGL** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Autoriser les appelants non authentifiés à être les premiers à une réunion** <br/> |Sélectionnez cette option pour autoriser les appelants non authentifiés à rejoindre des réunions en premier.  <br/> |
|**Restrictions pour les appels sortants depuis les réunions de cet utilisateur** <br/> |Sélectionnez une option dans cette liste si vous souhaitez restreindre les appels sortants aux appels nationaux uniquement, ou si vous souhaitez empêcher tous les appels sortants issus de réunions.  <br/> |
  
![Affiche la page de propriétés Audioconférence d’un utilisateur](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Sujets associés

[Gestion des paramètres d'audioconférence de mon organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
