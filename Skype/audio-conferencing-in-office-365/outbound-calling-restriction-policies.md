---
title: Stratégies de restriction appel sortant pour les appels PSTN utilisateur et de conférence Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type d’appels audio d’utilisateur final et de conférence PSTN qui peuvent être effectuées par les utilisateurs.
ms.openlocfilehash: ae6039f967b95ebd0c5934105f4e6fb044e431b4
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction appel sortant pour les appels PSTN utilisateur et de conférence Audio

En tant qu’administrateur, vous pouvez utiliser des contrôles d’appel sortant pour restreindre le type d’appels audio d’utilisateur final et de conférence PSTN qui peuvent être effectuées par les utilisateurs de votre organisation. 

Contrôles d’appel sortant peuvent être appliquées par utilisateur et fournissent deux contrôles suivants pour limiter l’accès indépendamment chaque type d’appels sortants. Par défaut, les deux contrôles sont configurés pour autoriser les appels sortants et internationales. 

|Contrôle|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels audio de conférence PSTN|Limite le type de sortie </br>appels qui sont autorisés à partir </br>réunions organisées par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|
|Appels PSTN utilisateur final|Restreint les types d’appels </br>qui peut être effectué par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|

   > [!NOTE]
   > Un appel est déterminé à l’intérieur si le numéro de téléphone appelé se trouve dans le même pays que celui qui a été défini dans Office 365 pour l’organisateur de la réunion (dans le cas des services d’audioconférence) ou de l’utilisateur final (dans le cas d’utilisateurs finaux des appels PSTN). 


## <a name="restrict-audio-conferencing-outbound-calls-using-the-skype-for-business-admin-center"></a>Restreindre les appels sortants de conférence audio à l’aide de la Skype entreprise centre d’administration 


1.  Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
2.  Dans la Skype pour la navigation de gauche, du centre d’administration Business, accédez à la **conférence Audio** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.
3.  Dans le volet Action, cliquez sur **Modifier**.
4.  Sous **Restrictions de numérotation issus de réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant.

    ![Les Restrictions sur les options de numérotation-outs](../images/restrictions-to-dial-outs.png)

5. Cliquez sur **Enregistrer**.

## <a name="restrict-audio-conferencing-and-end-user-outbound-calls-using-powershell"></a>Restreindre l’audio conférence et utilisateur final les appels sortants à l’aide de PowerShell

Restrictions des appels sortants sont contrôlées par une seule stratégie appelée OnlineDialOutPolicy qui possède un attribut de restriction pour chacun. La stratégie ne peuvent pas être personnalisée, au lieu de cela, il existe des instances de stratégie prédéfinies pour chaque combinaison des paramètres. 

Vous pouvez utiliser l’applet de commande Get-CSOnlineDialOutPolicy pour afficher les stratégies d’appel sortants et les attribuer aux utilisateurs à l’aide de l’applet de commande Grant-CSDialOutPolicy. (Notez que l’applet de commande Grant ne contient pas le mot « Online » comme l’applet de commande Get). 

Le tableau suivant fournit une vue d’ensemble de chaque stratégie.

|||
|:-----|:-----|
|Identité = 'tag : DialoutCPCandPSTNInternational'    |    Utilisateur à la conférence peut appeler des numéros et internationales, et cet utilisateur peut aussi passer des appels sortants vers des numéros et internationales.    |
|Identité = 'tag : DialoutCPCDomesticPSTNInternational'  |    Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur peut effectuer des appels sortants vers des numéros et internationales.    |
|    Identité = 'tag : DialoutCPCDisabledPSTNInternational'    |    Utilisateur à la conférence ne peut pas réaliser toute numérotation. Cet utilisateur peut effectuer des appels sortants vers des numéros et internationales.    |
|    Identité = 'tag : DialoutCPCInternationalPSTNDomestic'    |    Utilisateur à la conférence peut appeler des numéros et internationales et cet utilisateur peut uniquement établir des appels sortants vers un numéro RTC nationale.    |
|    Identité = 'tag : DialoutCPCInternationalPSTNDisabled'    |    Utilisateur à la conférence peut appeler des numéros et internationales et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
|    Identité = 'tag : DialoutCPCandPSTNDomestic'    |    Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur peut uniquement établir des appels sortants vers les numéros RTPC nationales.    |
|    Identité = 'tag : DialoutCPCDomesticPSTNDisabled'    |    Utilisateur de la conférence peut appeler uniquement des numéros nationaux et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
|    Identité = 'tag : DialoutCPCDisabledPSTNDomestic'    |    Utilisateur à la conférence ne peut pas émettre des appels sortants, et cet utilisateur peut uniquement établir des appels sortants vers les numéros RTPC nationales.    |
|    Identité = 'tag : DialoutCPCandPSTNDisabled'    |    Utilisateur à la conférence ne peut pas émettre des appels sortants, et cet utilisateur ne peut pas émettre des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
