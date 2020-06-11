---
title: Configurer un appel d’urgence dynamique
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
f1.keywords:
- NOCSH
description: Apprenez à configurer les plans d’appel Microsoft et les appels d’urgence dynamiques du système téléphonique pour le routage direct.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50e32c34b211766aa5fc3ad7732b1dd392ed8346
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690880"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planifier et configurer un appel d’urgence dynamique 

Les appels d’urgence dynamiques pour les plans d’appel Microsoft et le routage direct du système téléphonique permettent de configurer et d’acheminer les appels d’urgence et de notifier le personnel de sécurité en fonction de l’emplacement actuel du client Teams.  

En fonction de la topologie réseau définie par l’administrateur de clients, le client teams fournit des informations de connectivité réseau dans une demande au service d’information d’emplacement (LIS). S’il existe une correspondance, la propriété LIS renvoie un emplacement au client. Ces données d’emplacement sont transmises au client.  

Le client teams comporte des données de géolocalisation dans le cadre d’un appel d’urgence. Ce type de données est ensuite utilisé par le fournisseur de services d’urgence pour déterminer le point de raccordement de la sécurité publique approprié (PSAPI) et pour acheminer l’appel vers ce PSAPI, ce qui permet au répartiteur de PSAPI d’obtenir l’emplacement de l’appelant.  

Pour les appels d’urgence dynamiques, les informations suivantes doivent se produire :

1. L’administrateur réseau configure les paramètres réseau et LIS pour créer une carte de réseau/d’urgence.

   Pour le routage direct, une configuration supplémentaire est nécessaire pour le routage des appels d’urgence et peut-être pour la connectivité des partenaires. L’administrateur doit configurer la connexion à un fournisseur de service de routage d’urgence (ERS) **ou** configurer le contrôleur de bordure de session (SBC) pour une application de type identification d’emplacement d’urgence (Elin).

2. Lors du démarrage et, par la suite, ou lors de la modification d’une connexion réseau, le client teams envoie une demande d’emplacement contenant les informations relatives à la connectivité réseau aux paramètres du réseau et à la Banque d’informations locale.

   - S’il existe une correspondance entre le site paramètres du réseau, les stratégies d’appel d’urgence sont renvoyées au client teams depuis ce site. Pour plus d’informations sur les stratégies, voir [configurer des stratégies d’urgence](#configure-emergency-policies).

   - S’il existe une correspondance LIS, un emplacement d’urgence à partir de l’élément réseau auquel le client teams est connecté est retourné au client Teams.

3. Lorsque le client teams effectue un appel d’urgence, l’emplacement d’urgence est transmis au réseau PSTN.

   Pour le routage direct, l’administrateur doit configurer SBC pour envoyer des appels d’urgence au fournisseur ERS ou configurer l’application SBC ELIN.

Cet article contient les sections suivantes.

- [Configurer des adresses d’urgence](#assign-emergency-addresses)
- [Configurer les paramètres réseau](#configure-network-settings)
- [Configurer le service d’information d’emplacement](#configure-location-information-service)
- [Configurer des stratégies d’urgence](#configure-emergency-policies)
- [Activer les utilisateurs et les sites](#enable-users-and-sites)
- [Tester les appels d’urgence](#test-emergency-calling)

La possibilité de procéder au routage automatique vers le point de réponse sécurisé public approprié dépend du pays d’utilisation de l’utilisateur de teams.

Pour plus d’informations sur les appels d’urgence, y compris des informations sur les adresses de secours et le routage des appels d’urgence, les informations spécifiques aux pays et les informations sur les paramètres réseau et la topologie du réseau, voir les rubriques suivantes :

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les paramètres réseau pour les fonctionnalités vocales sur le Cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)

## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont actuellement pris en charge.  Consultez régulièrement les mises à jour de cette liste.

- Client de bureau teams pour Microsoft Windows
- Client de bureau teams pour Apple macOS
- Client Microsoft teams mobile pour les versions de client Apple iOS 1.0.92.2019121004 et App Store 1.0.92 et version ultérieure
- Client mobile teams pour Android et Google Play Store version 1416/1.0.0.2019121201 et version ultérieure
- Version de téléphone teams 1449/1.0.94.2019110802 et version ultérieure

## <a name="assign-emergency-addresses"></a>Attribution d’adresses de secours

Vous pouvez affecter des adresses d’urgence aux utilisateurs de plan d’appel et aux identifiants réseau requis pour l’obtention dynamique d’un emplacement. (Le sous-réseau et le point d’accès WiFi sont pris en charge ; le commutateur/port Ethernet est en attente).

Pour prendre en charge le routage automatisé des appels d’urgence à l’intérieur des États-Unis, vous devez vous assurer que les emplacements d’urgence attribués aux identifiants réseau incluent les codes géographiques associés. (Les adresses de secours sans codes géographiques ne peuvent pas être affectées aux identifiants réseau requis pour les emplacements dynamiques.)

Azure Maps est utilisé pour les services de géolocalisation.  Lorsque vous entrez une adresse d’urgence à l’aide du centre d’administration de Microsoft Teams, teams vérifie l’adresse dans Azure Maps.

- Si une correspondance existe, les codes géographiques sont automatiquement inclus.

- Si aucune correspondance n’est trouvée, vous pouvez créer manuellement une adresse de secours. Pour cela, vous pouvez utiliser la fonctionnalité d’insertion de code confidentiel. 

Cela signifie que si un emplacement d’urgence existant qui est créé pour l’attribution aux utilisateurs de plan d’appels est destiné à un emplacement dynamique, la même adresse doit être recréée pour inclure les codes géographiques. Pour faire la distinction entre les deux emplacements, vous devez inclure une autre description. Le nouvel emplacement d’urgence peut être attribué aux utilisateurs de l’ancien emplacement. Lors de la migration complète, l’ancien emplacement peut être supprimé.

Vous pouvez ajouter et affecter des adresses d’urgence dans le centre d’administration Microsoft teams ou à l’aide de PowerShell. Pour plus d’informations, reportez-vous à [la rubrique ajouter un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md) et [attribuer un emplacement d’urgence à un utilisateur](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurer les paramètres réseau

Les paramètres réseau sont utilisés pour déterminer l’emplacement d’un client teams et pour obtenir dynamiquement les politiques d’appel d’urgence et un emplacement d’urgence. Vous pouvez configurer les paramètres réseau en fonction de la manière dont votre organisation veut fonctionner.

Les paramètres réseau incluent des sites qui incluent une collection de sous-réseaux et qui sont utilisés exclusivement pour une attribution de stratégie dynamique aux utilisateurs. Par exemple, la stratégie d’appel d’urgence et la politique d’acheminement des appels d’urgence peuvent être attribuées au « site de Redmond » de telle sorte que tous les utilisateurs qui se connectent à partir de la maison ou d’un autre emplacement Microsoft soient configurés avec des numéros d’urgence, le routage et le Bureau de sécurité spécifiques à Redmond.  

>[!Note]
>Les sous-réseaux peuvent également être définis dans LIS et peuvent être associés à un emplacement d’urgence.  

Gardez à l’esprit les définitions suivantes. Pour plus d’informations, voir [paramètres réseau pour les fonctionnalités vocales dans le Cloud](cloud-voice-network-settings.md).

- Les adresses IP approuvées contiennent une collection d’adresses IP externes Internet du réseau d’entreprise, qui sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise. Une tentative d’obtention d’une stratégie ou d’un emplacement dynamique n’est faite que si l’adresse IP externe de l’utilisateur correspond à une adresse IP de l’adresse IP de confiance. Une correspondance peut être établie avec des adresses IP IPv4 ou IPv6 et dépend du format des paquets IP envoyés aux paramètres du réseau.  (Si une adresse IP publique comporte à la fois IPv4 et IPv6, vous devez ajouter les deux en tant qu’adresses IP approuvées.)

- Une région réseau contient une collection de sites réseau. 

- Un site réseau correspond à un emplacement où votre organisation a une valeur physique, par exemple un bureau, un ensemble de bâtiments ou un campus. Ces sites sont définis comme un ensemble de sous-réseaux IP.

- Un sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau du réseau et du site du réseau associé.  

Vous pouvez configurer les paramètres réseau dans le centre d’administration Microsoft teams ou à l’aide de PowerShell. Pour en savoir plus, voir [gérer la topologie de votre réseau pour les fonctionnalités vocales de Cloud](manage-your-network-topology.md).

Notez qu’il est possible que certaines modifications apportées aux paramètres réseau (par exemple, une nouvelle adresse, un identifiant réseau, etc.) soient propagées et soient disponibles pour les clients Teams.  

**Pour les utilisateurs de plan d’appel :**

- Si une configuration dynamique de la notification du support technique est requise, vous devez configurer des adresses IP et des sites réseau approuvés.

- Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP autorisées.

- Si ce n’est pas le cas, la configuration des paramètres réseau n’est pas obligatoire. 

**Pour les utilisateurs de routage direct :**

- Si l’activation dynamique de l’appel d’urgence ou de la configuration dynamique de la notification du support technique est requise, vous devez configurer des adresses IP et des sites réseau de confiance.

- Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP autorisées.

- Si ce n’est pas le cas, la configuration des paramètres réseau n’est pas obligatoire.


## <a name="configure-location-information-service"></a>Configurer le service d’information d’emplacement

Un client d’équipes obtient les adresses d’urgence à partir des emplacements associés à différents identificateurs de réseau. Les sous-réseaux et les points d’accès sans fil sont pris en charge. (La prise en charge du commutateur/port Ethernet est en attente.)

Pour qu’un client obtienne un emplacement, vous devez remplir la LIS avec des identificateurs de réseau (sous-réseaux, WAP, commutateurs, ports) et emplacements d’urgence. Vous pouvez le faire dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à **emplacements**  >  **réseaux & emplacements**.
2. Cliquez sur l’onglet qui représente l’identificateur du réseau que vous voulez ajouter. Par exemple, cliquez sur **sous-réseaux**, points d' **accès Wi-Fi**, **commutateurs**ou **ports**. Puis cliquez sur **Ajouter**.
3. Complétez les champs, ajoutez un emplacement d’urgence, puis cliquez sur **appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez les applets de commande suivantes pour ajouter des ports, des commutateurs, des sous-réseaux et des WAP à la Banque d’informations locale.

- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si des sous-réseaux sont utilisés dans le cadre de sites réseau, ils doivent être redéfinis dans le service d’information d’emplacement pour le rendu des emplacements dynamiques.

## <a name="configure-emergency-policies"></a>Configurer des stratégies d’urgence

Utilisez les stratégies suivantes pour configurer les appels d’urgence. Vous pouvez gérer ces stratégies dans le centre d’administration Microsoft teams ou à l’aide de PowerShell.

- **Stratégie d’acheminement des appels d’urgence** : s’applique uniquement au routage direct. Cette politique configure les numéros d’urgence, les masques par numéro, le cas échéant, et l’itinéraire RTC par numéro.  Vous pouvez affecter cette stratégie aux utilisateurs, aux sites réseau ou aux deux. (Les appels d’offres sont automatiquement activés pour les appels d’urgence en utilisant les numéros d’urgence du pays en fonction de leur emplacement d’utilisation de Microsoft 365 ou d’Office 365.)  Pour plus d’informations, consultez [gérer les stratégies d’acheminement des appels d’urgence pour le routage direct](manage-emergency-call-routing-policies.md).

- **Politique d’appel d’urgence** : s’applique aux offres d’appels et au routage direct. Cette stratégie configure l’interface de notification du support technique lors d’un appel d’urgence. Vous pouvez définir la personne à notifier et la manière dont elle est notifiée. Par exemple, pour avertir automatiquement le centre de sécurité de votre organisation et les informer lors des appels d’urgence.  Cette stratégie peut être affectée à des utilisateurs ou des sites réseau ou les deux. Pour en savoir plus, voir [gérer les stratégies d’appel d’urgence dans teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Activer les utilisateurs et les sites

Vous pouvez attribuer des stratégies de routage des appels d’urgence et des politiques d’appel d’urgence aux utilisateurs et aux sites. Gardez à l’esprit que les stratégies de routage des appels d’urgence s’appliquent uniquement au routage direct. (Bien qu’il soit possible d’affecter cette stratégie à un utilisateur de plan d’appels, la stratégie n’aura aucun effet.)

Vous attribuez des stratégies dans le centre d’administration Microsoft teams ou en utilisant PowerShell. Pour en savoir plus, reportez-vous à la rubrique :

- [Gérer les stratégies de routage des appels d’urgence pour le routage direct](manage-emergency-call-routing-policies.md)
- [Gérer les stratégies d’appel d’urgence dans teams](manage-emergency-calling-policies.md)

Voici quelques exemples de PowerShell.

Pour permettre à un utilisateur spécifique de notifier la sécurité du support technique, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Pour attribuer une stratégie nommée « Stratégie d’appel d’urgence contoso 1 » au site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Pour permettre à un utilisateur de routage direct spécifique d’appeler des services d’urgence, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Pour attribuer une stratégie nommée « routage des appels d’urgence de contoso New York » vers le site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.

## <a name="test-emergency-calling"></a>Tester les appels d’urgence

Certains fournisseurs de service de routage d’urgence (ERSPs) aux États-Unis proposent un robot de test d’appel d’urgence.

- **Les utilisateurs de plan d’appels aux États-Unis** peuvent utiliser la 933 de test prédéfinie pour valider la configuration des appels d’urgence. Ce numéro est routé vers un bot, qui réagit ensuite du numéro de téléphone de l’appelant (ID de ligne d’appel), de l’adresse de secours ou de l’emplacement et de l’acheminement automatique de l’appel au PSAPI ou à l’écran.

- **Le routage direct des clients aux États-Unis** doit coordonné avec leur ERSP pour un service de test.

 ## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage des appels d’urgence](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affectation ou modification d’un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Paramètres réseau pour les fonctionnalités voix Cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)
