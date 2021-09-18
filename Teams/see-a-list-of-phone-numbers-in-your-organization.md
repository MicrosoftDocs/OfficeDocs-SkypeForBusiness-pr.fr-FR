---
title: Consulter la liste des numéros de téléphone de votre organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Découvrez comment utiliser le Centre Microsoft Teams d’administration pour consulter la liste de tous les numéros de téléphone de votre organisation ainsi que ceux affectés à des utilisateurs ou non attribués.
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432486"
---
# <a name="see-a-list-of-telephone-numbers"></a>Consulter la liste des numéros de téléphone 

Il existe différents types de numéros de téléphone que vous pouvez affecter à des utilisateurs ou à des applications vocales telles que [l’audioconférence](deploy-audio-conferencing-teams-landing-page.md) ou les [files d’attente d’appels.](plan-auto-attendant-call-queue.md) Pour plus d’informations, voir [Gérer les numéros de téléphone pour votre organisation.](/microsoftteams/manage-phone-numbers-landing-page)

Cet article s’applique aux forfaits d’appels et aux Connecter. Pour plus d’informations sur le routage direct, voir Configurer le numéro de téléphone et activer la messagerie vocale et [la voix pour les entreprises.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Pour voir tous les numéros de téléphone de votre organisation

Pour consulter la liste des numéros de téléphone de votre organisation :

1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

3. Pour afficher les numéros de téléphone  affectés, consultez la colonne État des affectations, qui indique également le type de service auquel le numéro est affecté.

4. Pour filtrer l’affichage, cliquez sur l’icône de filtre. Dans le **volet** Filtre, vous pouvez utiliser la liste de listes listes pour filtrer l’affichage par :

   - **Plage de nombres** que vous définissez. Vous pouvez effectuer une recherche par nombre inférieur ou élevé.

   - Nombres qui commencent par un nombre que vous spécifiez.

   - État **d’activation du numéro.**

   - Type **de nombre.**

   - Téléphone **d’état du numéro.**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Pour voir tous les numéros de téléphone affectés aux utilisateurs

Lors de la configuration des utilisateurs, vous souhaitez peut-être simplement voir la liste des numéros de téléphone déjà affectés à des utilisateurs et les numéros de téléphone disponibles pour leur être affectés.

1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

    > [!IMPORTANT]
    > Pour que l’option Voix s’offre à vous dans le navigation gauche du Centre d’administration Microsoft Teams,  vous devez tout d’abord acheter au moins une licence **Enterprise E5,** une licence de module Système téléphonique ou une licence de module ajout  **d’audioconférence.**

3. Pour trier rapidement les nombres afin de voir les numéros attribués, cliquez sur l’en-tête de **colonne** État du devoir. Vous pouvez également cliquer sur l’icône de filtre, puis filtrer l’affichage pour afficher les numéros de téléphone déjà affectés à des utilisateurs ou les numéros non attribués que vous pouvez affecter à un utilisateur. Vous pouvez filtrer par :

   - **Affecté à l’utilisateur**
   - **Affecté à un pont de conférence** 
   - **Affecté à l’application Voix (Standard automatique/File d’attente d’appels)**
   - **Non-signé**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Pour voir tous les numéros de téléphone affectés aux utilisateurs Voix

Lorsque vous affectez des utilisateurs de votre organisation à passer et recevoir des appels téléphoniques, vous devez d’abord obtenir les numéros de téléphone, puis les affecter à vos utilisateurs. Une fois que vous avez obtenu vos numéros de téléphone, vous voudrez peut-être voir l’état d’activation des affectations de numéro.
  
1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

3. Cliquez sur l’icône de filtre pour filtrer l’affichage par **état d’activation.** Vous pouvez filtrer par :

   - **Activé**
   - **Devoir en attente**
   - **Échec du devoir**
   - **Mise à jour en attente**
   - **Échec de la mise à jour**

## <a name="using-the-teams-powershell-module"></a>Utilisation du module Teams PowerShell

Vous pouvez utiliser le module Teams PowerShell pour obtenir les mêmes informations à partir des sections précédentes, mais la version 1.1.6 ou ultérieure est requise, ce qui inclut l’intégration du connecteur Skype Entreprise Online. Pour plus d’informations sur le module, voir Microsoft Teams [vue d’ensemble de PowerShell.](teams-powershell-overview.md)

Pour consulter la liste des numéros de téléphone de votre organisation, utilisez l’cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Par exemple, pour voir chaque numéro de téléphone et son état, exécutez la commande suivante :

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Pour voir tous les numéros de téléphone affectés aux utilisateurs, utilisez l’cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Par exemple, pour voir tous les utilisateurs à qui un numéro de téléphone est affecté, exécutez la commande suivante :

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Sujets associés

[Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-landing-page.md)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)