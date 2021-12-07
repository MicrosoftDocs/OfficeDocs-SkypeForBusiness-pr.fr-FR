---
title: Adresses d’urgence pour les emplacements distants
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Découvrez comment Microsoft prend en charge les informations d’emplacement à cet emplacement pour prendre en charge les appels d’urgence.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7d241cee858d3ac19747be56b5a53e157b563f64
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2021
ms.locfileid: "61322999"
---
# <a name="emergency-addresses-for-remote-locations"></a>Adresses d’urgence pour les emplacements distants

Cet article décrit la prise en charge par Microsoft des informations d’emplacement d’appel d’urgence au 911 aux États-Unis. Ce support garantit que les informations d’emplacement à expédier les plus précises possible sont fournies aux Teams les utilisateurs qui appellent les services d’urgence. Quel que soit l’emplacement de l’appelant (sur site ou à domicile), les informations d’emplacement de l’appelant envoyées au Point de réponse de sécurité publique (PUBLIC SAFETY Answering Point) doivent être précises.

Cet article inclut des informations sur la conformité de Microsoft avec l’Act for Multi Line Telephone Systems (MLTS) du BAUM. La loi RAY BAUM étend les obligations légales de Kari, qui sont entrées en vigueur début 2021. Pour plus d’informations sur le RAY BAUM’S Act et la loi de Kari, consultez l’emplacement du régulateur pour [les appels 911](https://www.fcc.gov/911-dispatchable-location) et les systèmes téléphoniques multi-lignes – Loi de Kari et [RAY BAUM’s Act 911 Direct Dialing, Notification et Conditions d’emplacement](https://www.fcc.gov/mlts-911-requirements)du service à la fois. 

Les utilisateurs qui travaillent à domicile peuvent désormais définir leurs propres adresses de secours, le cas échéant. Cet article décrit comment configurer des stratégies utilisateur pour que vos utilisateurs finaux définissent leurs adresses d’urgence.

Bien que ces informations s’appliquent aux appels d’urgence au 911 aux États-Unis, les emplacements entrés par l’utilisateur sont également transmis au centre de sélection au Canada.

Cet article contient les sections suivantes :

- [Prise en charge des informations d’emplacement des appels d’urgence](#support-for-emergency-calling-location-information)
- [Priorité sur les emplacements](#location-precedence)
- [Classification et routage des adresses d’urgence](#emergency-address-classification-and-routing)
- [Permettre aux utilisateurs finaux de configurer leur adresse de secours](#enable-end-users-to-configure-their-emergency-address)
- [Notes et restrictions](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Prise en charge des informations d’emplacement des appels d’urgence

Pour répondre à ces exigences, Teams utilise les services d’emplacement fournis par le système d’exploitation respectif pour suggérer une adresse (si l’administrateur ou l’utilisateur vous en a accordé l’autorisation). L’utilisateur final peut confirmer l’emplacement d’une adresse suggérée, la modifier ou en entrer une nouvelle manuellement. Une adresse confirmée, modifiée ou entrée manuellement est ensuite enregistrée sur le client Teams afin que l’adresse confirmée par l’utilisateur soit automatiquement utilisée lorsque le client est connecté à ce réseau. Les adresses enregistrées par l’utilisateur sont automatiquement effacées lorsque Teams client est désigné.


## <a name="location-precedence"></a>Priorité sur les emplacements

Les adresses de secours Teams peuvent être classées selon différents types. La liste suivante indique la priorité d’emplacement utilisée lorsqu’un numéro d’urgence est composé :

1. Adresse acquise dynamiquement par l’administration du client dans le service Informations sur l’emplacement.

2. Adresse que l’utilisateur final a confirmée, modifiée ou entrée manuellement, associée au réseau local auquel le client Teams est connecté.

3. Une adresse suggérée automatiquement par le système d’exploitation.

4. Une adresse que l’administrateur affecte statiquement à l’utilisateur.


## <a name="emergency-address-classification-and-routing"></a>Classification et routage des adresses d’urgence

Le tableau suivant indique les types d’adresses d’urgence et les méthodes de routage associées pour chaque type : si l’appel est automatiquement acheminé vers le service CENTRE.PUBLIC ou s’il est filré pour plus de précision avant d’être transféré vers le service PUBLICP. Ce comportement de routage est pris en charge aux États-Unis pour tous les utilisateurs d’un plan d’appels, les partenaires Connecter opérateurs et les fournisseurs de services d’urgence certifiés pour le routage direct.


| Type d’adresse de secours | Méthode de routage d’urgence |
| :------------| :-------|
| Adresse d’urgence acquise dynamiquement définie par l’administrateur. | Direct vers PUBLICP. |
| Adresse d’urgence obtenue à partir du système d’exploitation **sans confirmation de précision** par l’utilisateur. | Screened and Transferred to PUBLICP. |
| Adresse d’urgence obtenue du système d’exploitation **avec confirmation de l’exactitude** par l’utilisateur.| Direct vers PUBLICP. |
| Adresse d’urgence obtenue à partir du système d’exploitation et modifiée et confirmée par l’utilisateur. | Screened and Transferred to PUBLICP. |
| Adresse de secours entrée et confirmée par l’utilisateur. | Screened and Transferred to PUBLICP. |
| Adresse d’urgence statique attribuée à l’utilisateur/numéro. | Screened and Transferred to PUBLICP. |
| Null | Screened and Transferred to PUBLICP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permettre aux utilisateurs finaux de configurer leur adresse de secours

Pour activer cette fonctionnalité pour vos utilisateurs finaux, utilisez l'New-CsTeamsEmergencyCallingPolicy cmdlet PowerShell, puis définissez le paramètre ExternalLocationLookupMode sur Activé. Consultez l’exemple suivant : 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Après avoir activation de cette fonctionnalité pour vos utilisateurs finaux, dans l’onglet Appels, l’utilisateur peut ajouter, modifier ou confirmer une adresse de secours et afficher l’adresse une fois celle-ci définie. 

Sur Windows, vous pouvez gérer le service de localisation d’Windows, et déterminer si les applications ont accès à l’emplacement, à l’aide d’une stratégie de groupe ou à l’aide de la gestion des périphériques [mobiles.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Pour plus d’informations sur Windows service de localisation, voir Windows [service d’emplacement et la confidentialité.](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)



## <a name="notes-and-restrictions"></a>Notes et restrictions

Tenez compte des points suivants :

- L’expérience domicile-travail décrite s’Teams bureau sur Windows et Mac.

- Teams téléphones ne supportent pas l’expérience entre domicile et travail.

- Teams mobile prend en charge la détection automatique de l’emplacement, mais pas l’expérience entrée par l’utilisateur décrite.

- Les paramètres de confidentialité peuvent être en conflit avec la détection automatique de l’emplacement - Vous pouvez utiliser des systèmes de gestion des appareils mobiles.


## <a name="related-topics"></a>Rubriques connexes

[Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)

