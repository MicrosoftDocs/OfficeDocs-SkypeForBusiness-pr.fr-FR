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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Découvrez comment Microsoft prend en charge les informations de localisation expédiables pour prendre en charge les appels d’urgence.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272069"
---
# <a name="emergency-addresses-for-remote-locations"></a>Adresses d’urgence pour les emplacements distants

Cet article décrit la prise en charge par Microsoft des informations d’emplacement d’appel d’urgence 911 dans le États-Unis. Cette prise en charge garantit que les informations d’emplacement dispatchable les plus précises possibles sont fournies aux utilisateurs Teams effectuant des appels d’urgence. Quel que soit l’emplacement de l’appelant , sur place ou à partir de son domicile, les renseignements sur l’emplacement d’un appelant envoyés au point de réponse à la sécurité publique (PSAP) doivent être exacts.

Cet article contient des informations sur la conformité de Microsoft avec la loi RAY BAUM pour les systèmes téléphoniques multilignes (MLTS). La Loi de RAY BAUM étend les exigences de la loi de Kari, qui sont entrées en vigueur au début de 2021. Pour plus d’informations sur la Loi de RAY BAUM et la loi de Kari, consultez [l’article Dispatchable Location for 911 Calls](https://www.fcc.gov/911-dispatchable-location) and [Multi-line Telephone Systems – Kari’s Law and RAY BAUM’s Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Les utilisateurs travaillant à la maison peuvent désormais définir leurs propres adresses d’urgence le cas échéant. Cet article explique comment configurer des stratégies utilisateur afin que vos utilisateurs finaux puissent définir leurs adresses d’urgence.

Bien que ces renseignements s’appliquent aux appels d’urgence 911 dans le États-Unis, les emplacements où les utilisateurs sont entrés seront également transmis au Centre de dépistage au Canada.

Cet article contient les sections suivantes :

- [Prise en charge des informations d’emplacement d’appel d’urgence](#support-for-emergency-calling-location-information)
- [Priorité de l’emplacement](#location-precedence)
- [Classification et routage des adresses d’urgence](#emergency-address-classification-and-routing)
- [Permettre aux utilisateurs finaux de configurer leur adresse d’urgence](#enable-end-users-to-configure-their-emergency-address)
- [Notes et restrictions](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Prise en charge des informations d’emplacement d’appel d’urgence

Pour prendre en charge ces exigences, Teams utilise les services d’emplacement fournis par le système d’exploitation respectif pour suggérer une adresse, si l’administrateur ou l’utilisateur lui accorde une autorisation. L’utilisateur final peut confirmer l’emplacement d’une adresse suggérée, la modifier ou en entrer manuellement une nouvelle. Une adresse confirmée, modifiée ou entrée manuellement est ensuite enregistrée sur le client Teams afin que l’adresse confirmée par l’utilisateur soit automatiquement utilisée lorsque le client est connecté à ce réseau. Les adresses enregistrées par l’utilisateur sont automatiquement effacées lorsque le client Teams est déconnecté.


## <a name="location-precedence"></a>Priorité de l’emplacement

Les adresses d’urgence pour Teams peuvent être classées par différents types. La liste suivante montre la priorité d’emplacement utilisée lorsqu’un numéro d’urgence est composé :

1. Adresse acquise dynamiquement définie par le locataire administré dans le service d’informations d’emplacement.

2. Adresse à laquelle l’utilisateur final a confirmé, modifié ou entré manuellement et qui est associée au réseau local auquel le client Teams est connecté.

3. Adresse suggérée automatiquement par le système d’exploitation.

4. Adresse que l’administrateur affecte statiquement à l’utilisateur.


## <a name="emergency-address-classification-and-routing"></a>Classification et routage des adresses d’urgence

Le tableau suivant répertorie les types d’adresses d’urgence et les méthodes de routage associées pour chaque type : si l’appel est automatiquement routée vers le PSAP de service ou si l’exactitude est filtrée avant le transfert vers le PSAP de service. Ce comportement de routage est pris en charge dans le États-Unis pour tous les utilisateurs du plan d’appel, les partenaires Operator Connect et les fournisseurs de services d’appel d’urgence certifiés pour le routage direct.


| Type d’adresse d’urgence | Méthode de routage d’urgence |
| :------------| :-------|
| Adresse d’urgence acquise dynamiquement définie par l’administrateur. | Direct vers PSAP. |
| Adresse d’urgence obtenue auprès du système d’exploitation **sans confirmation de précision** par l’utilisateur. | Filtré et transféré vers PSAP. |
| Adresse d’urgence obtenue auprès du système d’exploitation **avec confirmation de précision** par l’utilisateur.| Direct vers PSAP. |
| Adresse d’urgence obtenue à partir du système d’exploitation et modifiée et confirmée par l’utilisateur. | Filtré et transféré vers PSAP. |
| Adresse d’urgence entrée et confirmée par l’utilisateur. | Filtré et transféré vers PSAP. |
| Adresse d’urgence affectée statiquement à l’utilisateur/numéro. | Filtré et transféré vers PSAP. |
| Null | Filtré et transféré vers PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permettre aux utilisateurs finaux de configurer leur adresse d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **stratégies d’urgence** **vocale** > .
2. Sélectionnez **Ajouter**.
3. Entrez un nom pour la stratégie d’appel d’urgence, par exemple « E911WFH ».
4. Activez le **mode recherche d’emplacement externe**.
5. Sélectionnez **Appliquer**.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>Utiliser PowerShell

Pour activer cette fonctionnalité pour vos utilisateurs finaux, utilisez la New-CsTeamsEmergencyCallingPolicy cmdlet PowerShell et définissez le paramètre ExternalLocationLookupMode sur Activé. Consultez l’exemple suivant : 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Après avoir activé cette fonctionnalité pour vos utilisateurs finaux, à partir de l’onglet Appels, l’utilisateur peut ajouter, modifier ou confirmer une adresse d’urgence et afficher l’adresse une fois celle-ci définie. Pour plus d’informations sur la façon dont les utilisateurs finaux peuvent définir des services de localisation, consultez [Work from Home Emergency 911 : activer les services de localisation](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

Sur Windows, vous pouvez gérer le service d’emplacement Windows et déterminer si les applications ont accès à l’emplacement, à l’aide d’une stratégie de groupe ou à l’aide de [la gestion des appareils mobiles (GPM).](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Pour plus d’informations sur le service d’emplacement Windows, consultez [le service d’emplacement Windows et la confidentialité](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Notes et restrictions

Tenez compte des points suivants :

- L’expérience de travail à domicile décrite est pour le bureau Teams sur Windows et Mac.

- Les téléphones Teams ne prennent pas en charge l’expérience professionnelle à domicile.

- Teams Mobile prend en charge la détection automatique de l’emplacement, mais pas l’expérience entrée par l’utilisateur décrite.

- Les paramètres de confidentialité peuvent entrer en conflit avec la détection automatique de l’emplacement : les systèmes Gestion des appareils mobiles peuvent être utilisés.


## <a name="related-topics"></a>Voir aussi

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)

- [Travail d’urgence à domicile 911 : activer les services de localisation](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

