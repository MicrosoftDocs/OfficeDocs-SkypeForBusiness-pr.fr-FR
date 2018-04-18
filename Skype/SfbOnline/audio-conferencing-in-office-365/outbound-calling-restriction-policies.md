---
title: Stratégies de restriction appel sortant pour les appels RTPC Audio conférence et l’utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Les administrateurs peuvent contrôler le type d’utilisateur final et conférence PSTN appels audio pouvant être effectuées par les utilisateurs.
ms.openlocfilehash: a842366a5788de960cf5f0338219903ebe3d93f7
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction appel sortant pour les appels RTPC Audio conférence et l’utilisateur

En tant qu’administrateur, vous pouvez utiliser des contrôles d’appels sortants pour restreindre le type d’utilisateur final et conférence PSTN appels audio pouvant être effectuées par les utilisateurs de votre organisation. 

Contrôles d’appel sortant peuvent être appliquées sur une base par utilisateur et fournissent les deux contrôles suivantes pour restreindre indépendamment de chaque type d’appels sortants. Par défaut, les deux contrôles sont configurés pour autoriser les appels sortants et internationales. 

|Contrôle|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels de conférence PSTN audio|Restreint les types de trafic sortant </br>appels qui sont autorisés à partir </br>réunions organisées par un utilisateur.|Internationale et nationale (par défaut)</br>Nationaux</br>Aucun|
|Appels RTPC utilisateur final|Restreint les types d’appels </br>qui peut être effectuée par un utilisateur.|Internationale et nationale (par défaut)</br>Nationaux</br>Aucun|

   > [!NOTE]
   > Un appel est déterminé à l’intérieur si le numéro de téléphone appelé est dans le même pays que le pays qui a été défini dans Office 365 pour l’organisateur de la réunion (dans le cas d’une conférence audio) ou par l’utilisateur (pour l’utilisateur final les appels RTPC). 


## <a name="restrict-audio-conferencing-outbound-calls"></a>Restreindre les appels sortants de conférence audio 

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.

4. Dans le volet de **fournisseur de pont de conférence** , sous **Restrictions de numérotation issus de réunions de cet utilisateur**, sélectionnez l’option de restriction d’appels sortants.

5. Cliquez sur **Appliquer**. 

Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.

1.  Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2.  Dans le volet Action, cliquez sur **Modifier**.

3.  Sous **Restrictions de numérotation issus de réunions de cet utilisateur**, sélectionnez l’option de restriction d’appels sortants.

    ![Les Restrictions aux options de sorties à distance](../images/restrictions-to-dial-outs.png)

5. Cliquez sur **Enregistrer**.

**Utilisation de PowerShell**

Restrictions d’appel sortant sont contrôlées par une stratégie unique, appelée OnlineDialOutPolicy, qui a un attribut de restriction pour chacune. La stratégie ne peuvent pas être personnalisée, au lieu de cela, il existe des instances de stratégies prédéfinies pour chaque combinaison de paramètres des. 

Vous pouvez utiliser l’applet de commande Get-CSOnlineDialOutPolicy pour afficher les politiques d’appel sortants et les affecter aux utilisateurs à l’aide de l’applet de commande Grant-CSDialOutPolicy. (Notez que l’applet de commande Grant ne contient pas le mot « En ligne » comme le fait l’applet de commande Get). 

Le tableau suivant fournit une vue d’ensemble de chaque stratégie.

|||
|:-----|:-----|
|Identité = 'balise : DialoutCPCandPSTNInternational'    |    Utilisateur de la conférence peut appeler des numéros internationaux et nationaux, et cet utilisateur permettent également les appels sortants vers les numéros internationaux et nationaux.    |
|Identité = 'balise : DialoutCPCDomesticPSTNInternational'  |    Utilisateur à la conférence peut uniquement appeler des numéros nationaux, et que cet utilisateur peut effectuer des appels sortants vers les numéros internationaux et nationaux.    |
|    Identité = 'balise : DialoutCPCDisabledPSTNInternational'    |    Utilisateur à la conférence ne peut pas réaliser tout à distance. Cet utilisateur peut effectuer des appels sortants vers les numéros internationaux et nationaux.    |
|    Identité = 'balise : DialoutCPCInternationalPSTNDomestic'    |    Utilisateur de la conférence peut appeler des numéros internationaux et nationaux, et cet utilisateur peut effectuer uniquement des appels sortants vers un numéro RTC domestique.    |
|    Identité = 'balise : DialoutCPCInternationalPSTNDisabled'    |    Utilisateur de la conférence peut appeler des numéros internationaux et nationaux, et que cet utilisateur ne peut pas effectuer des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
|    Identité = 'balise : DialoutCPCandPSTNDomestic'    |    Utilisateur à la conférence peut uniquement appeler des numéros nationaux, et cet utilisateur peut appeler uniquement sortant des numéros RTPC domestiques.    |
|    Identité = 'balise : DialoutCPCDomesticPSTNDisabled'    |    Utilisateur à la conférence peut uniquement appeler des numéros nationaux, et que cet utilisateur ne peut pas effectuer des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
|    Identité = 'balise : DialoutCPCDisabledPSTNDomestic'    |    Utilisateur à la conférence ne peut pas effectuer les appels sortants, et cet utilisateur peut appeler uniquement sortant des numéros RTPC domestiques.    |
|    Identité = 'balise : DialoutCPCandPSTNDisabled'    |    Utilisateur à la conférence ne peut pas effectuer les appels sortants, et que cet utilisateur ne peut pas effectuer des appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
