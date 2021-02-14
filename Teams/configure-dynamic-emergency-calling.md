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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment configurer les plans d’appels Microsoft et la fonctionnalité d’appels d’urgence dynamiques de routage direct du système téléphonique.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031010"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planifier et configurer un appel d’urgence dynamique 

Les appels d’urgence dynamiques pour les plans d’appels Microsoft et le routage direct du système téléphonique offrent la possibilité de configurer et de router des appels d’urgence et de notifier le personnel de sécurité en fonction de l’emplacement actuel du client Teams.  

En fonction de la topologie de réseau définie par l’administrateur client, le client Teams fournit les informations de connectivité réseau dans une demande au service d’informations d’emplacement (LIS). En cas de correspondance, le LIS renvoie un emplacement au client. Ces données d’emplacement sont transmises au client.  

Le client Teams inclut des données de localisation dans le cadre d’un appel d’urgence. Ces données sont ensuite utilisées par le fournisseur de services d’urgence pour déterminer le point de réponse de la sécurité publique appropriée (PUBLIC Safety Answering Point) et pour router l’appel vers ce réseau PUBLIC PUBLIC, ce qui permet au régulateur DUP d’obtenir l’emplacement de l’appelant.  

Pour les appels d’urgence dynamiques, les situations suivantes doivent se produire :

1. L’administrateur réseau configure les paramètres réseau et le LIS pour créer une carte d’emplacement de réseau/d’urgence.

   Pour le routage direct, une configuration supplémentaire est requise pour router des appels d’urgence et éventuellement pour la connectivité partenaire. L’administrateur doit configurer la connexion à un fournisseur de services  de routage d’urgence (États-Unis) OU configurer le contrôleur de session border Controller (SBC) pour une application ELIN (Emergency Location Identification Number).

2. Au démarrage et régulièrement par la suite, ou lorsqu’une connexion réseau est modifiée, le client Teams envoie une demande d’emplacement contenant ses informations de connectivité réseau aux paramètres réseau et au LIS.

   - S’il existe une correspondance de site de paramètres réseau, les stratégies d’appel d’urgence sont renvoyées au client Teams à partir de ce site. (Pour plus d’informations sur les stratégies, voir [Configurer les stratégies d’urgence).](#configure-emergency-policies)

   - S’il existe une correspondance de lis, un emplacement d’urgence à partir de l’élément réseau lié au client Teams est renvoyé au client Teams. La correspondance est effectuée dans l’ordre suivant avec le premier résultat renvoyé :
       - WAP
       - Commutateur/port Ethernet
       - Commutateur Ethernet
       - Sous-réseau

3. Lorsque le client Teams effectue un appel d’urgence, l’emplacement d’urgence est transmis au réseau PSTN.

   Pour un routage direct, l’administrateur doit configurer le SBC pour envoyer des appels d’urgence au fournisseur ERS ou configurer l’application SBC ELIN.

Cet article contient les sections suivantes.

- [Configurer des adresses de secours](#assign-emergency-addresses)
- [Configurer les paramètres réseau](#configure-network-settings)
- [Configurer le service Informations sur l’emplacement](#configure-location-information-service)
- [Configurer des stratégies d’urgence](#configure-emergency-policies)
- [Activer les utilisateurs et les sites](#enable-users-and-sites)
- [Tester les appels d’urgence](#test-emergency-calling)

La possibilité d’utiliser un routage automatique vers le point de réponse de sécurité publique approprié varie selon le pays d’utilisation de l’utilisateur de Teams.

Pour plus d’informations sur les appels d’urgence, notamment sur les adresses de secours et le routage des appels d’urgence, les informations spécifiques aux pays et les informations sur les paramètres réseau et la topologie du réseau, voir les informations suivantes :

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les paramètres réseau pour les fonctionnalités vocales cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)

## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont actuellement pris en charge.  Consultez régulièrement cette liste pour voir les mises à jour.

- Client de bureau Teams pour Microsoft Windows
- Client de bureau Teams pour Apple macOS
- Client mobile Teams pour le client Apple iOS version 1.0.92.2019121004 et App Store version 1.0.92 et supérieure
- Client mobile Teams pour le client Android et Version 1416/1.0.0.2019121201 ou version supérieure de Google Play Store
- Version de téléphone Teams 1449/1.0.94.2019110802 ou version supérieure
- Salles Teams version 4.4.25.0 ou supérieure

> [!NOTE]
> Les appels d’urgence dynamiques, y compris les notifications de service de sécurité, ne sont pas pris en charge sur le client web de Teams. Pour empêcher les utilisateurs d’utiliser le client web de Teams pour appeler des numéros PSTN, vous pouvez définir une stratégie d’appel Teams et désactiver le paramètre Autoriser les appels **PSTN web.** Pour en savoir plus, consultez [les stratégies d’appel](teams-calling-policy.md) dans Teams et [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

## <a name="assign-emergency-addresses"></a>Affecter des adresses de secours

Vous pouvez affecter des adresses d’urgence tant aux utilisateurs d’un plan d’appels qu’aux identificateurs réseau requis pour obtenir dynamiquement un emplacement. (Les sous-réseaux et WIFi AP sont pris en charge. Le commutateur/port Ethernet est actuellement pris en charge sur Windows 8.1 et les systèmes plus tard.

Pour prendre en charge le routage automatisé des appels d’urgence aux États-Unis, vous devez vous assurer que les emplacements d’urgence affectés à des identificateurs réseau incluent les codes géographiques associés. (Les adresses de secours sans codes géographiques ne peuvent pas être affectées aux identificateurs réseau requis pour les emplacements dynamiques.)

Azure Maps est utilisé pour les services basés sur l’emplacement.  Lorsque vous entrez une adresse d’urgence à l’aide du Centre d’administration Microsoft Teams, Teams vérifie l’adresse dans Cartes Azure :

- Si une correspondance est trouvée, les codes géographiques sont inclus automatiquement.

- Si la correspondance n’est pas trouvée, vous avez la possibilité de créer manuellement une adresse de secours. Pour ce faire, vous pouvez utiliser la fonctionnalité de déposer un code confidentiel. 

Cela signifie que si un emplacement d’urgence existant créé pour être attribué aux utilisateurs d’un plan d’appels est conçu pour un emplacement dynamique, la même adresse doit être re-créée pour inclure les codes géographiques. Pour faire la distinction entre les deux emplacements, vous devez inclure une description différente. Le nouvel emplacement d’urgence peut être affecté aux utilisateurs de l’ancien emplacement. Une fois entièrement migré, l’ancien emplacement peut être supprimé.

Vous ajoutez et affectez des adresses d’urgence dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour plus d’informations, voir [Ajouter un emplacement d’urgence](add-change-remove-emergency-location-organization.md) pour votre organisation et Affecter un emplacement d’urgence [à un utilisateur.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Configurer les paramètres réseau

Les paramètres réseau servent à déterminer l’emplacement d’un client Teams et à obtenir dynamiquement des stratégies d’appel d’urgence et un emplacement d’urgence. Vous pouvez configurer les paramètres réseau en fonction de la manière dont votre organisation souhaite que les appels d’urgence fonctionnent.

Les paramètres réseau incluent des sites qui comprennent une collection de sous-réseaux qui sont utilisés exclusivement pour l’affectation de stratégies dynamiques aux utilisateurs. Par exemple, une stratégie d’appel d’urgence et une stratégie de routage des appels d’urgence peuvent être affectées au « site de Redmond », de sorte que tout utilisateur qui vient de chez vous ou d’un autre emplacement Microsoft soit configuré avec les numéros d’urgence, le routage et le service de sécurité spécifiques de Redmond.  

>[!Note]
>Les sous-réseaux peuvent également être définis dans le lis et peuvent être associés à un emplacement d’urgence.  

Gardez les définitions suivantes à l’esprit. Pour plus d’informations, [voir Paramètres réseau pour les fonctionnalités vocales cloud.](cloud-voice-network-settings.md)

- Les adresses IP fiables contiennent un ensemble d’adresses IP externes internet du réseau d’entreprise et sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve dans le réseau d’entreprise. Une tentative d’obtention d’une stratégie dynamique ou d’un emplacement ne sera réalisée que si l’adresse IP externe de l’utilisateur correspond à une adresse IP de l’adresse IP de confiance. Une correspondance peut être faite par rapport aux adresses IP IPv4 ou IPv6 et dépend du format du paquet IP envoyé aux paramètres réseau.  (Si une adresse IP publique possède le protocole IPv4 et IPv6, vous devez ajouter les deux en tant qu’adresses IP de confiance.)

- Une région réseau contient une collection de sites réseau. 

- Un site réseau représente un emplacement où votre organisation a une valeur physique, telle qu’un bureau, un ensemble de bâtiments ou un campus. Ces sites sont définis comme une collection de sous-réseaux IP.

- Un sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau réseau et du site réseau associé.  

Vous configurez les paramètres réseau dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour plus d’informations, [voir Gérer votre topologie de réseau pour les fonctionnalités vocales cloud.](manage-your-network-topology.md)

Notez que la propagation et la mise à disposition de certains paramètres réseau (par exemple, une nouvelle adresse, un identificateur réseau, etc.) peuvent prendre un certain temps (jusqu’à quelques heures).  

**Pour les utilisateurs d’une forfait d’appels :**

- Si une configuration dynamique des notifications du service de sécurité est requise, vous devez configurer à la fois les adresses IP et les sites réseau de confiance.

- Si seuls des emplacements dynamiques sont nécessaires, vous devez configurer uniquement les adresses IP fiables.

- Si aucun de ces paramètres n’est requis, la configuration des paramètres réseau n’est pas nécessaire. 

**Pour les utilisateurs du routage direct :**

- Si l’enablement dynamique des appels d’urgence ou la configuration dynamique des notifications du service de sécurité est nécessaire, vous devez configurer à la fois les adresses IP de confiance et les sites réseau.

- Si seuls des emplacements dynamiques sont nécessaires, vous devez configurer uniquement les adresses IP fiables.

- Si aucun de ces paramètres n’est requis, la configuration des paramètres réseau n’est pas nécessaire.


## <a name="configure-location-information-service"></a>Configurer le service Informations sur l’emplacement

Un client Teams obtient des adresses d’urgence à partir des emplacements associés à différents identificateurs réseau. Les sous-réseaux et points d’accès sans fil sont pris en charge. À ce jour, le commutateur/port Ethernet est pris en charge sur Windows 8.1 et les systèmes plus tard.

Pour qu’un client obtienne un emplacement, vous devez remplir le LIS avec des identificateurs réseau (sous-réseaux, waps, commutateurs, ports) et des emplacements d’urgence. Vous pouvez le faire dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le groupe de navigation de gauche, allez à **Locations**  >  **Networks & emplacements.**
2. Cliquez sur l’onglet représentant l’identificateur réseau à ajouter. Par exemple, cliquez **sur Sous-réseaux,** **points d’accès Wi-Fi,** **commutateurs** ou **ports.** Cliquez ensuite sur **Ajouter.**
3. Complétez les champs, ajoutez un emplacement d’urgence, puis cliquez sur **Appliquer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez les cmdlets suivantes pour ajouter des ports, commutateurs, sous-réseaux et wap au LIS.

- [Obtenir,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps) [définir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) [supprimer](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Obtenir,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps) [Définir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps) [Supprimer](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Obtenir,](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps) [Définir,](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps) [Supprimer](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Obtenir,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps) [définir,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) [supprimer](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si des sous-réseaux sont utilisés dans le cadre de sites réseau, ils doivent être redéfinis dans le service Informations sur l’emplacement pour voir les emplacements dynamiques.

## <a name="configure-emergency-policies"></a>Configurer des stratégies d’urgence

Utilisez les stratégies suivantes pour configurer les appels d’urgence. Vous pouvez gérer ces stratégies dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

- **Stratégie de routage d’appel d’urgence** : s’applique uniquement au routage direct. Cette stratégie configure les numéros d’urgence, les masques par numéro si vous le souhaitez et l’itinéraire PSTN par numéro.  Vous pouvez affecter cette stratégie à des utilisateurs, à des sites réseau ou aux deux. (Les clients Plans d’appel Teams sont automatiquement activés pour les appels d’urgence avec les numéros d’urgence du pays sur la base de leur emplacement d’utilisation de Microsoft 365 ou d’Office 365.)  Pour plus d’informations, voir [Gérer les stratégies de routage des](manage-emergency-call-routing-policies.md)appels d’urgence pour le routage direct.

- **Stratégie d’appel d’urgence** - Applicable aux plans d’appels et au routage direct. Cette stratégie configure l’expérience de notification du service de sécurité en cas d’appel d’urgence. Vous pouvez définir les personnes à informer et la manière dont elles sont informées. Par exemple, pour informer automatiquement le service de sécurité de votre organisation et lui faire écouter les appels d’urgence.  Cette stratégie peut être affectée à des utilisateurs ou à des sites réseau, ou les deux. Pour plus d’informations, voir [Gérer les stratégies d’appel d’urgence dans Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Activer les utilisateurs et les sites

Vous pouvez affecter des stratégies de routage des appels d’urgence et des stratégies d’appel d’urgence aux utilisateurs et aux sites. N’oubliez pas que les stratégies de routage des appels d’urgence s’appliquent uniquement au routage direct. (Bien qu’il soit possible d’affecter cette stratégie à un utilisateur du plan d’appels, cette stratégie n’aura aucun effet.)

Vous attribuez des stratégies dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour en savoir plus, reportez-vous à la rubrique :

- [Gérer les stratégies de routage d’appel d’urgence pour le routage direct](manage-emergency-call-routing-policies.md)
- [Gérer les stratégies d’appel d’urgence dans Teams](manage-emergency-calling-policies.md)

Voici quelques exemples powershell.

Pour activer la notification d’un utilisateur spécifique du service de sécurité, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Pour affecter une stratégie appelée « Stratégie d’appel d’urgence de Contoso 1 » à Site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Pour activer un utilisateur de routage direct spécifique pour les appels d’urgence, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Pour attribuer une stratégie appelée « Routage des appels d’urgence de Contoso New York » vers le site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie qui lui est affectée.

## <a name="test-emergency-calling"></a>Tester les appels d’urgence

Certains fournisseurs de services de routage d’urgence aux États-Unis proposent un robot de test d’appel d’urgence.

- **Les utilisateurs d’un plan** d’appels aux États-Unis peuvent utiliser le numéro d’urgence de test prédéfide 933 pour valider leur configuration d’appel d’urgence. Ce numéro est acheminé vers un bot, ce qui a pour effet de faire écho au numéro de téléphone de l’appelant (ID de ligne d’appel), à l’adresse d’urgence ou à l’emplacement, et de savoir si l’appel doit être automatiquement acheminé vers le réseau PUBLIC OU d’abord présenté sous l’écran.

- **Les clients de routage direct aux États-Unis** doivent s’coordonner avec leur fournisseur ERSP pour un service de test.

 ## <a name="related-topics"></a>Sujets associés

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage d’appel d’urgence ](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affectation ou modification d’un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Paramètres réseau pour les fonctionnalités voix Cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)
