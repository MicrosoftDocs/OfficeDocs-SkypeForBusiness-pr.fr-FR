---
title: Implémenter la qualité de service dans Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Préparez le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5667374b52561af8809ab136646ffaf9d6077ad1
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735129"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implémenter la qualité de Service (QoS) dans les équipes Microsoft

Cet article vous aide à préparer le réseau de votre organisation de qualité de Service (QoS) dans Microsoft Teams.

Vous pouvez utiliser QoS pour hiérarchiser le trafic réseau qui est sensible aux délais réseau sur le trafic est moins sensible. Analogie est que QoS crée virtuel « voies covoiturage » dans vos données réseau afin de certains types de données jamais ou rarement rencontrer des retards.
Lorsque vous le trafic des communications en temps réel telles que les appels ou réunions partagées dans les équipes, vous pouvez classer par priorité plus proposer fiable une expérience utilisateur de qualité professionnelle. Sans une forme de qualité de service, vous pouvez voir les problèmes suivants de qualité vocale et vidéo :

- Gigue – arrivant à différents taux de paquets de médias.
- Perte de paquets – paquets perdus, qui peut aboutir à des mots ou des syllabes manquants.
- Durée d’aller-retour différée (durée aller-retour) – paquets de médias prend beaucoup de temps pour atteindre leurs destinations.

QoS être vraiment efficace, cohérentes paramètres QoS doivent être appliquée de bout en bout dans votre organisation (les ordinateurs des utilisateurs, commutateurs réseau et routeurs vers le nuage), parce que n’importe quelle partie du chemin d’accès ne parvient pas à prendre en charge vos priorités QoS peut diminuer la qualité des appels , vidéo et partage d’écran.

QoS est un mécanisme que vous pouvez utiliser pour définir la priorité certains types de trafic réseau qui sont sensibles aux délais réseau trafic est moins sensible. Analogie est que QoS crée virtuel « voies covoiturage » dans vos données réseau, donc certains types de données jamais ou rarement rencontrer les retards.

Lorsque vous le trafic des communications en temps réel telles que les appels ou réunions partagées dans les équipes, vous pouvez classer par priorité plus proposer fiable une expérience utilisateur de qualité professionnelle. Lorsque vous n’implémentez QoS, gel des écrans partagés dans les réunions, vidéo peut pixellate et décalage de couleurs et les appels vocaux peuvent devenir instable et difficiles ou impossibles à comprendre. QoS être vraiment efficace, cohérentes paramètres QoS doivent être appliquée de bout en bout dans votre organisation (les ordinateurs des utilisateurs, commutateurs réseau et routeurs vers le nuage), parce que n’importe quelle partie du chemin d’accès ne parvient pas à prendre en charge vos priorités QoS peut diminuer la qualité des appels , vidéo et partage d’écran.

![La relation entre les réseaux d’une organisation et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui se connecte à son tour avec les services Office 365 Cloud voix et de conférence sur site.](media/Qos-in-Teams-Image1.png) 

Une seule option disponible pour résoudre QoS de bout en bout est [ExpressRoute Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nous vous recommandons de mettre en œuvre QoS sur votre réseau local. Cette augmentation de la qualité des charges de travail de communication en temps réel au sein de votre déploiement et éviter les goulots d’étranglement. 

Dans la plupart des cas, le réseau de connexion de votre entreprise vers le nuage sera une connexion internet de réseau non géré où vous ne serez pas en mesure de définir de manière fiable QoS. Une des options disponibles pour QoS réellement au bout en bout est [ExpressRoute Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nous vous recommandons d’implémenter QoS sur les parties du réseau de bout en bout, vous pouvez contrôler, à savoir votre réseau local. Cette augmentation de la qualité des charges de travail de communication en temps réel au sein de votre déploiement et éviter les goulots d’étranglement dans votre déploiement existant.

## <a name="prioritize-teams-network-traffic-for-qos"></a>Hiérarchiser les équipes le trafic pour QoS 

Cet article explique comment définir la priorité le trafic des communications en temps réel les équipes, à savoir, audio et vidéo. Vous pouvez également classer les autres types de trafic, en fonction de vos besoins.

Il existe plusieurs façons pour hiérarchiser le trafic, mais le plus courant est à l’aide de services différenciés des indications point (DSCP). Elles peuvent être appliquées (« balisage ») en fonction de plages de ports ou via des objets de stratégie de groupe. Sujets abordés dans cet article. Nous vous recommandons d’utiliser le balisage basé sur les plages de ports, car elle fonctionne pour tous les périphériques, pas seulement ceux liés au domaine.

Contrôler le marquage DSCP via des objets de stratégie de groupe garantit que les ordinateurs à un domaine recevant les paramètres corrects et que seul un administrateur peut gérer.

Il est important de comprendre la qualité de service fonctionne uniquement lorsqu’elle est implémentée sur tous les liens qui se connectent de l’appelant vers un autre. Si vous utilisez QoS sur le réseau interne et un utilisateur se connecte à partir d’un emplacement distant, vous pouvez classer uniquement au sein de votre réseau interne, gérée. Bien que les sites distants peuvent recevoir une connexion gérée en implémentant un réseau privé virtuel (VPN), nous vous recommandons d’éviter d’exécuter le trafic des communications en temps réel via la connexion VPN.

> [!NOTE]
> Il est recommandé d’implémenter le fractionnement tunnel pour les utilisateurs distants connectés VPN optimiser la qualité de l’expérience utilisateur. Télécharger le document [Guide de déploiement-VPN fractionné Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) à partir de MyAdvisor pour plus d’informations.

Dans une organisation globale avec liens gérées qui couvrent continents, il est vivement recommandé QoS, car la bande passante pour ces liens est limitée par rapport à votre réseau local.

## <a name="qos-queues"></a>Files d’attente de QoS

Pour fournir la qualité de service, les périphériques réseau doivent disposer d’un moyen de classer le trafic et doivent être en mesure de faire la distinction audio ou vidéo à partir du reste du trafic réseau. 

Services différenciés (DiffServ) utilise le type de champ services (ToS) dans l’en-tête d’un paquet IPv4/IPv6 pour définir la priorité pour les périphériques réseau. Les six bits les plus significatifs du champ DiffServ sont le point de code de services différenciés ou DSCP. Utilisez cette, le trafic peut être considéré comme un type particulier (par exemple, voix) et puis marqué (101110, ou 46 en décimal pour le trafic vocal), afin que lorsque les périphériques réseau traitent ces marquages, le trafic peut être définie en conséquence (EF transfert, dans Cet exemple).

Le trafic réseau quand un routeur, le trafic est placé dans une file d’attente. Si aucun QoS n’est en place, qu’une seule file d’attente et les données sont considérées comme première-in, sorti. Cela signifie que le trafic vocal (qui est très sensible aux délais) peut être bloqué derrière le trafic des services de diffusion en continu en ligne. Lorsque vous implémentez la qualité de service, vous pouvez définir plusieurs files d’attente en utilisant les fonctionnalités de réductions congestion (par exemple, pondérée aléatoire [de détection au plus tôt et les fonctionnalités de gestion de congestion différents (tels que Cisco priorité et basé sur une classe weighted fair file d’attente [CBWFQ]) WRED]).

![La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.] (media/Qos-in-Teams-Image2.png "La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.")

_La figure 2. Exemples de files d’attente de QoS_

Une fois ces éléments sont en place, il est possible de remettre QoS prévisible parce que le réseau comprend désormais comment classer, de marquer et de définir la priorité du trafic. Du point de vue des équipes, l’étape de configuration plus importante est la classification et le marquage des paquets, mais pour QoS de bout en bout aboutisse, vous devez également Alignez soigneusement la configuration de l’application avec la configuration réseau sous-jacente.

## <a name="teams-qos-scenarios"></a>Scénarios de QoS des équipes

Les instructions pour l’implémentation de QoS pour les équipes repose sur quatre scénarios :

*  **Scénario 1 :** Vous avez déployé ou équipes de déploiement et mettre en œuvre QoS via le balisage basé sur un port. Balisage basé sur le port est la méthode la plus fiable, car elle fonctionne de manière universelle sur toutes les plateformes et est très facile à implémenter.  

*  **Scénario 2 :** Vous avez déployé ou équipes de déploiement et mettre en œuvre QoS par le biais de la liaison d’objet stratégie de groupe. Cette méthode est parfois utilisée en conjonction avec le scénario 1. Bien que ce scénario est entièrement valide, il ne fonctionne que pour les clients à un domaine Windows. Tous les périphériques qui n’est pas un client Windows à un domaine ne sont pas être activé pour le marquage DSCP marquage.

*  **Scénario 3 :** Vous avez déployé Skype pour Business en ligne, y compris QoS mise en réseau et déployez maintenant équipes. Si tel est le cas, Teams respectera la configuration existante et utilisera les même plages de ports et marquage que le client Skype Entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire. 

    > [!NOTE]
    > Si vous utilisez des applications nom QoS balisage via la stratégie de groupe, vous devez ajouter Teams.exe comme nom d’application.

*  **Scénario 4 :** Vous avez déployé ou équipes de déploiement et à mettre en œuvre QoS via basée sur le port de liaison à l’aide d’une plage de ports personnalisés.

## <a name="implement-qos"></a>Mettre en œuvre QoS

Un très haut niveau, l’implémentation de QoS requiert comme suit :

1. Déterminer vos besoins de l’itinéraire et la bande passante.

2. Utilisez le marquage DSCP et des plages de ports de classer le trafic.

3. Configurer les paramètres QoS basée sur la stratégie dans un objet de stratégie de groupe.

4. Vérifiez les plages de ports dans l’objet de stratégie de groupe.

5. Valider QoS en analysant les équipes le trafic sur le réseau.

Lorsque vous préparez implémenter QoS, n’oubliez pas les instructions suivantes :

- Le chemin le plus court vers Office 365 est préférable.

- Fermeture des ports uniquement entraîne une dégradation de la qualité.

- Les obstacles intermédiaires, tels que des serveurs proxy, ne sont pas recommandés.

- Limite le nombre de tronçons :

    - Client à côté du réseau – tronçons de 3 à 5.
    - Fournisseur de services Internet à côté du réseau Microsoft – 3 tronçons
    - Côté du réseau Microsoft vers une destination finale – non pertinents 

Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).

## <a name="determine-bandwidth-requirements"></a>Déterminer les besoins en bande passante

Avant de configurer la QoS pour Microsoft Teams, il est important de préparer votre réseau Microsoft Teams et déterminer vos besoins en bande passante. Fourniture de QoS dans votre réseau requiert la réservation d’un nombre défini de bande passante sur chaque lien pour le trafic en temps réel. (Si cette bande passante n’est pas nécessaire pour le trafic en temps réel à tout moment, il peut être utilisé pour le reste du trafic.)

Encombrement du trafic réseau considérablement impact sur la qualité des médias. Un manque de bande passante entraîne une dégradation des performances et une expérience utilisateur médiocre, envisagez donc de bande passante comme point de départ pour le déploiement des équipes de planification. Comme les équipes d’adoption et de l’utilisation augmente, utiliser des rapports pour effectuer des ajustements nécessaires. 

Le Planificateur de réseau disponible sur FastTrack est utile lorsque vous déterminez les besoins en bande passante.

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a>Configuration requise pour une connexion de votre réseau à côté du réseau Microsoft

La meilleure qualité des médias, les objectifs de performances réseau ou les seuils indiquées dans le tableau 1 sont requis pour une connexion de réseau de votre organisation à la périphérie du réseau Microsoft.

> [!IMPORTANT]
> La connectivité entre un client d’équipes sur votre réseau d’entreprise aux services Office 365 doit respecter les exigences de performances réseau suivantes.

_Le tableau 1. Mesures de performances réseau - client aux services Office 365_

| Mesure | Cible  |
|--------|--------|
| Latence (unidirectionnelle) | < 50 millisecondes |
| Latence (durée d’aller-retour (durée aller-retour) | < 100 millisecondes |
| Perte de paquets en rafale | < 10 % au cours de l’intervalle de 200 millisecondes |
| Perte de paquets | < 1 % pendant les 15 secondes |
| Gigue arrivée entre des batteries de paquets | < 30 millisecondes pendant les 15 secondes |
| Réorganisation des paquets | < 0,05 % en dehors des paquets de commande |

La cible de métrique latence suppose que votre société ou les sites et les bords de Microsoft sont sur le même continent.

Site de votre société à la connexion de périphérie réseau Microsoft inclut le premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil.

La cible de performance réseau suppose que la bande passante appropriée et/ou de planification QoS. En d’autres termes, les conditions s’appliquent directement à du trafic multimédia en temps réel équipes lorsque la connexion réseau est soumis à une charge maximale.

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a>Configuration requise pour une connexion de votre périmètre de réseau à Microsoft réseau edge

Le tableau 2 montre les objectifs en termes de performances réseau ou les seuils qui sont requis pour la connexion entre votre périmètre de réseau et le périmètre du réseau Microsoft. Cela exclut le réseau interne de votre organisation ou des liaisons réseau étendu et est conçue comme un guide quand vous testez le trafic réseau qui est envoyé via internet ou via un réseau de partenaires ExpressRoute.

> [!IMPORTANT]
> La connectivité entre le côté du réseau de votre société sur les côtés de réseau Microsoft doit respecter les exigences de performances réseau suivantes.

_Le tableau 2. Mesures de performances réseau - face à face_

| Mesure | Cible  |
|--------|--------|
| Latence (unidirectionnelle) | < 30 millisecondes |
| Latence (durée d’aller-retour (durée aller-retour) | < 60 millisecondes |
| Perte de paquets en rafale | < 1 % au cours de l’intervalle de 200 millisecondes |
| Perte de paquets | < 0,1 % pendant les 15 secondes |
| Gigue arrivée entre des batteries de paquets | < 15 millisecondes pendant les 15 secondes |
| Réorganisation des paquets | < 0,01 % en dehors des paquets de commande |


## <a name="recommended-dscp-markings"></a>Marquages DSCP recommandés

Lorsque vous êtes prêt à configurer la qualité de service, la première étape consiste à classer les flux de trafic (tels que les paramètres audio / vidéo) en assignant des valeurs DSCP pour les plages de ports unique, sans chevauchement. La valeur DSCP affectée ici détermine la priorité du trafic via le réseau, en fonction de la configuration réseau. Chaque charge de travail obtient sa propre valeur DSCP, mais pas nécessairement une valeur unique, vous souhaiterez peut-être définir la même valeur pour les charges de travail voix et vidéo, en leur donnant le même niveau de priorité dans le réseau.  

La valeur DSCP à utiliser dépend de la manière dont vous souhaitez définir la priorité la charge de travail. Par exemple, les impératifs peuvent nécessiter que vous donnez application partage la même priorité que la vidéo (et par conséquent marquez-le avec la même valeur DSCP en tant que vidéo). Autres environnements peuvent avoir une stratégie de QoS existante en place, qui vous aideront à déterminer la priorité des charges de réseau. 

Le tableau 3 montre les marquages DSCP requis pour les équipes et ExpressRoute. Ces marquages peuvent être un bon point de départ pour les clients qui ne savez pas comment utiliser dans leurs propres environnements. Pour des informations complémentaire, consultez les [Exigences de qualité de service d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Le tableau 3. Marquage DSCP_

| Plage de ports client source |Protocole|Catégorie de médias|Valeur DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50,019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50,020 – 50,039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50,040 – 50,059|TCP/UDP|Application/partage du bureau|18|Assured Forwarding (AF21)|

Connaître les éléments suivants lorsque vous utilisez les informations dans le tableau 3 :

-  Si vous envisagez d’implémenter ExpressRoute dans le futur et n’ont pas encore implémenté QoS, nous conseillons de suivre les conseils dans le tableau 3 afin que les valeurs DSCP sont les mêmes à partir de l’expéditeur au récepteur. 

-  Tous les clients, y compris les clients mobiles et les périphériques d’équipes, utiliseront ces plages de ports et seront affectés par une stratégie DSCP que vous implémentez qui utilise ces plages de ports source. Seuls les clients qui continueront à utiliser des ports dynamiques sont les clients basés sur navigateur (autrement dit, les clients qui permettent aux participants de participer à des réunions à l’aide de leurs navigateurs).

-  Bien que le client Mac utilise les mêmes plages de ports, il utilise également des valeurs codées en dur pour (EF) les paramètres audio / vidéo (AF41). Ces valeurs ne sont pas configurables.


## <a name="source-ports-used-by-teams"></a>Ports sources utilisés par Teams

Dans Teams, la qualité de service doit être configurée selon les ports sources utilisés par les différentes charges de travail. Actuellement, aucun des deux plages de ports côté serveur et côté client peuvent être configurés. 

Les plages de ports source client répertoriées dans le tableau 3 également appliquent aux équipes et utilisent leur marquage QoS DSCP associée.

La méthode d’implémentation de ces stratégies QoS recommandée consiste à utiliser les ports source client avec une adresse IP source et de destination de « indifférent ». Ceci permet de détecter les deux le trafic multimédia entrant et sortant sur le réseau interne. 

> [!NOTE]
> Si vous avez déjà configuré QoS basée sur les plages de ports source pour Skype for Business en ligne, la même configuration s’appliquera aux équipes et aucune modification supplémentaire ne sera requise. Si vous avez déployé Skype pour Business Server locale, vous devez vos stratégies QoS, et modifiez-les si nécessaire.

## <a name="set-dscp-markings"></a>Définir le marquage DSCP

Il existe plusieurs approches pour définir les marques DSCP appropriées pour la classification de trafic :

-  **Le marquage DSCP au point de terminaison :** C’est généralement l’option recommandée, car le point de terminaison fournit les inscriptions appropriées. Actuellement cela à l’aide d’un objet de stratégie de groupe, mais il peut uniquement être utilisé sur les clients à un domaine Windows. Les clients mobiles ne fournissent un mécanisme pour marquer le trafic à l’aide de valeurs DSCP. Bien que vous ne pouvez pas configurer non&ndash;à un domaine clients au trafic balise, clients tels que Mac OS les balises codé en dur et Windows sera balise toujours le trafic comme indiqué ci-dessus.

-  **DSCP basée sur le port de liaison à l’aide de listes de contrôle d’accès (ACL) sur les routeurs :** Il s’agit d’une option très courante rencontrée dans les environnements hétérogènes Windows et Mac. Dans ce scénario, l’équipe réseau marque le trafic sur les routeurs d’entrée/sortie (généralement situé sur le réseau étendu) basé sur les plages de ports source définies pour chaque modalité. Bien que cela fonctionne sur plusieurs plates-formes, il marque uniquement le trafic sur le bord WAN — pas tout à fait à l’ordinateur client et par conséquent entraîne une surcharge de gestion.

-  **Une combinaison de marquage DSCP au point de terminaison et ACL basées sur des ports sur les routeurs :** Nous vous recommandons de cette combinaison, si possible dans votre environnement. Utilisez un objet de stratégie de groupe pour intercepter la plupart des clients et également utiliser DSCP basée sur le port de marquage pour vous assurer que mobile, Mac et les autres clients seront toujours traitement QoS (au moins partiellement).

Vous pouvez utiliser QoS basée sur les stratégies au sein de la stratégie de groupe pour définir la valeur DSCP pour la plage de ports source prédéfinis dans le client d’équipes. Pour créer une stratégie pour chaque charge de travail, utilisez les plages de ports spécifiés dans le tableau 3.

Une fois que vous avez identifié les plages de ports, l’étape suivante consiste à configurer les paramètres QoS basée sur la stratégie dans un objet de stratégie de groupe. Vous trouverez plus d’informations sur ces étapes de [Configuration des plages de ports et une stratégie de qualité de Service pour vos clients sur Skype pour Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).

Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 10, ouvrez une session un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez Gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur gestion des stratégies de groupe), puis suivez les étapes suivantes :

1. Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **Clients**, la nouvelle stratégie doit être créée en l’unité d’organisation du Client.

2. Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.

3. Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4. Avec le bouton droit de la stratégie nouvellement créée, puis cliquez sur **Modifier**.

5. Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6. Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**. Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.

7. Dans la page suivante, sélectionnez **uniquement les applications portant ce nom exécutable** et entrez le nom **Teams.exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie pour définir la priorité uniquement le trafic correspondant à partir du client équipes.

8. Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**. Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.

9. Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisées.

10. Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservé ports 50000 par le biais de ports 50019 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **50000:50019**. Cliquez sur **Terminer**.

11. Répétez les étapes 5 à 10 pour créer des stratégies pour la vidéo et l’Application/partage du bureau, en remplaçant les valeurs appropriées dans les étapes 6 et 10.

Les nouvelles stratégies que vous avez créé ne prennent effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate.

### <a name="force-group-policy-refresh"></a>Actualisation de la stratégie de groupe

1. Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez
   ```
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier le marquage DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.

1. Ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez 
   ```
   gpresult /R > gp.txt
   ```

   Cela générer un rapport et envoyez-le à un fichier texte nommé gp.txt. Vous pouvez également entrer la commande suivante pour produire les mêmes données dans un rapport HTML plus lisible nommé gp.html :
   ```
   gpresult /H >gp.html
   ```
 ![Capture d’écran de la fenêtre de console exécutant la commande gpresult.] (media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande gpresult.")

3. Dans le fichier généré, recherchez l’en-tête **Appliqué des objets de stratégie de groupe** et vérifiez que les noms des objets de stratégie de groupe créés précédemment sont dans la liste des stratégies appliquées. 

4. Ouvrez l’Éditeur du Registre et accédez à :

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Vérifiez les valeurs pour les entrées de Registre répertoriées dans le tableau 4.

   _Le tableau 4. Valeurs des entrées du Registre Windows pour QoS_


   |          Nom          |  Type  |    Données     |
   |------------------------|--------|-------------|
   |    Nom de l’application    | REG_SZ |  Teams.exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        Adresse IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe de l’adresse IP locale | REG_SZ |     \*      |
   |       Port local       | REG_SZ | 50000-50019 |
   |        Protocole        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe de l’adresse IP distante    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Taux d’accélération      | REG_SZ |     -1      |


5. Vérifiez que la valeur de l’entrée de nom de l’Application est correcte pour le client que vous utilisez, puis vérifiez que la valeur DSCP et le Port Local entrées reflètent les paramètres de l’objet de stratégie de groupe.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Valider la qualité de service en analysant les équipes le trafic sur le réseau

Pour l’ensemble de valeurs QoS pour être efficaces, DSCP par l’objet de stratégie de groupe doit être présent aux deux extrémités d’un appel. En regardant le trafic généré par le client d’équipes, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de la charge de travail des équipes parcourt les déplacements via le réseau.

De préférence, vous capturez le trafic réseau à la sortie. Vous pouvez utiliser la mise en miroir de port sur un commutateur ou un routeur pour cela.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilisez le Moniteur réseau pour vérifier les valeurs DSCP

Le Moniteur réseau est un outil que vous pouvez [télécharger à partir de Microsoft](https://www.microsoft.com/download/4865) pour analyser le trafic réseau.

1. Sur l’ordinateur exécutant le Moniteur réseau, connectez-vous au port qui a été configuré pour capturer les paquets de début et de la mise en miroir de port. 

2. Émettre un appel à l’aide du client équipes. Assurez-vous que le support a été établie avant de raccrocher l’appel. 

3. Arrêtez la capture.

4. Dans le champ de **Filtre d’affichage** , utilisez l’adresse IP source de l’ordinateur qui effectue l’appel et affiner le filtre en définissant la valeur DSCP 46 (hex d’arrêt 0xb8) comme critères de recherche, comme illustré dans l’exemple suivant :

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.] (media/Qos-in-Teams-Image4.png "Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.")

5. Sélectionnez **Appliquer** pour activer le filtre.

6. Dans la fenêtre de **Cadre résumé** , sélectionnez le premier paquet UDP.

7. Dans la fenêtre **Détails de la trame** , développez l’élément de liste IPv4 et notez la valeur à la fin de la ligne qui commence par **le marquage DSCP**. 

    ![Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.] (media/Qos-in-Teams-Image5.png "Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.")

Dans cet exemple, la valeur DSCP est définie à 46. Cela est correct, car le port source utilisé est 50019, qui indique qu’il s’agit d’une charge de travail voix. 

Répétez cette vérification pour chaque charge de travail qui a été marquée par l’objet de stratégie de groupe. 

## <a name="more-information"></a>Plus d’informations

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Exigences ExpressRout QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
