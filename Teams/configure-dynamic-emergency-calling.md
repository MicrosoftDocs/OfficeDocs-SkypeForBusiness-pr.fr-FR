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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment configurer la fonctionnalité d’appel dynamique d’urgence des forfaits d’appels Microsoft et du routage direct du système téléphonique.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814356"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planifier et configurer un appel d’urgence dynamique 

Les appels d’urgence dynamiques pour les plans d’appels Microsoft, Operator Connect, Teams Phone Mobile et le routage direct permettent de configurer et de router les appels d’urgence et d’informer le personnel de sécurité en fonction de l’emplacement actuel du client Teams.  

En fonction de la topologie de réseau (éléments réseau associés aux adresses d’urgence) que l’administrateur client définit, le client Teams fournit des informations de connectivité réseau dans une requête adressée au service d’informations de localisation (LIS). S’il existe une correspondance, la lis renvoie un emplacement au client.

Le client Teams inclut des données d’emplacement dans le cadre d’un appel d’urgence. Ces données sont ensuite utilisées par le fournisseur de services d’urgence pour déterminer le point de réponse de sécurité publique (PSAP) approprié et pour acheminer l’appel vers ce PSAP, ce qui permet au répartiteur du PSAP d’obtenir l’emplacement de l’appelant.  

Pour les appels d’urgence dynamiques, les opérations suivantes doivent se produire :

1. L’administrateur réseau configure les paramètres réseau et le LIS pour créer une carte d’emplacement réseau/d’urgence.

2. Au démarrage et régulièrement par la suite, ou lorsqu’une connexion réseau est modifiée, le client Teams envoie une demande d’emplacement qui contient ses informations de connectivité réseau aux paramètres réseau et au LIS.

   - S’il existe une correspondance de site de paramètres réseau, les stratégies d’appel d’urgence sont renvoyées au client Teams à partir de ce site. (Pour plus d’informations sur les stratégies, consultez [Configurer des stratégies d’urgence](#configure-emergency-policies)).

   - S’il existe une correspondance LIS, un emplacement d’urgence à partir de l’élément réseau auquel le client Teams est connecté est retourné au client Teams. La correspondance est effectuée dans l’ordre suivant, le premier résultat correspondant étant retourné :
       - WAP
       - Commutateur/port Ethernet
       - Commutateur Ethernet
       - Sous-réseau

3. Lorsque le client Teams effectue un appel d’urgence, l’emplacement d’urgence est transmis au réseau RTC.

La possibilité d’effectuer un routage automatique vers le point de réponse de sécurité publique (PSAP) approprié varie en fonction du pays d’utilisation de l’utilisateur Teams.

Les plans d’appels Microsoft, les partenaires Operator Connect et les partenaires Teams Phone Mobile incluent des services de routage d’urgence dynamiques pour les utilisateurs du États-Unis et du Canada.

Toutefois, pour le routage direct, une configuration supplémentaire est nécessaire pour le routage des appels d’urgence et éventuellement pour la connectivité des partenaires. L’administrateur doit s’assurer que le routage de passerelle RTC de l’appel d’urgence a été configuré pour ajouter des informations d’emplacement à l’INVITE sortante (en définissant le paramètre PidfloSupported sur True sur l’objet de passerelle RTC en ligne. En outre, l’administrateur doit configurer la connexion à un fournisseur de service de routage d’urgence (ERS) (États-Unis et Canada) **OU** configurer le contrôleur de frontière de session (SBC) pour une application ELIN (Emergency Location Identification Number). Pour plus d’informations sur les fournisseurs ERS, consultez [Contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md).

Cet article contient les sections suivantes.

- [Attribuer des adresses d’urgence](#assign-emergency-addresses)
- [Configurer les paramètres réseau](#configure-network-settings)
- [Configurer le service d’informations sur l’emplacement](#configure-location-information-service)
- [Configurer des stratégies d’urgence](#configure-emergency-policies)
- [Activer les utilisateurs et les sites](#enable-users-and-sites)
- [Tester les appels d’urgence](#test-emergency-calling)

Pour plus d’informations sur les appels d’urgence, notamment des informations sur les adresses d’urgence et le routage des appels d’urgence, des informations spécifiques aux pays et des informations sur les paramètres réseau et la topologie du réseau, consultez les rubriques suivantes :

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les paramètres réseau pour les fonctionnalités vocales cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)

Pour plus d’informations sur les fonctionnalités disponibles dans les clouds gouvernementaux, consultez [Prise en charge du](#government-support) secteur public à la fin de cet article.


## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont actuellement pris en charge.  Revenez souvent pour voir les mises à jour de cette liste.

- Client de bureau Teams pour Microsoft Windows
- Client de bureau Teams pour Apple macOS
- Client mobile Teams pour le client iOS Apple version 1.0.92.2019121004 et App Store version 1.0.92 et ultérieure
- Client mobile Teams pour client Android et Google Play Store version 1416/1.0.0.2019121201 et versions ultérieures
- Téléphone Teams version 1449/1.0.94.2019110802 et versions ultérieures
- salles Teams version 4.4.25.0 et ultérieure

> [!NOTE]
> Les emplacements basés sur les sous-réseaux et wi-fi sont pris en charge sur tous les clients Teams pris en charge. <br><br>
> Ethernet/Switch (LLDP) est pris en charge sur :
> - Windows versions 10.0 et ultérieures pour l’instant.<br>
> - Mac OS, qui nécessite un [logiciel d’activation LLDP](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - Téléphone Teams avec l’application Teams version 1449/1.0.94.2021110101 et ultérieures.

> [!NOTE]
> Les appels d’urgence dynamiques, y compris les notifications du bureau de sécurité, ne sont pas pris en charge sur le client web Teams. Pour empêcher les utilisateurs d’utiliser le client web Teams pour appeler des numéros RTC, vous pouvez définir une stratégie d’appel Teams et désactiver le paramètre **Autoriser les appels RTC web** . Pour plus d’informations, consultez [Stratégies d’appel dans Teams](teams-calling-policy.md) et [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> Les téléphones 3PIP ne prennent pas en charge les appels d’urgence dynamiques. 



## <a name="assign-emergency-addresses"></a>Attribuer des adresses d’urgence

Vous pouvez attribuer des adresses d’urgence comme suit :

- Aux utilisateurs du forfait d’appels.

- Aux utilisateurs&mdash;Operator Connect et Teams Phone Mobile en fonction des fonctionnalités attribuées au numéro lorsque l’opérateur les charge dans l’inventaire d’un client.

- Aux identificateurs réseau requis pour l’obtention dynamique d’un emplacement. 

Pour prendre en charge le routage automatisé des appels d’urgence dans le États-Unis, vous devez vous assurer que les emplacements d’urgence affectés aux identificateurs réseau incluent les codes géographiques associés. (Les adresses d’urgence sans codes géographiques ne peuvent pas être affectées aux identificateurs réseau requis pour les emplacements dynamiques.)

Azure Maps est utilisé pour les services basés sur l’emplacement. Lorsque vous entrez une adresse d’urgence à l’aide du Centre d’administration Microsoft Teams, Teams vérifie Azure Maps pour l’adresse :

- Si une correspondance est trouvée, les codes géographiques sont automatiquement inclus.

- Si aucune correspondance n’est trouvée, vous aurez la possibilité de créer manuellement une adresse d’urgence. Pour ce faire, vous pouvez utiliser la fonctionnalité de suppression du code confidentiel. 

> [!NOTE]
> Les adresses d’urgence datant de plus de deux ans ne peuvent pas être affectées à des identificateurs réseau. Vous devez recréer des adresses plus anciennes.

Vous ajoutez et affectez des adresses d’urgence dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour plus d’informations, consultez [Ajouter un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md) et [Attribuer un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurer les paramètres réseau

Les paramètres réseau sont utilisés pour déterminer l’emplacement d’un client Teams et pour obtenir dynamiquement des stratégies d’appel d’urgence et un emplacement d’urgence. Vous pouvez configurer les paramètres réseau en fonction de la façon dont votre organisation souhaite que les appels d’urgence fonctionnent.

Les paramètres réseau incluent des sites qui incluent une collection de sous-réseaux et ceux-ci sont utilisés exclusivement pour l’attribution de stratégie dynamique aux utilisateurs. Par exemple, une stratégie d’appel d’urgence et une stratégie de routage des appels d’urgence peuvent être affectées au « site de Redmond » afin que tout utilisateur itinérant depuis son domicile ou un autre emplacement Microsoft soit configuré avec des numéros d’urgence, un routage et un bureau de sécurité spécifique à Redmond.  

Les adresses IP approuvées contiennent une collection d’adresses IP externes Internet du réseau d’entreprise et sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise. Une tentative d’obtention d’une stratégie ou d’un emplacement dynamique n’est effectuée que si l’adresse IP externe de l’utilisateur correspond à une adresse IP dans l’adresse IP approuvée.

Pour plus d’informations sur les adresses IP, les régions réseau, les sites et les adresses de sous-réseau, consultez [Paramètres réseau pour les fonctionnalités vocales cloud](cloud-voice-network-settings.md).

Vous configurez les paramètres réseau dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour en savoir plus, consultez [Gérer la topologie de votre réseau pour les fonctionnalités vocales cloud](manage-your-network-topology.md).

Notez que la propagation de certaines modifications des paramètres réseau (telles qu’une nouvelle adresse, un identificateur réseau, etc.) peut prendre un certain temps (jusqu’à quelques heures) et être disponibles pour les clients Teams.  

> [!Note]
> Les sous-réseaux peuvent également être définis dans LIS et peuvent être associés à un emplacement d’urgence.  Les sous-réseaux LIS doivent être définis par l’ID réseau correspondant à la plage d’adresses IP de sous-réseau attribuée aux clients. Par exemple, l’ID réseau d’une adresse IP/masque cliente de 10.10.10.150/25 est 10.10.128. Pour plus d’informations, consultez [Comprendre les principes de base de l’adressage TCP/IP et du sous-réseau](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Les recherches de paramètres de configuration réseau ne sont pas prises en charge avec les déploiements de service de proxy cloud qui modifient les adresses IP sources des clients Teams.



**Pour les utilisateurs du forfait d’appels, de l’opérateur Connect et de Teams Phone Mobile :**

- Si une configuration dynamique de la notification du bureau de sécurité est requise, vous devez configurer à la fois des adresses IP approuvées et des sites réseau.

- Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP approuvées ; la configuration des paramètres réseau n’est pas obligatoire.

- Si aucun des deux n’est requis, la configuration des paramètres réseau n’est pas obligatoire. 

**Pour les utilisateurs de routage direct :**

- Si l’activation dynamique de l’appel d’urgence ou la configuration dynamique de la notification du bureau de sécurité est requise, vous devez configurer des adresses IP approuvées et des sites réseau.

- Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP approuvées ; la configuration des paramètres réseau n’est pas obligatoire.

- Si aucun des deux n’est requis, la configuration des paramètres réseau n’est pas obligatoire.


## <a name="configure-location-information-service"></a>Configurer le service d’informations sur l’emplacement

Un client Teams obtient des adresses d’urgence à partir des emplacements associés à différents identificateurs réseau. 

Pour qu’un client obtienne un emplacement, vous devez remplir le lis avec des identificateurs réseau (sous-réseaux, WAP, commutateurs, ports) et des emplacements d’urgence. Vous pouvez le faire dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à **Emplacements Réseaux** > **& emplacements**.
2. Cliquez sur l’onglet qui représente l’identificateur réseau que vous souhaitez ajouter. Par exemple, cliquez sur **Sous-réseaux**, **Points d’accès Wi-Fi**, **Commutateurs** ou **Ports**. Cliquez ensuite sur **Ajouter**.
3. Renseignez les champs, ajoutez un emplacement d’urgence, puis cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez les applets de commande suivantes pour ajouter des ports, des commutateurs, des sous-réseaux et des wanps au LIS.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si les sous-réseaux sont utilisés dans le cadre de sites réseau, ils doivent être redéfinis dans le service d’informations de localisation pour afficher les emplacements dynamiques.

## <a name="configure-emergency-policies"></a>Configurer des stratégies d’urgence

Utilisez les stratégies suivantes pour configurer les appels d’urgence. Vous pouvez gérer ces stratégies dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell.

- **Stratégie de routage des appels d’urgence : s’applique uniquement au routage direct**. Cette stratégie configure les numéros d’urgence, les masques par numéro si vous le souhaitez et l’itinéraire RTC par numéro. Vous pouvez affecter cette stratégie aux utilisateurs, aux sites réseau ou aux deux. Pour plus d’informations, consultez [Gérer les stratégies de routage des appels d’urgence pour le routage direct](manage-emergency-call-routing-policies.md).  

   (Les utilisateurs du forfait d’appels, de l’opérateur Connect et de Teams Phone Mobile sont automatiquement activés pour les appels d’urgence avec les numéros d’urgence du pays en fonction de leur emplacement d’utilisation Microsoft 365 ou Office 365.)

- **Stratégie d’appel d’urgence : s’applique aux forfaits d’appels, à Operator Connect, à Teams Phone Mobile et au routage direct.** Cette stratégie configure l’expérience de notification du service de sécurité lorsqu’un appel d’urgence est effectué. Vous pouvez définir les personnes à notifier et leur mode de notification. Par exemple, pour avertir automatiquement le bureau de sécurité de votre organisation et lui faire écouter les appels d’urgence.  Cette stratégie peut être attribuée aux utilisateurs ou aux sites réseau, ou aux deux. Pour en savoir plus, consultez [Gérer les stratégies d’appel d’urgence dans Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Activer les utilisateurs et les sites

Vous pouvez affecter des stratégies de routage des appels d’urgence et des stratégies d’appel d’urgence aux utilisateurs et aux sites. N’oubliez pas que les stratégies de routage des appels d’urgence s’appliquent uniquement au routage direct. (Bien qu’il soit possible d’affecter cette stratégie à un utilisateur forfait d’appels, Opérateur Connect ou Téléphone Mobile Teams, la stratégie n’aura aucun effet.)

Vous attribuez des stratégies dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Pour en savoir plus, consultez les articles :

- [Gérer les stratégies de routage des appels d’urgence pour le routage direct](manage-emergency-call-routing-policies.md)
- [Gérer les stratégies d’appel d’urgence dans Teams](manage-emergency-calling-policies.md)

Voici des exemples PowerShell :

Pour activer un utilisateur spécifique pour la notification du bureau de sécurité, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Pour affecter une stratégie appelée « Stratégie d’appel d’urgence Contoso 1 » au site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Pour activer un utilisateur de routage direct spécifique pour les appels d’urgence, utilisez la commande suivante :

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Pour affecter une stratégie appelée « Routage des appels d’urgence Contoso New York » au site 1, utilisez la commande suivante :

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie affectée à l’utilisateur.

## <a name="test-emergency-calling"></a>Tester les appels d’urgence

Certains fournisseurs de services de routage d’urgence dans le États-Unis proposent un bot de test d’appel d’urgence.

- Les **utilisateurs du forfait d’appels, de la connexion opérateur et de Teams Phone Mobile dans le États-Unis ou au Canada** peuvent utiliser le numéro d’urgence de test prédéfini 933 pour valider leur configuration d’appel d’urgence. Ce numéro est acheminé vers un bot, qui renvoie ensuite le numéro de téléphone de l’appelant (ID de ligne d’appel), l’adresse d’urgence ou l’emplacement, et indique si l’appel est automatiquement routé vers le PSAP ou filtré en premier.

- **Les clients de routage direct dans le États-Unis** doivent se coordonner avec leur ERSP pour un service de test.

## <a name="government-support"></a>Soutien du gouvernement

Le tableau suivant indique la prise en charge des appels d’urgence dynamiques dans les clouds gouvernementaux :

| Nuage | Disponibilité |
| :------------|:-------|
| World Wide MultiLocataire | Disponible sur tous les clients Teams |
| GCC | Disponible sur tous les clients Teams |
| GCCH | -Disponible sur le bureau Teams <br> -Disponible sur les clients mobiles Teams <br> -Disponible sur les téléphones Teams, version de l’application : 1449/1.0.94.2022061702 |
| Dod | -Disponible sur le bureau Teams <br>-Disponible sur les clients mobiles Teams <br>-En attente sur les téléphones Teams |

 ## <a name="related-topics"></a>Rubriques connexes

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage des appels d’urgence ](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Attribuer ou modifier un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Paramètres réseau pour les fonctionnalités voix Cloud](cloud-voice-network-settings.md)
- [Gérer votre topologie du réseau pour les fonctionnalités de voix cloud](manage-your-network-topology.md)
