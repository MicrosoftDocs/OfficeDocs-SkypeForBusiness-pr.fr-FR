---
title: Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type de conférence audio et d'appels RTC d’utilisateur final pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: 20122d2bc258b8ac6040a103d62e20f81e46a364
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573330"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs

En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation. 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|Télécommande|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels RTC de conférence audio|Limite le type de sortie </br>les appels autorisés de l'intérieur </br>réunions organisées par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|
|Appels RTC utilisateur final|Limite le type d'appels </br>qui peuvent être effectués par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|

   > [!NOTE]
   > Un appel est considéré comme domestique si le numéro composé est dans le même pays que celui où Office 365 a été configuré pour l’organisateur de la réunion (dans le cas d’une audioconférence) ou l’utilisateur final (dans le cas d’appels RTC de l’utilisateur final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restreindre les appels sortants de conférence audio 

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. A côté de **Conférence Audio**, cliquez sur **Modifier**.

4. Sous **Autorisation d’appel sortant de réunions**, sélectionnez l’option de restriction d’appel sortant souhaitée.

5. Cliquez sur **Enregistrer**. 

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**

1.  Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, sélectionnez**utilisateurs**de l' **audioconférence** > , puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2.  Dans le volet Action, cliquez sur **Modifier**.

3.  Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.

    ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)

5. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser PowerShell**

Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings. 

You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.) 

Le tableau suivant fournit une vue d’ensemble de chaque stratégie.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.    |
|    Identité = 'tag : DialoutCPCDisabledPSTNInternational'    |    L'utilisateur de la conférence ne peut effectuer aucun appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur peut uniquement effectuer des appels sortants vers des numéros RTC nationaux.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    L'utilisateur de la conférence ne peut effectuer aucun appel sortant et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.    |
