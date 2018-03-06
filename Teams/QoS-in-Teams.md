---
title: "Qualité de service (QoS) dans Microsoft Teams"
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "Préparez le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a>Qualité de service (QoS) dans Microsoft Teams
==========================================
Ce guide vous aidera à préparer le réseau de votre organisation à la qualité de service (QoS) dans Teams.


La qualité de service (QoS) est un mécanisme permettant de classer par ordre de priorité certains types de trafic réseau. Classer le trafic par ordre de priorité pour les communications en temps réel telles que Teams est important pour offrir une expérience utilisateur de niveau professionnel. Pour que la qualité de service soit réellement performante, une connexion pouvant la prendre en charge doit être configurée de bout en bout (PC, commutateurs réseau et routeurs vers le cloud) car si une partie dans le chemin réseau ne peut pas la prendre en charge, la qualité de l'intégralité de l’appel peut être dégradée.


![Capture d’écran d’un diagramme illustrant la relation entre les réseaux d'une organisation et les services Office 365.](media/Qos-in-Teams-Image1.png)

 

Dans la plupart des cas, le réseau d'interconnexion sera un réseau non géré, une connexion Internet. Une option disponible pour corriger la qualité de service de bout en bout est [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nous recommandons d’implémenter la qualité de service sur les parties du réseau que vous contrôlez, c’est-à-dire votre réseau sur site. La qualité des charges de travail de communication en temps réel sera ainsi améliorée dans votre déploiement, et les goulots d’étranglement dans votre déploiement existant seront réduits. 

## <a name="objectives"></a>Objectifs 

Ce guide sera axé sur la procédure de hiérarchisation du trafic des communications en temps réel, c’est-à-dire les communications vocales et vidéo. Les autres types de trafic peuvent également être hiérarchisés en fonction de vos besoins.

Il existe plusieurs façons de classer le trafic par ordre de priorité, mais la plus courante consiste à utiliser des marquages DSCP (Differentiated Services Code Point). Ils peuvent être appliqués en fonction des plages de ports mais également par le biais d’objets de stratégie de groupe. Nous aborderons les deux dans ce document.

Contrôler le marquage DSCP via des objets de stratégie de groupe (GPO) permet de s’assurer que les ordinateurs avec jonction à un domaine reçoivent les paramètres corrects, et que ces paramètres ne peuvent être gérés que par un administrateur. 

Il est important de comprendre que la qualité de service ne fonctionne que lorsqu’elle est implémentée sur toutes les liaisons connectant l’appelant à l’appelé. Si nous l’utilisons sur le réseau interne et qu'un utilisateur se connecte depuis un emplacement distant, nous ne pouvons la hiérarchiser qu’au sein de notre réseau interne et géré. Tandis que les emplacements distants peuvent recevoir une connexion gérée en implémentant un réseau privé virtuel, il est déconseillé d’exécuter le trafic des communications en temps réel sur le VPN.

> [!NOTE]
> Afin d’améliorer l’expérience utilisateur, nous recommandons d’implémenter une tunnellisation fractionnée pour les utilisateurs distants connectés au VPN. Reportez-vous au document [Déployer-Guide-Tunnel fractionné VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) pour plus d’informations.

Dans une organisation mondiale avec des liaisons gérées réparties sur plusieurs continents, la qualité de service est fortement recommandée car la bande passante est limitée par rapport au réseau local.

## <a name="quality-of-service"></a>Qualité de service

Pour fournir un niveau de service garanti pour une application sur le réseau, les périphériques réseau sous-jacents doivent disposer d’un moyen de classifier les différents types de trafic. Un routeur, par exemple, doit pouvoir distinguer le trafic vocal du trafic de navigation sur le Web normal, s’il est attendu que le trafic vocal bénéficie d’un meilleur traitement. 

Les services différenciés (DiffServ) fournissent une infrastructure dans laquelle le trafic est traité par périphériques réseau, avec des priorités basées sur le champ ToS (type de services) dans l’en-tête d’un paquet IPv4/IPv6. Les octets les plus significatifs du champ DiffServ sont appelés DSCP (Differentiated Services Code Point). En utilisant cette infrastructure, le trafic peut être classifié en tant que type de trafic spécifique (vocal) puis marqué (101110 ou 46 en valeur décimale), de telle sorte que lorsque les périphériques réseau traitent ces marquages, le trafic puisse être classé par ordre de priorité en conséquence (acheminement accéléré dans cet exemple).

Lorsque le trafic réseau entre dans un routeur, il est placé dans une file d’attente. S’il n’y a pas de QoS en place, il n’existe essentiellement qu'une seule file d’attente et les données sont traitées sur la base du premier entré, premier sorti. Cela signifie que le trafic vocal (qui est très sensible aux délais) pourrait être bloqué derrière le trafic des services de diffusion en ligne. Lors de l’implémentation de la qualité de service, plusieurs files d’attente peuvent être définies, avec des fonctionnalités de gestion des surcharges différentes (telles que PQ, Priority Queuing de Cisco et CBWFQ, Class Based Weighted Fair Queue) et des fonctionnalités d'évitement de surcharge (comme WRED, Weighted Random Early Detection).

![Capture d’écran d’un diagramme illustrant les files d’attente QoS dans Teams.](media/Qos-in-Teams-Image2.png)

Figure 1 : files d’attente QoS visualisées

Une fois ces éléments en place, une qualité de service prévisible peut être fournie, le réseau géré sous-jacent comprenant maintenant comment classifier, marquer et classer par ordre de priorité le trafic. Du point de vue de Teams, l’élément de configuration le plus important est la classification et le marquage des paquets, mais une planification rigoureuse est nécessaire pour aligner la configuration de l’application sur celle du réseau sous-jacent afin que la qualité de service de bout en bout soit réussie.

## <a name="qos-scenarios"></a>Scénarios de qualité de service

Lors de l’implémentation de la qualité de service pour Teams, nous avons basé nos conseils sur quatre scénarios de départ :

1.  Vous avez déployé ou déployez Teams et vous prévoyez d’implémenter la qualité de service par le biais du marquage selon les ports. Le marquage selon les ports est la méthode la plus fiable, car elle fonctionne universellement sur toutes les plateformes et elle est la plus simple à implémenter. 

2.  Vous avez déployé ou déployez Teams et vous prévoyez d’implémenter la qualité de service par le biais du marquage des objets de stratégie de groupe. Cette méthode est parfois utilisée en conjonction avec le scénario 1. Tandis que ce scénario est entièrement valide et décrit ci-dessous, il est important de comprendre que cela fonctionnera uniquement pour les clients Windows avec jonction à un domaine. Le marquage QoS/DSCP ne sera appliqué sur aucun des périphériques qui ne sont pas un client Windows avec jonction à un domaine. 

3.  Vous avez déployé Skype Entreprise Online avec le marquage QoS et vous déployez maintenant Teams. Si tel est le cas, Teams respectera la configuration existante et utilisera les même plages de ports et marquage que le client Skype Entreprise. Aucune autre configuration ne devrait être nécessaire. 
    > [!NOTE]
    > Si vous utilisez le marquage QoS par nom d’application par le biais d’une stratégie de groupe, vous devez ajouter « Teams.exe » comme nom d’application.
4.  Vous avez déployé ou vous déployez Teams et souhaitez implémenter la qualité de service par le biais du marquage selon les ports avec une plage de ports personnalisée.

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a>Marquages DSCP (differentiated services code point) recommandés

La première étape consiste à classifier les flux de trafic (comme audio et vidéo) en utilisant les plages de ports uniques et qui ne se chevauchent pas avec une valeur DSCP. La valeur DSCP attribuée ici déterminera la priorité du trafic qui transite sur le réseau (selon la configuration du réseau). Chaque charge de travail obtient sa propre valeur DSCP, bien que certains clients puissent obtenir la même valeur sur le trafic vocal et vidéo, leur donnant la même priorité sur le réseau. 

La valeur DSCP à utiliser dépend de la priorité donnée à une charge de travail. Par exemple, les exigences de l’entreprise peuvent imposer que le partage d’application soit traité avec le même niveau de priorité que la vidéo (et soit donc marqué avec la même valeur DSCP que la vidéo). D’autres environnements peuvent avoir déjà une stratégie QoS en place. 

Le tableau 1 ci-dessous présente les marquages DSCP requis lorsque l’application Teams est utilisée avec ExpressRoute. Cela peut être un bon point de départ pour les clients qui ne savent pas quoi utiliser dans leur propre environnement. Pour des informations complémentaire, consultez les [Exigences de qualité de service d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


| Port source du client|Protocole|Catégorie de médias|Valeur DSCP courante|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50 019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50 020 – 50 039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50 040 – 50 059|TCP/UDP|Partage d’application/de bureau et transfert de fichiers|18|Sélecteur de classe (CS3)|

Tableau 1 : marquages DSCP

Voici quelques précisions à comprendre lorsque vous utilisez les informations du tableau 1 :

- Le partage de fichiers et le partage d’application utilisent la même plage de ports sources, et utiliseront donc les mêmes marquages DSCP lorsque le marquage selon les ports est utilisé. Pour cette raison, il est nécessaire de déterminer la priorité qui s’applique le plus aux *deux* modalités (interactive ou par défaut).
    
- S’il est prévu d’implémenter ExpressRoute à l’avenir et que la qualité de service n’a pas encore été implémentée, il est recommandé de suivre les conseils fournis ci-dessus afin que les valeurs DSCP soient les mêmes de l’expéditeur au destinataire. 
    
## <a name="source-ports-used-by-teams"></a>Ports sources utilisés par Teams

Dans Teams, la qualité de service doit être configurée selon les ports sources utilisés par les différentes charges de travail. Les plages de ports, aussi bien côté serveur que côté client, ne sont pas configurables à ce stade. 

Pour déployer la qualité de service, utilisez les plages de ports sources répertoriées dans le Tableau 2 avec leurs marquages DSCP QoS associés.

| Port source du client|Protocole|Catégorie de médias|Valeur DSCP courante|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50 019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50 020 – 50 039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50 040 – 50 059|TCP/UDP|Partage d’application/de bureau et transfert de fichiers|18|Sélecteur de classe (CS3)|

Tableau 2 : plages de ports sources du client

> [!NOTE]
> Si vous avez déjà configuré la qualité de service selon les plages de ports sources pour Skype Entreprise Online, la même configuration s’appliquera à Teams et aucune autre modification n’est nécessaire. Si vous avez déployé Skype Entreprise Server (sur site), vous devrez modifier vos stratégies QoS.

## <a name="setting-differentiated-services-code-point-dscp-markings"></a>Définition des marquages DSCP (differentiated services code point)

Il existe plusieurs approches pour définir les marquages DSCP pour la classification du trafic.

- Marquage DSCP au point de terminaison : il s’agit de l’option préférée en général, le point de terminaison lui-même fournissant les marquages corrects. Ce marquage peut être effectué actuellement en utilisant un objet de stratégie de groupe, mais il est possible uniquement sur des clients Windows avec jonction à un domaine. Les clients Mac OSX et mobiles, par exemple, ne fournissent pas de mécanisme pour marquer le trafic avec des valeurs DSCP.

- Selon les ports en utilisant des listes de contrôle d’accès sur les routeurs : il s’agit d’une option très courante dans les environnements hétérogènes Windows et Mac. Dans ce scénario, l’équipe en charge du réseau marque le trafic sur les routeurs d’entrée/sortie (généralement sur le réseau étendu, WAN) selon les plages de ports sources définies pour chaque modalité. Cette option fonctionne sur toutes les plateformes mais seul le bord WAN est marqué - pas jusqu’à l’ordinateur client - et elle implique des tâches de gestion.
    
- Une combinaison de marquages DSCP au niveau du client et des listes de contrôle d’accès basées sur les ports au niveau des routeurs.
    
Si cela est possible, nous recommandons une combinaison des deux : utiliser un objet de stratégie de groupe pour intercepter une majorité de clients, ainsi qu'un marquage DSCP selon les ports pour garantir que les clients mobiles, Mac et les autres clients continueront à bénéficier d'un traitement QoS (partiel).

La définition de la valeur DSCP pour la plage de ports sources prédéfinie peut être effectuée sur le client Teams en utilisant une qualité de service basée sur une stratégie au sein de la stratégie de groupe. Les tableaux suivants utilisent les plages de ports spécifiées dans le tableau pour créer une stratégie pour chaque charge de travail.

| Type de trafic du client|Début de la plage de ports|Fin de la plage de ports|Valeur DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vidéo|50020|50039|34|
| Partage d'application|50040|50059|18|
| Transfert de fichiers|50040|50059|18|

Tableau 3 : plages de ports par type de trafic

Remarque : les plages de ports définies par Teams ne peuvent pas être modifiées ni altérées. Pour les informations les plus récentes, consultez la page suivante : https://support.microsoft.com/ kb/2409256

Une fois les plages de ports déterminées, l’étape suivante consiste à configurer les paramètres QoS en fonction de la stratégie au sein d'un objet de stratégie de groupe (GPO). Vous trouverez des informations détaillées pour cette procédure sur [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Les nouvelles stratégies que vous avez créées ne seront appliquées que lorsque la stratégie de groupe aura été actualisée sur les ordinateurs clients. La stratégie de groupe s’actualise elle-même régulièrement, mais vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur sur lequel elle doit être actualisée :

        gpudate.exe /force

Cette commande peut être actualisée depuis n’importe quelle fenêtre de commande exécutée avec des informations d’identification d’administrateur. Pour exécuter une fenêtre de commande, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

## <a name="verifying-the-dscp-markings-in-gpo"></a>Vérification des marquages DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de la stratégie de groupe ont été définies, suivez la procédure suivante :

1.  Utilisez la commande gpresult pour vérifier que les paramètres de l’objet de stratégie de groupe ont été reçus par l’ordinateur local. La commande gpresult /R >gp.txt générera un rapport et l’enverra dans un fichier texte, gp.txt.

    ![Capture d’écran de l’invite de commande Administrateur exécutant la commande gpresult.](media/Qos-in-Teams-Image3.png)

    Figure 2 : objets de stratégie de groupe appliqués
    > [!NOTE]
    > Vous pouvez également exécuter la commande gpresult /H gp.html pour produire les mêmes données dans un rapport HTML plus convivial. 
2.  Dans le fichier généré, recherchez l’en-tête Applied Group Policy Objects et vérifiez que les noms des objets de stratégie de groupe créés précédemment se trouvent dans la liste des stratégies appliquées. 

3.  Ouvrez l’éditeur du Registre est accédez à

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Vérifiez les valeurs du registre répertoriées dans le tableau 3.
    
    | Nom | Type | Données|
    |---------|---------|---------
    | Nom de l’application|REG_SZ|Teams.exe|
    | Valeur DSCP|REG_SZ|46|
    | Adresse IP locale|REG_SZ|*|
    | Longueur du préfixe de l’adresse IP locale|REG_SZ|*|
    | Port local|REG_SZ|50000-50019|
    | Protocole|REG_SZ|*|
    | Adresse IP distante|REG_SZ|*|
    | Préfixe de l’adresse IP distante|REG_SZ|*|
    | Port distant|REG_SZ|*|
    | Taux d’accélération|REG_SZ|-1|
    
    Tableau 3 : valeurs du registre Windows pour la qualité de service

4.  Vérifiez que le nom de l’application est correct pour le client que vous utilisez, et que la valeur DSCP et le port local renvoient les paramètres dans l’objet de stratégie de groupe.

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a>Validation de la qualité de service : analyse du trafic Teams sur le réseau

Pour que la qualité de service soit appliquée, la valeur DSCP définie par l’objet de stratégie de groupe doit être présente de l’appelant à l’appelé. En regardant le trafic généré par le client Teams, nous pouvons vérifier que la valeur DSCP n'est pas modifiée ni supprimée lors du parcours du réseau. 

De préférence, nous capturerions le trafic au point de sortie du réseau. La mise en miroir des ports peut être utilisée sur un commutateur ou routeur pour aider à la capture du trafic sur le réseau. 

### <a name="looking-at-network-traffic-using-network-monitor"></a>Vérification du trafic réseau à l’aide du Moniteur réseau

Le Moniteur réseau est un outil que vous pouvez télécharger sur le site Microsoft pour analyser le trafic réseau. Téléchargez [Moniteur réseau 3.4](https://www.microsoft.com/download/4865).

Connectez l’ordinateur qui exécute le moniteur réseau au port qui a été configuré pour la mise en miroir des ports, et commencez à capturer les paquets. Passez un appel à l’aide du client Skype Entreprise. Assurez-vous que la connexion multimédia est établie avant de raccrocher. Arrêtez la capture pour créer un filtre d’affichage qui correspond à l’adresse IP source de l’ordinateur qui a passé l’appel, et affinez le filtre en définissant la valeur DSCP 46 (0xb8 en valeur hexadécimale) comme critère de recherche :

Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

![Capture d’écran de la boîte de dialogue du filtre d’affichage dans Moniteur réseau, présentant les filtres à appliquer.](media/Qos-in-Teams-Image4.png)


Cliquez sur **Appliquer** pour activer le filtre. Dans la fenêtre **Résumé de la trame**, sélectionnez le premier paquet UDP et vérifiez les détails de la trame :

![Capture d’écran de la boîte de dialogue des détails de la trame dans Moniteur réseau, mettant en relief les paramètres DSCP.](media/Qos-in-Teams-Image5.png)

Développez IPv4 et vérifiez la valeur à la fin de la ligne DSCP. Dans cet exemple, nous voyons que la valeur DSCP est définie sur 46, ce qui est correct car le port source utilisé est 50019, ce qui nous indique que la charge de travail est la voix. 

Répétez cette vérification pour chaque charge de travail qui a été marquée par l’objet de stratégie de groupe. 

> [!NOTE]
> Vérifiez que les marquages sont respectés également pour le trafic réseau pair à pair. Pour ce faire, vous pouvez installer Moniteur réseau sur deux clients et passer des appels entre eux. Vérifiez le trafic multimédia passant entre les clients de la même manière que ci-dessus.

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a>Modèles de filtres à utiliser pour Moniteur réseau ou Wireshark

|Utilisation  |Modèle de filtre  |
|---------|---------|
|Voix (remarque : le multiplexage doit être désactivé)     |   udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46      |
|Vidéo     | udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34        |
|Partage d’écran     |  udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a>Filtre : trafic multimédia depuis les relais Microsoft (nécessite [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/))

ip.src in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.srcport in {3479 3480 3481} or (udp.srcport ge 50000 and udp.srcport lt 60000))

### <a name="filter-media-traffic-to-microsoft-relays"></a>Filtre : trafic multimédia depuis les relais Microsoft

ip.dst in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.dstport in {3479 3480 3481} or (udp.dstport ge 50000 and udp.dstport lt 60000))


Vous devez voir le trafic depuis et vers les relais Microsoft. Vous pouvez vérifier les marquages DSCP sur la couche IP dans Wireshark, comme indiqué dans la section suivante.

### <a name="expected-dscp-markings"></a>Marquages DSCP attendus

Flux audio : 46

Flux vidéo : 34

Flux de données : 18

### <a name="filter-dscp-condition-to-network"></a>Filtre : condition DSCP vers le réseau

ip.dsfield.dscp in {46 34 18}



### <a name="looking-at-network-traffic-using-wireshark"></a>Vérification du trafic réseau à l’aide de Wireshark

Wireshark (https://www.wireshark.org/), est un outil puissant permettant de filtrer et d’enregistrer les données du réseau pour une analyse plus approfondie. Connectez un ordinateur qui exécute Wireshark au port qui a été configuré pour la mise en miroir des ports, et commencez à capturer les paquets. Passez un appel à l’aide du client Teams. Assurez-vous que la connexion multimédia est établie avant de raccrocher.

Arrêtez le traçage des paquets et créez un filtre qui affiche uniquement l’adresse IP source de l’ordinateur sur lequel le client Teams est installé, par exemple *ip.src_host == 192.168.137.201*, et vérifiez les paquets qui utilisent un port source de la plage spécifiée pour la voix, 50 000 – 50 019 :

![Capture d’écran de Wireshark avec les paramètres de filtre.](media/Qos-in-Teams-Image6.png)
 

Marquez le package et développez l’en-tête de la version du protocole Internet 4 (IPV4) dans le volet des détails du paquet :

![Capture d’écran de Wireshark avec les paramètres Differentiated Services Codepoint mis en relief.](media/Qos-in-Teams-Image7.png)
 

Vérifiez que la valeur pour *Differentiated Services Codepoint* correspond à celle de la charge de travail spécifique, dans ce cas 46 (101110 en binaire) pour la voix.

Répétez cette vérification pour chaque charge de travail qui a été marquée par l’objet de stratégie de groupe.

> [!NOTE]
> Vérifiez que les marquages sont respectés pour le trafic réseau pair à pair. Pour ce faire, vous pouvez installer WireShark ou Moniteur réseau sur deux clients et passer des appels entre eux. Vérifiez le trafic multimédia passant entre les clients de la même manière que ci-dessus.

## <a name="summary"></a>Résumé

La qualité de service est un élément essentiel important pour fournir des expériences de niveau professionnel avec Teams. Cependant, il est important de ne jamais oublier qu’elle n’est efficace que sur des réseaux gérés correctement. À cet effet, l’équipe en charge du déploiement doit travailler en étroite collaboration avec l’équipe chargée de la mise en réseau pour garantir que les informations correctes sont transmises à la couche réseau, gérée dans l’idéal de bout en bout.

