---
title: Affichage de la liste des numéros de téléphone de votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
description: Découvrez comment utiliser le Microsoft Teams d’administration pour consulter la liste de tous les numéros de téléphone de votre organisation ainsi que ceux attribués à des utilisateurs ou non attribués.
ms.openlocfilehash: d7de480508020dac24a63b5923af9cf2481c691b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733973"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Affichage de la liste des numéros de téléphone de votre organisation

Il existe différents types de numéros de téléphone que vous pouvez affecter à des utilisateurs ou à d’autres services (numéros de service), comme pour l’audioconférence dans Microsoft 365 ou Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Pour obtenir une liste des numéros de téléphone disponibles pour votre organisation

![Icône représentant le logo Teams’affichage.](media/teams-logo-30x30.png) **Utiliser le centre d’administration Microsoft Teams**

1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

    > [!IMPORTANT]
    > Pour que l’option Voix s’offre à vous dans le navigation gauche du Centre d’administration Skype Entreprise,  vous devez d’abord acheter au moins une licence **Enterprise E5,** une licence de module Système téléphonique ou une licence de module ajout  **d’audioconférence.**

3. Pour afficher les numéros de téléphone affectés, consultez la **colonne** État.

4. Pour filtrer l’affichage, cliquez sur l’icône de filtre. Dans le **volet** Filtres, vous pouvez utiliser la liste de listes filtrées pour filtrer l’affichage en :

   - **Plage de nombres** que vous définissez. Vous pouvez effectuer une recherche par nombre inférieur ou élevé.

   - Nombres qui commencent par un nombre que vous spécifiez.

   - État **d’activation du numéro.**

   - Type **de nombre.**

   - Téléphone **d’état du numéro.**

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Pour afficher tous les numéros de téléphone affectés aux utilisateurs

Lors de la configuration des utilisateurs, vous souhaitez peut-être simplement voir la liste des numéros de téléphone déjà affectés à des utilisateurs et les numéros de téléphone disponibles pour leur être affectés.
  
![Icône représentant le logo Teams’affichage.](media/teams-logo-30x30.png) **Utiliser le centre d’administration Microsoft Teams**

1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

    > [!IMPORTANT]
    > Pour que l’option Voix s’offre à vous dans le navigation gauche du Centre d’administration Microsoft Teams,  vous devez tout d’abord acheter au moins une licence **Enterprise E5,** une licence de module Système téléphonique ou une licence de module ajout  **d’audioconférence.**

3. Pour trier rapidement les nombres afin de voir les numéros attribués, cliquez sur **l’en-tête** de colonne État. Vous pouvez également cliquer sur l’icône de filtre, puis filtrer l’affichage pour afficher les numéros de téléphone déjà attribués à des utilisateurs ou les numéros non attribués que vous pouvez affecter à un utilisateur. Vous pouvez filtrer par :

   - **Affecté à l’utilisateur**

   - **Affecté à un pont de conférence** 

   - **Non-signé**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Pour afficher les numéros de téléphone affectés aux utilisateurs Voix

Lorsque vous configurez des utilisateurs de votre organisation pour passer et recevoir des appels, vous devez d'abord obtenir les numéros de téléphone, puis les affecter aux utilisateurs. Une fois que vous avez obtenu vos numéros de téléphone, vous voudrez peut-être simplement voir l’état d’activation des affectations de numéro.

![Icône représentant le logo Teams’affichage.](media/teams-logo-30x30.png) **À l’Microsoft Teams centre d’administration de l’utilisateur** !
  
1. Allez dans le **Microsoft Teams d’administration.**

2. Dans le groupe de navigation de gauche, allez sur  >  **Numéros Téléphone voix.**

    > [!IMPORTANT]
    > Pour que l’option Voix s’offre à vous dans le navigation gauche du Centre d’administration Microsoft Teams,  vous devez tout d’abord acheter au moins une licence **Enterprise E5,** une licence de module Système téléphonique ou une licence de module ajout  **d’audioconférence.**

3. Cliquez sur l’icône de filtre pour filtrer votre affichage par état **d’activation.** Vous pouvez filtrer par :

   - **Activé**

   - **Devoir en attente**

   - **Échec du devoir**

   - **Mise à jour en attente**

   - **Échec de la mise à jour**

## <a name="using-the-teams-powershell-module"></a>Utilisation du module Teams PowerShell

Vous pouvez utiliser le module Teams PowerShell pour obtenir les mêmes informations à partir des sections précédentes, mais la version 1.1.6 ou ultérieure est requise, ce qui inclut l’intégration du connecteur Skype Entreprise Online. Pour plus d’informations sur le module, voir Microsoft Teams [vue d’ensemble de PowerShell.](teams-powershell-overview.md)

Vous pouvez consulter la liste de tous les numéros de téléphone que vous avez pour votre organisation à l’aide de l’cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Par exemple, vous pouvez exécuter la commande suivante pour voir chaque numéro de téléphone et leur état :

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Vous pouvez voir tous les numéros de téléphone affectés aux utilisateurs à l’aide de l’cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Par exemple, vous pouvez exécuter la commande suivante pour voir tous les utilisateurs avec un numéro de téléphone affecté :

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)