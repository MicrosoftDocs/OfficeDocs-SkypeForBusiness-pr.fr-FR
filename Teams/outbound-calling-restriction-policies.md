---
title: Restrictions relatives aux appels sortants - Audioconférence et & appels PSTN
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Les administrateurs peuvent contrôler le type d’audioconférence et d’appels PSTN d’utilisateur final qui peuvent être effectués par les utilisateurs.
ms.openlocfilehash: 9e7f656cd51131237507cc184e021128a33d9268
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598408"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs

En tant qu’administrateur, vous pouvez utiliser les contrôles d’appel sortant pour restreindre le type d’audioconférence et les appels de réseau téléphonique public commuté (PSTN) d’utilisateurs finaux qui peuvent être effectués par les utilisateurs de votre organisation.

Les contrôles d’appel sortant peuvent être appliqués pour chaque utilisateur ou client et fournir les deux contrôles suivants afin de limiter de manière indépendante chaque type d’appels sortants. Par défaut, les deux contrôles sont définis pour autoriser les appels sortants internationaux et nationaux.

|Contrôle|Description|Options de contrôle|
|:-----|:-----|:-----|
|Appels RTC de conférence audio|Limite le type de sortie </br>les appels autorisés de l'intérieur </br>réunions organisées par un utilisateur.|N’importe quelle destination (par défaut)</br>Dans le même pays ou la même région que l’organisateur </br> [Zone A pays ou régions](audio-conferencing-zones.md) uniquement </br>Ne pas autoriser|
|Appels PSTN d’utilisateur final|Limite le type d'appels </br>qui peuvent être effectués par un utilisateur.|International et national (par défaut)</br>Nationaux</br>Aucun|

Pour savoir quels pays et quelles régions sont considérés comme zone A, consultez les zones pays et région pour [l’audioconférence.](audio-conferencing-zones.md)

   > [!NOTE]
   > Un appel est considéré comme national si le numéro composé se trouve dans le pays dans lequel Microsoft 365 ou Office 365 a été définie pour l’organisateur de la réunion (en cas d’audioconférence) ou l’utilisateur final (en cas d’appels PSTN de l’utilisateur final).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restreindre les appels sortants de conférence audio

![Logo Microsoft Teams’aide ](media/teams-logo-30x30.png) **du Centre d’Microsoft Teams’administration**

1. Dans la barre de navigation de gauche, **sélectionnez** Utilisateurs, puis le nom d’affichage de l’utilisateur dans la liste des utilisateurs disponibles.

3. En plus de **l’audioconférence,** sélectionnez **Modifier.**

4. Sous **Appel sortant de réunions,** sélectionnez l’option de restriction d’appel sortant de votre choix.

5. Sélectionnez **Enregistrer**.

![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

1. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, sélectionnez Utilisateurs de l’audioconférence, puis sélectionnez l’utilisateur dans la liste   >  des utilisateurs disponibles.

2. Dans le volet Action, sélectionnez **Modifier.**

3.  Sous **Restrictions de numérotation des réunions de cet utilisateur**, sélectionnez l’option de restriction d’appel sortant souhaitée.

      ![Les restrictions aux options de numérotation](media/restrictions-to-dial-outs.png)

4. Sélectionnez **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser PowerShell**

Les restrictions d’appels sortants sont contrôlées par une stratégie unique appelée OnlineDialOutPolicy, qui possède un attribut de restriction pour chacune d’elles. La stratégie ne peut pas être personnalisée, mais il existe des instances de stratégie prédéfinies pour chaque combinaison de paramètres.

Vous pouvez utiliser l'Get-CSOnlineDialOutPolicy cmdlet pour afficher les stratégies d’appels sortants et utiliser la commande suivante pour la configuration.

**Définissez la stratégie au niveau utilisateur avec l’cmdlet suivante.** (La cmdlet Grant ne contient pas le mot « En ligne » comme le fait la cmdlet Get.)

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Définissez la stratégie au niveau du client avec l’cmdlet suivante.**

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

Cette stratégie est attribuée à tous les utilisateurs du client qui n’ont pas de stratégie de numérotation. Les autres utilisateurs demeurent avec leur stratégie actuelle.

Le tableau suivant fournit une vue d’ensemble de chaque stratégie.

|Cmdlet PowerShell|Description|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur peut également passer des appels vers des numéros internationaux et nationaux.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux et cet utilisateur peut passer des appels vers des numéros internationaux et nationaux.    |
|    Identité = 'tag : DialoutCPCDisabledPSTNInternational'    |    Les utilisateurs de la conférence ne peuvent pas composer l’appel sortant. Cet utilisateur peut effectuer des appels sortants vers des numéros nationaux et internationaux.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux, et cet utilisateur ne peut passer que des appels sortants vers un numéro RTC national.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    L'utilisateur de la conférence peut composer des numéros internationaux et nationaux et cet utilisateur ne peut pas effectuer d'appels sortants vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    L'utilisateur de la conférence ne peut appeler que des numéros nationaux, et cet utilisateur ne peut émettre que des appels vers des numéros RTC nationaux.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    L'utilisateur de la conférence peut uniquement composer des numéros nationaux, et cet utilisateur ne peut effectuer aucun appel sortant vers le numéro RTC en dehors des numéros d'urgence.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    Les utilisateurs de la conférence ne peuvent pas composer l’appel sortant, et il ne peut effectuer un appel sortant que vers des numéros PSTN nationaux.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    Les utilisateurs de la conférence ne peuvent pas appeler et ne peuvent pas appeler un numéro PSTN en plus des numéros d’urgence.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et effectuer des appels sortants vers des numéros nationaux et internationaux.    |
|    Identity='tag:DialoutCPCZoneAPSTN Tagsstic'    |    Les utilisateurs de la conférence peuvent uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et uniquement effectuer des appels sortants vers un numéro PSTN national.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    Un utilisateur de la conférence peut uniquement appeler les pays et régions de la zone [A](audio-conferencing-zones.md)et ne peut pas effectuer d’appels sortants vers un numéro PSTN en plus des numéros d’urgence.    |
