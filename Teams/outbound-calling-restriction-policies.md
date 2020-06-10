---
title: Restrictions des appels sortants-audioconférence & appels RTC
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Les administrateurs peuvent contrôler le type de conférence audio et d'appels RTC d’utilisateur final pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: ca4b7920ccad27a9434cbd1e5f76d7d10c4f4612
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665906"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs

En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation. 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|Télécommande|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels RTC de conférence audio|Limite le type de sortie </br>les appels autorisés de l'intérieur </br>réunions organisées par un utilisateur.|Toute destination (par défaut)</br>Dans le même pays ou la même région que le organizor </br> </br>Zonage uniquement dans les pays ou régions </br>Ne pas autoriser|
|Appels RTC utilisateur final|Limite le type d'appels </br>qui peuvent être effectués par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|

Pour connaître les pays/régions qui sont considérés comme la zone A, consultez [la rubrique zone a pays/régions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).

   > [!NOTE]
   > Un appel est considéré comme domestique si le numéro composé est dans le même pays que Microsoft 365 ou Office 365 a été configuré pour l’organisateur de la réunion (dans le cas d’une audioconférence) ou par l’utilisateur final (dans le cas d’appels RTC de l’utilisateur final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restreindre les appels sortants de conférence audio 

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. A côté de **Conférence Audio**, cliquez sur **Modifier**.

4. Sous **Autorisation d’appel sortant de réunions**, sélectionnez l’option de restriction d’appel sortant souhaitée.

5. Cliquez sur **Enregistrer**. 

![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

1.    Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, sélectionnez utilisateurs de l' **audioconférence**  >  **Users**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2.    Dans le volet Action, cliquez sur **Modifier**.

3.    Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.

    ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)

5. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser PowerShell**

Les restrictions des appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun. La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres. 

Vous pouvez utiliser la cmdlet Get-CSOnlineDialOutPolicy pour afficher les stratégies d'appels sortants et les affecter aux utilisateurs à l'aide de la cmdlet Grant-CSDialOutPolicy. (Veuillez noter que la cmdlet Grant ne contient pas le mot « Online » en tant que cmdlet Get.) 

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
|    Identity = 'tag : DialoutCPCZoneAPSTNInternational'    |    Dans la Conférence, l’utilisateur peut uniquement appeler les pays et régions d’un pays ou d’une région, et cet utilisateur peut passer des appels sortants vers des numéros internationaux et nationaux.    |
|    Identity = 'tag : DialoutCPCZoneAPSTNDomestic'    |    Dans la Conférence, l’utilisateur peut uniquement appeler des pays et des régions, et cet utilisateur ne peut émettre des appels sortants que vers son numéro RTC local.    |
|    Identity = 'tag : DialoutCPCZoneAPSTNDisabled'    |    Dans la Conférence, l’utilisateur peut uniquement appeler des pays et des régions, et cet utilisateur ne peut pas passer d’appels sortants au numéro RTC en plus des numéros d’urgence.    |
