---
title: Restrictions relatives aux appels sortants - Audioconférence & appels RTC
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.service: msteams
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Les administrateurs peuvent contrôler le type d’audioconférence et les appels RTC des utilisateurs finaux qui peuvent être effectués par les utilisateurs.
ms.openlocfilehash: 67c138db8522ec6eee1f384e182f5c8d01ea40fd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641765"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs

En tant qu’administrateur, vous pouvez utiliser des contrôles d’appel sortants pour limiter le type d’appels d’audioconférence et de réseau téléphonique commuté (RTC) des utilisateurs finaux qui peuvent être effectués par des utilisateurs de votre organisation.

Les contrôles d’appel sortant peuvent être appliqués par utilisateur ou par locataire et fournissent les deux contrôles suivants pour restreindre indépendamment chaque type d’appels sortants. Par défaut, les deux contrôles sont définis pour autoriser les appels sortants internationaux et nationaux.

|Contrôle|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels RTC de conférence audio|Limite le type de sortie </br>les appels autorisés de l'intérieur </br>réunions organisées par un utilisateur.|N’importe quelle destination (par défaut)</br>Dans le même pays ou région que l’organisateur </br> [Zone A pays ou régions](audio-conferencing-zones.md) uniquement </br>Ne pas autoriser|
|Appels PSTN de l’utilisateur final|Limite le type d'appels </br>qui peuvent être effectués par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|

Pour savoir quels pays et régions sont considérés comme la zone A, consultez [Zones de pays et de régions pour l’audioconférence](audio-conferencing-zones.md).

   > [!NOTE]
   > Un appel est considéré comme national si le numéro composé se trouve dans le pays où Microsoft 365 ou Office 365 a été configuré pour l’organisateur de la réunion (dans le cas de l’audioconférence) ou l’utilisateur final (dans le cas des appels RTC de l’utilisateur final).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restreindre les appels sortants de conférence audio

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, sélectionnez **Utilisateurs**, puis sélectionnez le nom complet de l’utilisateur dans la liste des utilisateurs disponibles.

2. Ensuite, accédez à **l’audioconférence**, **sélectionnez Modifier**.

3. Sous **Numérotation à partir de réunions**, sélectionnez l’option de restriction de numérotation souhaitée.

4. Sélectionnez **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Les restrictions d’appel sortant sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy, qui a un attribut de restriction pour chacune d’elles. La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.

Vous pouvez utiliser l’applet de commande Get-CSOnlineDialOutPolicy pour afficher les stratégies d’appel sortant et utiliser la commande suivante pour l’installation.

**Définissez la stratégie au niveau de l’utilisateur avec l’applet de commande suivante**. (L’applet de commande Grant ne contient pas le mot « Online » comme l’applet de commande Get.)

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Définissez la stratégie au niveau du locataire avec l’applet de commande suivante**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Tous les utilisateurs du locataire qui n’ont pas de stratégie de numérotation affectée recevront cette stratégie. Les autres utilisateurs conservent leur stratégie actuelle.

**Vérifiez la stratégie actuelle au niveau du locataire avec l’applet de commande suivante**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

Le tableau suivant fournit une vue d’ensemble de chaque stratégie.

|Applet de commande PowerShell|Description|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.    |
|    Identité = 'tag : DialoutCPCDisabledPSTNInternational'    |    L’utilisateur de la conférence ne peut pas composer. Cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    L’utilisateur de la conférence ne peut pas composer et cet utilisateur peut uniquement effectuer un appel sortant vers des numéros RTC nationaux.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    L’utilisateur de la conférence ne peut pas composer et cet utilisateur ne peut pas effectuer d’appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    L’utilisateur de la conférence peut uniquement composer des appels vers des [pays et régions de la zone A](audio-conferencing-zones.md), et cet utilisateur peut effectuer des appels sortants vers des numéros internationaux et nationaux.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    L’utilisateur de la conférence ne peut composer que vers les [pays et régions de la zone A](audio-conferencing-zones.md), et cet utilisateur peut uniquement effectuer des appels sortants vers un numéro RTC national.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    L’utilisateur de la conférence peut uniquement composer un numéro vers les [pays et régions de la zone A](audio-conferencing-zones.md), et cet utilisateur ne peut pas effectuer d’appels sortants vers un numéro RTC en plus des numéros d’urgence.    |
