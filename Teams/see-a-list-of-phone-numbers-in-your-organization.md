---
title: Afficher la liste des numéros de téléphone de votre organisation
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
description: Apprenez à utiliser le Centre d’administration Microsoft Teams pour afficher la liste de tous les numéros de téléphone de votre organisation et de tous les numéros affectés aux utilisateurs ou non affectés.
ms.openlocfilehash: a0c5bf59d4ebf2d760ae6c8b4abb6c70e3e3ebb7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551848"
---
# <a name="see-a-list-of-telephone-numbers"></a>Afficher la liste des numéros de téléphone 

Il existe différents types de numéros de téléphone que vous pouvez affecter aux utilisateurs ou aux applications vocales telles que [l’audioconférence](deploy-audio-conferencing-teams-landing-page.md) ou [les files d’attente d’appels](plan-auto-attendant-call-queue.md). Pour plus d’informations, consultez [Gérer les numéros de téléphone de votre organisation](/microsoftteams/manage-phone-numbers-landing-page).

Cet article s’applique aux forfaits d’appels, à Operator Connect et à Teams Phone Mobile. Pour plus d’informations sur le routage direct, consultez [Configurer le numéro de téléphone et activer la voix d’entreprise](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Pour afficher tous les numéros de téléphone de votre organisation

Pour afficher la liste de tous les numéros de téléphone de votre organisation :

1. Accédez au **Centre d’administration Microsoft Teams**.

2. Dans le volet de navigation gauche, accédez aux **numéros de téléphone** **vocal** > .

3. Pour afficher les numéros de téléphone affectés, consultez la colonne **État de l’affectation** , qui indique également le type de service auquel le numéro est affecté.

4. Pour filtrer votre affichage, cliquez sur l’icône de filtre. Dans le volet **Filtre** , vous pouvez utiliser la liste déroulante pour filtrer votre affichage par :

   - **Plage de nombres** que vous définissez. Vous pouvez effectuer une recherche par nombre le plus bas ou le plus élevé.

   - Nombres qui commencent par un nombre que vous spécifiez.

   - **État d’activation du nombre**.

   - **Type de nombre**.

   - **État** du numéro de téléphone.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Pour afficher tous les numéros de téléphone affectés aux utilisateurs

Lorsque vous configurez des utilisateurs, vous souhaiterez peut-être simplement afficher la liste des numéros de téléphone qui sont déjà affectés aux utilisateurs et les numéros de téléphone qui peuvent leur être affectés.

1. Accédez au **Centre d’administration Microsoft Teams**.

2. Dans le volet de navigation gauche, accédez aux **numéros de téléphone** **vocal** > .

    > [!IMPORTANT]
    > Pour que vous voyiez l’option **Voix** dans la navigation de gauche dans le Centre d’administration Microsoft Teams, vous devez d’abord acheter au moins une **licence Entreprise E5**, une licence de module complémentaire **Système téléphonique** ou une licence de module complémentaire **AudioConférence** .

3. Pour trier rapidement les nombres afin de voir quels sont les numéros attribués, cliquez sur l’en-tête de colonne **État de l’affectation** . Vous pouvez également cliquer sur l’icône de filtre, puis filtrer votre affichage pour afficher les numéros de téléphone qui sont déjà affectés à des utilisateurs ou des numéros non attribués que vous pouvez affecter à un utilisateur. Vous pouvez filtrer par :

   - **Affecté à l’utilisateur**
   - **Affecté au pont de conférence** 
   - **Affecté à l’application Voix (Standard automatique/File d’attente d’appels)**
   - **Non affecté**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Pour afficher tous les numéros de téléphone affectés aux utilisateurs vocaux

Lorsque vous configurez des utilisateurs de votre organisation pour passer et recevoir des appels téléphoniques, vous devez d’abord obtenir les numéros de téléphone, puis les affecter à vos utilisateurs. Une fois que vous avez obtenu vos numéros de téléphone, vous souhaiterez peut-être voir l’état d’activation des affectations de numéros.
  
1. Accédez au **Centre d’administration Microsoft Teams**.

2. Dans le volet de navigation gauche, accédez aux **numéros de téléphone** **vocal** > .

3. Cliquez sur l’icône de filtre pour filtrer votre affichage par **état d’activation**. Vous pouvez filtrer par :

   - **Activé**
   - **Affectation en attente**
   - **Échec de l’affectation**
   - **Mise à jour en attente**
   - **Échec de la mise à jour**

## <a name="using-the-teams-powershell-module"></a>Utilisation du module Teams PowerShell

Vous pouvez utiliser le module Teams PowerShell pour obtenir les mêmes informations que les sections précédentes, mais la version 1.1.6 ou ultérieure est requise, ce qui inclut l’intégration du connecteur Skype Entreprise Online. Pour plus d’informations sur le module, consultez [La vue d’ensemble de Microsoft Teams PowerShell](teams-powershell-overview.md).

Pour afficher la liste de tous les numéros de téléphone dont vous disposez pour votre organisation, utilisez l’applet de commande [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) . Par exemple, pour afficher chaque numéro de téléphone, son type et son état, exécutez la commande suivante :

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

Pour afficher tous les numéros de téléphone affectés aux utilisateurs, utilisez l’applet de commande [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) . Par exemple, pour voir tous les utilisateurs avec un numéro de téléphone attribué, exécutez la commande suivante :

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Rubriques connexes

[Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
