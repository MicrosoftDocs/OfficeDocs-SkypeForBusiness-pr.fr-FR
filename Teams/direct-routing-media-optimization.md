---
title: Optimisation des éléments multimédias locaux du routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Optimisation du contenu multimédia local pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886dd4d14d8393764f3c939991a8959ed4726aa3
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686460"
---
# <a name="local-media-optimization-for-direct-routing"></a>Optimisation du contenu multimédia local pour le routage direct

Le réseau téléphonique public commuté (RTC) est considéré comme une application vitale pour les entreprises dont la qualité de la voix est élevée. Le routage direct vous permet de contrôler les flux de trafic multimédia pour accepter une multitude de topologies réseau et de configuration de téléphonie locale pour différentes entreprises dans le monde entier. 

L’optimisation des éléments multimédias locaux pour le routage direct vous permet de gérer la qualité de la voix.

-   Contrôle du flux de trafic multimédia entre les clients teams et les contrôleurs de frontière de session client (SBCs).
-   Conservation de l’emplacement local des contenus multimédias dans les limites des sous-réseaux du réseau d’entreprise.
-   Autorisant les flux multimédias entre les clients teams et les éléments SBCs, même si les éléments SBCs sont situés derrière des pare-feux d’entreprise disposant d’une IPs privée et ne sont pas visibles par Microsoft directement.

L’optimisation des éléments multimédias locaux prend en charge deux scénarios :

- Centralisation de toutes les lignes locales par le biais d’un SBC centralisé connecté au Trunk SIP (Session Initiation Protocol) principal, fournissant des services de téléphonie à toutes les succursales locales de l’entreprise.

-   Création d’une topologie de réseau virtuel de type SBCs--où les éléments SBCs dans les succursales locales sont connectés à un SBC proxy centralisé qui est visible par le système Microsoft Phone et en communiquant avec ce système par le biais de son adresse IP externe. Dans une topologie de réseau virtuel, les éléments SBCs en aval permettent de communiquer par le biais d’une IPs interne et ne sont pas directement visibles par le système téléphonique.

Cet article décrit les fonctionnalités de fonctionnalité, et les scénarios et solutions de clients. Pour plus d’informations sur la configuration, voir [configurer l’optimisation des médias locaux](direct-routing-media-optimization-configure.md). 

  > [!NOTE]
  > Si vous souhaitez conserver les éléments multimédias locaux dans les limites de votre intranet, l’optimisation du contenu multimédia local est recommandée. Si vous avez déjà une dérivation multimédia et que vous utilisez uniquement les adresses IP publiques de votre SBCs, il n’est pas obligatoire de procéder à une optimisation de média locale. Vous pouvez continuer à utiliser le contournement multimédia. Pour plus d’informations, voir [planifier un contournement de média](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Scénarios clients pris en charge

Pour cette discussion, supposez que contoso exécute plusieurs entreprises sur le globe comme suit. (Notez que les régions Europe et APAC ne sont utilisées qu’à titre d’exemple. Une société peut avoir plusieurs régions différentes ayant des exigences similaires.)
 
- **En Europe**, contoso dispose de bureaux dans approximativement 30 pays. Chaque succursale possède son propre échange de succursale privée. 

  Contoso a offert une option de centralisation des Trunks au sein d’un emplacement--Amsterdam--pour les 30 bureaux européens. Contoso a déployé l’SBC dans Amsterdam, à condition de disposer d’une bande passante suffisante pour exécuter les appels par le biais de l’emplacement centralisé, connecté un Trunk SIP central à l’emplacement centralisé et commencé à utiliser tous les emplacements d’Amsterdam. 

- **Dans la région APAC**, Contoso possède plusieurs bureaux dans différents pays. 

  Dans de nombreux pays, l’entreprise dispose toujours de lignes de multiplexage de répartition du temps dans les succursales locales. La centralisation des lignes de TDM n’est pas une option disponible dans la région de l’APAC, donc le passage à SIP n’est pas possible. Supposez qu’il y a plus de 50 de succursales Contoso dans la région APAC avec des centaines de passerelles (SBCs). Dans ce scénario, il n’est pas possible de jumeler toutes les passerelles vers l’interface de routage directe en raison d’un manque d’adresses IP publiques et/ou de points de suite Internet locaux. De plus, certains pays imposent des exigences réglementaires qui ne peuvent pas être satisfaites sans connexion réseau PSTN locale.

Selon les besoins de votre entreprise, Contoso a implémenté deux solutions avec une optimisation de média locale pour le routage direct :

- **En Europe**, toutes les lignes sont centralisées et multimédias entre le SBC central et les utilisateurs, en fonction de l’emplacement de l’utilisateur. 

  - Si un utilisateur est connecté au sous-réseau local d’un réseau d’entreprise (c’est-à-dire, l’utilisateur est interne), le contenu multimédia est transmis entre l’adresse IP interne de l’SBC central et du client teams de l’utilisateur. 
  
  - Si un utilisateur ne se trouve pas dans les limites du réseau d’entreprise, par exemple, si l’utilisateur utilise une connexion Internet sans fil publique, l’utilisateur est considéré comme externe. Dans ce cas, les éléments multimédias sont acheminés entre l’adresse IP externe de la SBC centrale et celle du client Teams.

- **Dans la région APAC**, un proxy centralisé SBC est associé au routage direct Microsoft, qui transmet les éléments multimédias entre l’interface de routage directe et l’interface de routage directe en aval dans les agences locales. 

  L’intérieur de l’intérieur des bureaux de succursales locaux n’est pas directement visible pour le routage direct au sein de l’Asie de l’est, mais il est couplé en utilisant l’applet de connexion Set-CSOnlinePSTNGateway pour créer une topologie de réseau virtuel dans le système Microsoft Phone. Le contenu multimédia reste toujours local dans la mesure du possible. Les utilisateurs externes disposent de contenus multimédias entre le client teams et l’adresse IP publique du proxy SBC.


## <a name="central-sbc-with-centralized-trunks"></a>SBC central avec Trunks centralisées

Pour créer une solution dans laquelle les services RTC sont fournis à toutes les succursales locales par le biais d’un SBC central unique avec un Trunk SIP centralisé connecté, l’administrateur client de contoso associe un SBC (centralsbc.contoso.com) au service. un Trunk SIP centralisé est connecté à l’SBC. 

- Lorsqu’un utilisateur se trouve sur le réseau interne de l’entreprise, l’SBC fournit l’adresse IP interne de l’SBC pour le média. 

- Lorsqu’un utilisateur se trouve en dehors du réseau d’entreprise, l’SBC fournit la adresse IP externe (publique) de l’SBC.

Remarque : toutes les valeurs dans les exemples, tableaux ou diagrammes sont présentés à des fins d’illustration uniquement.

Tableau 1. Exemples de paramètres réseau pour SBCs 

| Lieu | NOM DE DOMAINE COMPLET SBC | Sous-réseau interne | NAT externe (IP de confiance) | Adresse IP externe d’une SBC | Adresse IP interne de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Allemagne | Non déployée | 192.168.6.0/24 | 172.16.76.74 | Non déployée |  Non déployée |
| France | Non déployée | 192.168.7.0/24 | 172.16.76.75 | Non déployée |  Non déployée ||||


### <a name="internal-user"></a>Utilisateur interne

Le schéma suivant illustre le flux de trafic quand un utilisateur est connecté au réseau d’entreprise dans le bureau ou le site d’origine de l’utilisateur. 

Sur site, l’utilisateur est affecté à la succursale locale d’Allemagne. L’utilisateur effectue un appel téléphonique de routage direct par le biais d’équipes.

- Le client teams de l’utilisateur communique avec le système téléphonique directement par le biais de l’API REST, mais le média généré lors de l’appel est transmis à l’adresse IP interne de l’SBC central. 

- Le SBC redirige le flux vers le système téléphonique et le réseau PSTN connecté. 

- Le SBC central est visible par le système téléphonique par le biais de l’adresse IP externe uniquement. 

Diagramme 1. Flux de trafic lorsque l’utilisateur se trouve sur le site « maison » avec un SBC centralisé et un Trunk SIP centralisé connecté

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-1.png "Flux de trafic lorsque l’utilisateur se trouve sur un site d’accueil avec une SBC centralisée avec un trunking SIP centralisé connecté")


### <a name="external-user"></a>Utilisateur externe

Le diagramme suivant illustre le flux de trafic quand un utilisateur n’est pas en local et n’est pas connecté au réseau d’entreprise (c’est-à-dire que l’appareil de l’utilisateur est connecté à Internet par le biais d’un appareil mobile ou d’un Wi-Fi public). L’utilisateur effectue un appel téléphonique de routage direct par le biais d’équipes :

- Le client teams de l’utilisateur communique avec son système téléphonique directement par le biais de l’API REST, mais dans ce cas, le média généré lors de l’appel est transmis à l’adresse IP externe de l’SBC central. 

- Le SBC redirige le flux vers le système téléphonique et le réseau PSTN connecté. 

- Le SBC central est visible par le système téléphonique par le biais de l’adresse IP externe uniquement. 

Dans le cas présent, il s’agit de la même façon que l’utilisateur est local de la succursale en Allemagne ou à n’importe quelle autre succursale. L’utilisateur est considéré comme extérieur, car il se trouve en dehors des limites du réseau d’entreprise.

Diagramme 2. Flux de trafic lorsque l’utilisateur est externe avec un SBC centralisé et un Trunk SIP centralisé connecté

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-2.png "Flux de trafic lorsque l’utilisateur est externe en cas de SBC centralisé avec un trunking SIP centralisé connecté")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy avec connexion SBCs en aval

Pour créer une solution dans laquelle les services RTC sont fournis dans toutes les succursales locales de la région Asie de l’est, où la centralisation des Trunks TDM n’est pas une option, l’administrateur de contoso (proxysbc.contoso.com), également appelé SBC proxy, pour le service de routage direct. 

Par la suite, l’administrateur de contoso ajoute une partie SBCs en aval indiquant qu’il est possible de joindre par le biais du proxy SBC proxysbc.contoso.com. Les fonctions SBCs en aval ne possèdent pas d’IPs public, mais peuvent être affectées à des itinéraires vocaux. Le tableau ci-dessous répertorie des exemples de paramètres réseau et de configuration.

Lorsqu’un utilisateur se trouve dans la succursale locale où se trouve l’SBC en aval, le trafic multimédia passe entre l’utilisateur et le SBC en aval directement. Si un utilisateur ne se trouve pas dans l’entreprise (sur une connexion Internet publique), les éléments multimédias passent de l’utilisateur à l’adresse IP publique du proxy SBC, qui le transmet aux SBC en aval correspondants.

Tableau 2. Exemple d’informations réseau SBC

| Lieu | NOM DE DOMAINE COMPLET SBC | Sous-réseau interne | NAT externe (IP de confiance) | Adresse IP externe d’une SBC  | Adresse IP interne de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Aucun |  192.168.1.5 |
| Indonésie  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Aucun |  192.168.2.5 |
| Singapour | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Utilisateur interne 

Le diagramme suivant illustre le flux de trafic de haut niveau pour le scénario lorsque l’utilisateur se trouve à l’intérieur du bureau dans la région APAC. L’utilisateur, qui est affecté à une succursale locale au Viêt Nam et est en local, effectue un appel téléphonique de routage direct par le biais d’équipes. 

- Le client teams de l’utilisateur communique avec le système téléphonique directement par le biais de l’API REST, mais les éléments multimédias générés lors de l’appel sont transmis à l’adresse IP interne d’un SBC local.

- Le SBC local redirige le flux vers l’SBC proxy sur Singapour et sur le réseau PSTN local connecté.

-  L’SBC proxy est visible pour le système téléphonique par le biais de l’adresse IP externe uniquement et route le flux de l’SBC en aval (dans ce cas, l’SBC local en Vietnam) vers le système téléphonique. 

- La ligne SBC en aval de la succursale locale n’est pas visible par le système téléphonique directement, mais elle est mappée dans la topologie du réseau virtuel définie par l’administrateur de contoso lors de la configuration de l’optimisation des médias locaux.

Remarque : le comportement peut être différent pour les utilisateurs locaux et les utilisateurs non locaux, en fonction du mode d’optimisation de média local configuré. 

Pour plus d’informations sur les modes et le comportement pertinents, voir Configurer l’optimisation des médias locaux.

Diagramme 3. Flux de trafic lorsque l’utilisateur se trouve sur le réseau « domestique » avec un SBC proxy et une connexion SBCs en aval 

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-3.png "Flux de trafic dans le cas d’une SBC de proxy avec une connexion SBCs en aval lorsque l’utilisateur se trouve sur le réseau « domestique »")

### <a name="external-user"></a>Utilisateur externe

Le diagramme suivant illustre le flux de trafic quand un utilisateur se trouve en dehors des frontières du réseau d’entreprise. L’utilisateur n’est pas en local (ne se trouve pas dans les limites du réseau d’entreprise). L’utilisateur effectue un appel vers un numéro de téléphone au Viêt Nam par le biais d’équipes. 

- Le client teams de l’utilisateur communique avec le système téléphonique directement par le biais de l’API REST, mais le média généré lors du flux d’appels est d’abord transmis à l’adresse IP externe du proxy SBC dans Singapour. 

- En fonction des stratégies de configuration et de voix (pour plus d’informations, voir [configurer l’optimisation de médias locaux](direct-routing-media-optimization-configure.md) ), le proxy SBC redirige le flux vers l’SBC en aval au Viêt Nam. 

- L’SBC en aval dans le Viêt Nam redirige le flux vers le réseau PSTN local connecté. 

- L’SBC proxy est visible par le système téléphonique par le biais de l’adresse IP externe uniquement.

-  La ligne SBC en aval de la succursale locale n’est pas visible par le système téléphonique directement, mais elle est mappée dans la topologie du réseau virtuel définie par l’administrateur de contoso lors de la configuration de l’optimisation des médias locaux. Dans l’exemple, l’utilisateur est considéré comme extérieur, car il ne se trouve pas dans les limites du réseau d’entreprise. 

Diagramme 4. Flux de trafic lorsque l’utilisateur est externe avec un SBC proxy et avec une connexion SBCs en aval

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-4.png "Flux de trafic dans le cas d’une SBC de proxy avec une connexion SBCs en aval lorsque l’utilisateur est externe")

## <a name="local-media-optimization-modes"></a>Modes d’optimisation des médias locaux

L’optimisation des éléments multimédias locaux prend en charge deux modes :

- **Mode 1 : toujours contournement**. Dans le cas présent, si l’utilisateur est interne, le média passe par l’adresse IP interne de l’SBC en aval local, quel que soit l’emplacement réel de l’utilisateur interne ; par exemple, au sein de la même succursale où se trouve l’SBC en aval ou dans une autre succursale.  

- **Mode 2 : uniquement pour les utilisateurs locaux**. Dans ce mode, les éléments multimédias seront acheminés directement vers l’adresse IP interne de l’SBC en aval uniquement en cas de génération par l’utilisateur interne situé dans la même succursale que l’SBC aval. 

Pour faire la distinction entre les modes d’optimisation des éléments multimédias locaux, l’administrateur client doit définir le paramètre-BypassMode sur « toujours » ou « OnlyForLocalUsers » pour chaque SBC à l’aide de l’applet de Set-CSonlinePSTNGateway. Pour plus d’informations, voir [configurer l’optimisation des éléments multimédias locaux](direct-routing-media-optimization-configure.md).  

 > [!NOTE]
  > Lorsque les utilisateurs sont internes, la connectivité multimédia entre l’utilisateur et l’SBC sur l’adresse IP interne est **requise**. Dans le cas présent, il n’y a pas de recours aux relais de transport public pour le contenu multimédia, car l’SBC fournira une adresse IP interne pour la connectivité multimédia. 

### <a name="mode-1-always-bypass"></a>Mode 1 : toujours contournement

Si vous avez une bonne connexion entre les succursales, le mode recommandé est toujours contournement.
 
Par exemple, supposons qu’une entreprise dispose d’un Trunk SIP centralisé dans Amsterdam, qui dessert 30 pays et qui dispose d’une bonne connectivité entre les 30 sites et les utilisateurs locaux. Il existe également une branche en Allemagne qui déploie un SBC local.

L’SBC en Allemagne peut être configuré en mode « toujours contournement ». Les utilisateurs, quel que soit leur lieu, se connectent directement à la SBC par le biais de l’adresse IP interne de l’SBC (par exemple, de France à Allemagne ; Voir le diagramme ci-dessous pour référence).

Ce qui suit décrit deux scénarios :

- Scénario 1. L’utilisateur se trouve au même emplacement que l’SBC défini dans la politique de routage de la voix en ligne.

- Scénario 2. L’utilisateur et les passerelles se trouvent dans différents sites.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Scénario 1. L’utilisateur se trouve au même emplacement que l’SBC défini dans la politique de routage de la voix en ligne

L’SBC dans Amsterdam est configuré en tant que SBC proxy d’un SBC local en Allemagne. L’utilisateur se trouve en Allemagne au sein du même sous-réseau que le réseau d’entreprise de l’SBC local. Les éléments SBCs (proxy et aval) sont configurés pour toujours le mode contournement. Les stratégies de routage de la voix en ligne indiquent que, en cas d’appel en Allemagne (avec indicatif + 49), elles doivent être routées vers l’SBC local en Allemagne. Tous les autres appels, et en cas d’échec de la SBC en Allemagne, les appels en Allemagne-doivent être routés vers l’SBC de proxy d’Amsterdam. Le tableau suivant récapitule les exemples de configuration. 

Tableau 3. Exemple de configuration pour le scénario 1

| Emplacement physique de l’utilisateur | Un utilisateur effectue un appel vers un numéro | Politique de routage de la voix en ligne | Mode configuré pour SBC | Flux multimédia | 
|:------------|:-------|:-------|:-------|:-------|
| Allemagne | commande + 49 1 437 2800 | Priorité 1 : ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com<br>Priorité 2 :. *-proxysbc.contoso.com| DEsbc.contoso.com : toujours contournement <br>proxysbc.contoso.com : toujours contournement | < des utilisateurs d’équipes – > DEsbc.contoso.com |

Le diagramme ci-dessous illustre le flux de trafic de haut niveau pour l’utilisateur interne en Allemagne effectuant un appel vers un téléphone de routage directe via teams vers le numéro en Allemagne. 

- Le client teams de l’utilisateur communique directement avec le système téléphonique par le biais de l’API REST. 

- Le média généré lors de l’appel est transmis à l’adresse IP interne de l’SBC local. 

- Le SBC local redirige le flux vers l’SBC proxy dans Amsterdam et au réseau PSTN local connecté. 

- L’SBC proxy est visible pour le système téléphonique par le biais de l’adresse IP externe uniquement et route le flux de l’SBC en aval (dans ce cas, l’SBC local en Allemagne) vers le système téléphonique. 

- La ligne SBC en aval de la succursale locale n’est pas visible par le système téléphonique directement, mais elle est mappée dans la topologie du réseau virtuel définie par l’administrateur de contoso lors de la configuration de l’optimisation des médias locaux.


Diagramme 5.  Flux de trafic avec le mode « toujours Bypass » et l’utilisateur se trouve sur le site « maison »

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-5.png "Flux de trafic avec le mode « toujours Bypass » et l’utilisateur dans le site « Home »")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scénario 2 : l’utilisateur et les passerelles se trouvent dans différents sites

L’SBC dans Amsterdam est configuré en tant que SBC proxy d’un SBC local en Allemagne. Les éléments SBCs (proxy et aval) sont configurés pour toujours le mode contournement. Les utilisateurs internes situés en France, situés dans la succursale locale, effectuent un appel de routage direct vers l’Allemagne. Les stratégies de routage vocal en ligne permettent de rediriger les appels vers l’Allemagne (avec l’indicatif de la région + 49) vers l’SBC local en Allemagne. Tous les autres appels, et en cas d’échec de la SBC en Allemagne, tous les appels en Allemagne-doivent être routés vers l’SBC du proxy d’Amsterdam. Le tableau suivant récapitule les exemples de configuration. 

Tableau 4. Exemple de configuration pour le scénario 2

| Emplacement physique de l’utilisateur | Un utilisateur effectue un appel vers un numéro | Politique de routage de la voix en ligne | Mode configuré pour SBC | Flux multimédia | 
|:------------|:-------|:-------|:-------|:-------|
| France | commande + 49 1 437 2800 | Priorité 1 : ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com <br>Priorité 2 :. *-proxysbc.contoso.com |  DEsbc.contoso.com : toujours contournement de proxysbc.contoso.com – toujours contournement | < des utilisateurs d’équipes – > DEsbc.contoso.com  |

Le diagramme suivant illustre le flux de trafic de haut niveau lorsque l’utilisateur allemand interne situé en France effectue un appel direct par le biais d’équipes au numéro en Allemagne. 

- Le client teams de l’utilisateur communique directement avec le système téléphonique par le biais de l’API REST.

- Le contenu multimédia généré au cours de l’appel passe directement à l’adresse IP interne de l’SBC en Allemagne. 

- L’SBC en Allemagne redirige le flux vers l’SBC du proxy dans Amsterdam et au réseau PSTN local connecté. 

Diagramme 6.  Flux de trafic avec le mode « toujours Bypass » et l’utilisateur n’est pas sur le site « Home » mais sur le réseau interne

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-6.png "Flux de trafic avec le mode « toujours Bypass » et l’utilisateur ne se trouve pas sur le site « Home » mais dans le réseau interne")

### <a name="mode-2-only-for-local-users"></a>Mode 2 : uniquement pour les utilisateurs locaux

S’il existe des connexions incorrectes entre les succursales locales mais une bonne connexion entre chaque succursale locale et votre bureau régional, le mode recommandé est « uniquement pour les utilisateurs locaux ».

Par exemple, dans la région APAC, Contoso possède plusieurs bureaux dans différents pays. Dans de nombreux pays, le basculement vers SIP n’est pas possible, car l’entreprise dispose toujours de lignes TDM dans de nombreux agences locales. La centralisation des lignes TDM n’est pas une option disponible dans la région de l’APAC. De plus, il existe de plus de 50 contoso succursales dans la région APAC avec des centaines de passerelles (SBCs). 

Pour créer une solution dans laquelle les services RTC sont fournis dans tous les bureaux de succursales locaux dans la région APAC où la centralisation des Trunks TDM n’est pas une option, l’administrateur contoso associe un SBC régional à Singapour en tant que proxy SBC vers le service de routage direct. La connexion directe entre les succursales locales n’est pas correcte, mais il existe une bonne connexion entre chaque succursale locale et la ligne SBC régionale dans Singapour. Pour le SBC régional, l’administrateur sélectionne le mode « toujours contournement » et pour l’SBCs local en aval, l’administrateur choisit le mode’uniquement pour les utilisateurs locaux.

Ce qui suit décrit deux scénarios :

- Scénario 1. L’utilisateur se trouve au même emplacement que l’SBC défini dans la politique de routage de la voix en ligne

- Scénario 2. L’utilisateur et les passerelles se trouvent dans différents sites

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Scénario 1. L’utilisateur se trouve au même emplacement que le SBC défini dans la stratégie de routage de la voix en ligne

Supposez que l’SBC dans Singapour est configuré en tant que SBC proxy pour l’SBCs local en amont au Viêt Nam et en Indonésie. L’utilisateur se trouve au Viêt Nam dans le même emplacement que le SBC local. Politiques de routage vocal en ligne spécifiez que les appels au Viêt-Nam (avec l’indicatif de la région + 84) doivent être routés vers l’SBC local au Viêt Nam. Tous les autres appels, et, si la SBC en panne ne fonctionne pas, les appels au Viêt Nam doivent être routés vers l’SBC du proxy dans Singapour. Le tableau suivant récapitule les exemples de configuration. 

Tableau 5. Exemple de configuration pour le mode’uniquement pour les utilisateurs locaux’scénario 1

| Emplacement physique de l’utilisateur | Un utilisateur effectue un appel vers un numéro | Politique de routage de la voix en ligne | Mode configuré pour SBC | Flux multimédia | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | commande + 84 4 3926 3000 | Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br>Priorité 2 :. *-proxysbc.contoso.com | VNsbc.contoso.com – uniquement pour les utilisateurs locaux <br> proxysbc.contoso.com : toujours contournement | < des utilisateurs d’équipes – > VNsbc.contoso.com |

Dans le diagramme suivant, un utilisateur affecté à la succursale locale au Viêt Nam, en local, effectue un appel téléphonique de routage direct par le biais d’équipes. 

- Le client teams de l’utilisateur communique directement avec le système téléphonique par le biais de l’API REST. 

- Le contenu multimédia généré lors de l’appel est transmis à l’adresse IP interne de l’SBC local. 

- Le SBC local redirige le flux vers l’SBC proxy sur Singapour et sur le réseau PSTN local connecté. 

- L’SBC proxy est visible pour le système téléphonique par le biais de l’adresse IP externe uniquement et route le flux de l’SBC en aval (dans ce cas, l’SBC local au Viêt Nam) vers le système téléphonique. 

- La ligne SBC en aval de la succursale locale n’est pas visible par le système téléphonique directement, mais elle est mappée dans la topologie du réseau virtuel.

Diagramme 7. Flux de trafic avec le mode « uniquement pour les utilisateurs locaux » et l’utilisateur dans le site « Accueil »

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-7.png "Flux de trafic avec le mode « uniquement pour les utilisateurs locaux » et l’utilisateur dans le site d’accueil")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scénario 2. L’utilisateur et les passerelles se trouvent dans différents sites

Supposez que l’SBC dans Singapour est configuré en tant que SBC proxy pour l’SBCs local en amont au Viêt Nam et en Indonésie. L’utilisateur interne de l’Indonésie, situé dans la succursale locale, effectue un appel de routage direct au Viêt Nam. Politiques de routage vocal en ligne spécifiez que les appels vers le Viêt Nam (avec l’indicatif de la région + 84) doivent être routés vers l’SBC local au Viêt Nam. Tous les autres appels, et en cas d’échec de l’SBC en Viêt Nam, les appels vers le Viêt Nam doivent être routés vers l’SBC proxy de Singapour. Le proxy SBC dans Singapour est défini sur le mode « toujours contournement » et l’SBC local au Viêt Nam est défini sur « uniquement pour le mode utilisateurs locaux ». Le tableau suivant récapitule les exemples de configuration. 

Tableau 6. Configuration utilisateur

| Emplacement physique de l’utilisateur | Un utilisateur effectue un appel vers un numéro | Politique de routage de la voix en ligne | Mode configuré pour SBC | Flux multimédia | 
|:------------|:-------|:-------|:-------|:-------|
| Indonésie | commande + 84 4 3926 3000 | Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorité 2 :. *-proxysbc.contoso.com |VNsbc.contoso.com – uniquement pour les utilisateurs locaux <br> proxysbc.contoso.com : toujours contournement | < des utilisateurs d’équipes : > < proxysbc.contoso.com-> VNsbc.contoso.com |


Dans le diagramme suivant, l’utilisateur interne, en local, dans la succursale indonésienne, effectue un appel de téléphone de routage direct par le biais d’équipes vers un numéro au Viêt Nam. 

- Le client teams de l’utilisateur communique directement avec le système téléphonique par le biais de l’API REST.

- Le contenu multimédia généré lors de l’appel est transmis d’abord à l’adresse IP interne de proxy SBC. 

- Le proxy SBC dans Singapour redirige le flux vers l’adresse IP interne de l’SBC en aval au Viêt Nam et au système téléphonique. 

- Le SBC en aval en Viêt Nam route le flux vers le réseau PSTN local connecté. 

- L’SBC proxy est visible par le système téléphonique par le biais de l’adresse IP externe uniquement.

- Les bureaux de succursales en aval ne sont pas visibles par le système téléphonique directement, mais ils sont mappés dans la topologie du réseau virtuel.

Diagramme 8.  Flux de trafic avec le mode « uniquement pour les utilisateurs locaux » et l’utilisateur n’est pas sur le site « maison » mais sur le réseau interne

![Diagramme illustrant l’optimisation du flux de trafic local](media/direct-routing-media-op-8.png "Flux de trafic avec le mode « uniquement pour les utilisateurs locaux », l’utilisateur n’est pas sur le site « Accueil », mais dans le réseau interne")

## <a name="known-issues"></a>Problèmes connus

Vous trouverez ci-dessous une liste des problèmes connus actuellement présents dans l’optimisation de média local. Microsoft travaille actuellement à la résolution de ces problèmes.

| Problème | Moyens |
| :--- | :--- |
| Le client teams n’est pas identifié comme **interne** lorsque l’adresse IP du client teams correspond à la liste des adresses IP approuvées du client. | L’optimisation de média locale nécessite que le sous-réseau du client teams correspond à un [sous-](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) réseau configuré par le client.|
| Les remontées des appels entraînent des appels interrompus lorsque le client teams est identifié comme interne.| Désactiver l’optimisation des éléments multimédias locaux sur l’SBC du routage direct.|


