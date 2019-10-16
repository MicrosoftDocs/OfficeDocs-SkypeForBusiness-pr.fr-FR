---
title: Configurer les appels d’urgence dynamiques
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurer les appels d’urgence dynamiques
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516931"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>Planifier et configurer les appels d’urgence dynamiques pour les offres d’appels
Les appels d’urgence dynamiques pour les plans d’appel Microsoft offrent la possibilité de configurer et d’acheminer les appels d’urgence en fonction de l’emplacement actuel du client Teams.  La possibilité de procéder au routage automatique vers le point d’accès à la sécurité publique approprié (PSAPI) ou de notifier le personnel de votre support technique dépend du pays d’utilisation de l’utilisateur de teams.  

> [!Note] 
> Les appels d’urgence dynamiques ne sont actuellement disponibles qu’aux États-Unis. La notification du support technique est toutefois prise en charge entre les pays.

**Aux États-Unis**, vous pouvez configurer le routage des appels d’urgence dynamiques comme suit :
  
- Si un client teams se trouve dans un emplacement d’urgence dynamique défini par un client, les appels d’urgence de ce client sont automatiquement routés vers le PSAPI qui dessert cet emplacement géographique.  

- Si un client Teams ne se trouve pas dans un emplacement d’urgence dynamique défini par le client, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAPI qui dessert cet emplacement géographique.

Vous pouvez configurer les notifications de bureau de sécurité comme suit :

- Si un client teams se trouve sur un site réseau défini par un client, les membres du groupe de sécurité configurés pour ce site en seront avertis.

- Si un client Teams ne se trouve pas sur un site réseau défini par un client, les membres du groupe de sécurité configurés pour l’utilisateur en seront avertis.

**Hors des États-Unis**, les appels d’urgence sont routés vers le PSAPI qui est mappé au numéro de téléphone attribué à l’utilisateur.  Certains pays, tels que la Grande-Bretagne et le Canada, envoient les appels nationaux avant de transférer l’appelant vers le PSAPI approprié, tandis que d’autres sont routés directement au PSAPI, quel que soit l’endroit où l’utilisateur se trouve actuellement. 

Notez que vous pouvez configurer la notification du support technique dynamique pour tous les utilisateurs du plan d’appel.


## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont actuellement pris en charge.  Consultez régulièrement les mises à jour de cette liste.

- Client de bureau teams pour Windows
- Client de bureau teams pour Mac

## <a name="configure-dynamic-emergency-calling"></a>Configurer les appels d’urgence dynamiques

Pour configurer les appels d’urgence dynamiques, vous devez effectuer les tâches suivantes :

- [Configurer des adresses d’urgence](#configure-emergency-addresses)
- [Configurer les paramètres réseau](#configure-network-settings)
- [Configurer le service d’information d’emplacement](#configure-location-information-service)
- [Configurer des stratégies d’urgence](#configure-emergency-policies)
- [Activer les utilisateurs et les sites](#enable-users-and-sites)
- [Tester les appels d’urgence](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>Configurer des adresses d’urgence

Pour prendre en charge le routage automatisé à l’intérieur des États-Unis, vous devez configurer entièrement l’adresse postale qui fait partie des emplacements d’urgence attribués aux identifiants réseau, en incluant les codes géographiques associés. (Les adresses d’urgence sans code géo ne peuvent pas être affectées aux identifiants réseau requis pour les emplacements dynamiques).

- Si vous entrez une adresse d’urgence via le centre d’administration de Microsoft Teams, les codes géographiques sont automatiquement inclus si une correspondance est trouvée.

- Si une correspondance est introuvable, vous pouvez créer manuellement une adresse de secours.  

Cela signifie que si une adresse d’urgence existante est configurée pour les appels d’urgence, la même adresse doit être recréée pour inclure les codes géographiques.  Pour faire la distinction entre les deux adresses, vous devez inclure une autre description. La nouvelle adresse de secours peut être affectée aux utilisateurs disposant de l’ancienne adresse. Lors de la migration complète, l’ancienne adresse peut être supprimée. 

Pour plus d’informations sur la configuration des adresses d’urgence, voir [que sont les emplacements d’urgence, les lieux et le routage des appels ?](what-are-emergency-locations-addresses-and-call-routing.md).

### <a name="configure-network-settings"></a>Configurer les paramètres réseau

Pour le routage des appels d’urgence, vous devez configurer des paramètres réseau pour obtenir dynamiquement les appels d’urgence et, si vous le souhaitez, fournir une configuration dynamique des notifications du Bureau de sécurité. L’appel d’urgence souhaité détermine les paramètres réseau qui doivent être configurés. 

Gardez à l’esprit les définitions suivantes :

- Les adresses IP de confiance contiennent une collection d’adresses IP externes Internet du réseau d’entreprise, qui sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise. Les emplacements dynamiques ne sont activés que si l’adresse IP externe de l’utilisateur correspond à une adresse IP dans la collection IP approuvée.  Une correspondance peut être établie avec des adresses IP IPv4 ou IPv6 et dépend du format des paquets IP envoyés aux paramètres du réseau.

- Une région réseau contient une collection de sites réseau. 

- Un site réseau correspond à un emplacement où votre organisation a une valeur physique, par exemple un bureau, un ensemble de bâtiments ou un campus. Ces sites sont définis comme un ensemble de sous-réseaux IP.

- Un sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau du réseau et du site du réseau associé.  


Pour les utilisateurs de plan d’appel :

- Si la configuration dynamique de la notification du support technique est requise, vous devez configurer les adresses IP et les sites réseau approuvés.

- Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP autorisées. 

- Si ce n’est pas le cas, il n’est pas nécessaire de configurer les paramètres réseau. 

Pour plus d’informations, voir [configurer les paramètres réseau pour le routage en fonction de l’emplacement](location-based-routing-configure-network-settings.md), qui décrit comment configurer les paramètres réseau. (Les informations contenues dans cet article s’appliquent aux plans d’appel et au routage direct.)


### <a name="configure-location-information-service"></a>Configurer le service d’information d’emplacement

Un client d’équipes obtient les adresses d’urgence des emplacements d’urgence associés à différents identificateurs de réseau.  Les sous-réseaux et les points d’accès sans fil sont tous deux pris en charge. (La prise en charge du commutateur/port Ethernet est en attente.)

Pour configurer le service d’information d’emplacement (LIS) avec des identificateurs réseau et des emplacements d’urgence, utilisez les applets de commande suivantes :

- Get, Set, Remove-CsOnlineLisPort
- Get, Set, Remove-CsOnlineLisSwitch
- Get, Set, Remove-CsOnlineLisSubnet
- Get, Set, Remove-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> Si des sous-réseaux sont utilisés dans le cadre de sites réseau, ils doivent être redéfinis dans le service d’information d’emplacement pour le rendu des emplacements dynamiques.


### <a name="configure-emergency-policies"></a>Configurer des stratégies d’urgence

Les politiques d’urgence déterminent ce qui se produit quand un utilisateur de votre organisation effectue un appel d’urgence.  Vous pouvez définir la personne à notifier et la manière dont elle est avertie quand un utilisateur appelle des services d’urgence. Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement l’assistance technique de votre organisation et leur permettre d’écouter les appels d’urgence.

Pour gérer les stratégies d’urgence, vous pouvez utiliser les applets de CsTeamsEmergencyCalling de stratégie nouveau, Set et Grant-.  Pour plus d’informations, consultez [gérer les stratégies d’appel d’urgence dans teams](manage-emergency-calling-policies.md).


### <a name="enable-users-and-sites"></a>Activer les utilisateurs et les sites

Lorsque les utilisateurs d’un plan d’appels sont automatiquement activés pour les appels d’urgence, vous devez activer les notifications d’appel d’urgence en configurant la politique d’appel d’urgence, comme le montre l’exemple suivant :


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Vous pouvez également affecter la politique d’appel d’urgence à un site réseau comme le montre l’exemple suivant, qui affecte une stratégie appelée « stratégie d’appel d’urgence contoso 1 » vers le site 1 :

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.


### <a name="test-emergency-calling"></a>Tester les appels d’urgence

Pour tester les appels d’urgence aux États-Unis, utilisez la 933 de test prédéfinie.  Ce numéro est routé vers un bot, qui réagit ensuite du numéro de téléphone de l’appelant (ID de ligne d’appel), de l’adresse de secours ou de l’emplacement et de l’acheminement automatique de l’appel vers le champ PSAPI ou à l’écran.  