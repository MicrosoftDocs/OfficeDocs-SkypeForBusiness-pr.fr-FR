---
title: 'Lync Server 2013 : Vue d’ensemble du contrôle d’admission des appels'
TOCTitle: Vue d’ensemble du contrôle d’admission des appels
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398529(v=OCS.15)
ms:contentKeyID: 49297604
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Les communications en temps réel sont sensibles à la latence et à la perte de paquets susceptibles de survenir sur des réseaux saturés. Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies. La conception du contrôle d’admission des appels dans Lync Server 2013 offre quatre principaux avantages :

  - Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.

  - Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du point de terminaison et non pas de l’emplacement où est hébergé l’utilisateur.

  - Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.

  - Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau. Pour plus d’informations, reportez-vous aux exemples dans [Composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison de réseau étendu, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur RTC.

Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.

Les administrateurs définissent les stratégies de contrôle d’admission des appels, appliquées par le service de stratégie de bande passante installé avec chaque pool de serveurs frontaux. Les paramètres de contrôle d’admission des appels sont transmis automatiquement à tous les serveurs frontauxLync Server de votre réseau.

Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :

1.  Internet

2.  RTC

3.  Messagerie vocale

L’enregistrement des détails des appels capture les informations concernant les appels réacheminés vers RTC ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.

> [!NOTE]  
> Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.

Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison de réseau étendu. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.

## Considérations relatives au contrôle d’admission des appels

L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central. Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites. Le service de stratégie de bande passante s’exécute dans le cadre des serveurs frontaux, si bien qu’une haute disponibilité est prédéfinie au sein de ce pool. Le service de stratégie de bande passante qui s’exécute sur chaque serveur frontal se synchronise toutes les 15 secondes. Si le pool de serveurs frontaux est défaillant, les stratégies de contrôle d’admission des appels ne sont plus appliquées pour ce site tant que le pool de serveurs frontaux et en conséquence le service de stratégie de bande passante ne sont pas de nouveau opérationnels. Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante. Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.

Le service de stratégie de bande passante fournit la haute disponibilité au sein d’un pool de serveurs frontaux ; en revanche, il ne fournit pas de redondance entre les pools de serveurs frontaux. Il ne peut pas basculer d’un pool de serveurs frontaux vers un autre. Une fois que service est rétabli vers le pool de serveurs frontaux, le service de stratégie de bande passante reprend et peut de nouveau appliquer les vérifications de stratégie de bande passante.

## Considérations relatives au réseau

Même si la restriction de bande passante pour l’audio et la vidéo est appliquée par le service de stratégie de bande passante dans Lync Server 2013, cette restriction n’est pas appliquée sur le routeur réseau (couches 2 et 3). Le contrôle d’admission des appels Lync Server 2010 ne peut pas, par exemple, empêcher une application de données de consommer l’intégralité de la bande passante du réseau sur une liaison de réseau étendu, dont la bande passante réservée pour l’audio et la vidéo par votre stratégie de contrôle d’admission des appels. Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ). Par conséquent, la meilleure pratique consiste à coordonner les stratégies de bande passante du contrôle d’admission des données que vous définissez avec les paramètres QoS que vous pouvez déployer.

## Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)

Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.

## Contrôle d’admission des appels des utilisateurs extérieurs

Le contrôle d’admission des appels ne s’applique pas aux utilisateurs distants où le trafic réseau transite par Internet. Du fait que le trafic multimédia transite par Internet, qui n’est pas géré par Lync Server, le contrôle d’admission des appels ne peut pas être appliqué. Le contrôle d’admission des appels effectuera néanmoins des vérifications sur la portion d’appel qui transite par le réseau de l’entreprise.

## Contrôle d’admission des appels des connexions RTC

Le contrôle d’admission des appels est applicable sur le serveur de médiation, qu’il soit connecté à un système IP/PBX, à une passerelle RTC ou à une jonction SIP. Le serveur de médiation étant un agent utilisateur dos à dos (B2BUA), il ferme le média. Il comporte deux côtés de connexion : un côté connecté à Lync Server et un côté passerelle connecté aux passerelles RTC, IP/PBX ou jonctions SIP. Pour plus d’informations sur les connexions RTC, reportez-vous à [Planification de la connectivité RTC dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Le contrôle d’admission des appels peut être appliqué des deux côtés du serveur de médiation, à moins que la déviation du trafic multimédia soit activée. Si c’est le cas, le trafic multimédia ne transite pas par le serveur de médiation, mais passe plutôt directement entre le client Lync et la passerelle. Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire. Pour plus d’informations, reportez-vous à [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions RTC avec ou sans la déviation du trafic multimédia activée.

**Application du contrôle d’admission des appels sur des connexions RTC**

![Application de connexion de contournement de média CAC vocal](images/Gg398529.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de connexion de contournement de média CAC vocal")

## Compatibilité du contrôle d’admission des appels avec les versions précédentes d’Office Communications Server

Le contrôle d’admission des appels peut seulement être activé sur les points de terminaison activés pour Lync Server 2010 et versions ultérieures.

Le contrôle d’admission des appels ne peut pas être activé sur les points de terminaison qui exécutent Office Communicator 2007 R2 ou une version antérieure.

**Application du contrôle d’admission des appels sur des versions de Lync Server différentes**

![Diagramme de comparaison de version de CAC vocal](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramme de comparaison de version de CAC vocal")

