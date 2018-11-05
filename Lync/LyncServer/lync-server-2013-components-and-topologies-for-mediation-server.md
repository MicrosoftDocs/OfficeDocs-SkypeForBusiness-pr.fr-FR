---
title: "Lync Server 2013 : Comp. et topologies utilisés pour le serveur de médiation"
TOCTitle: Composants et topologies utilisés pour le serveur de médiation
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398537(v=OCS.15)
ms:contentKeyID: 49297667
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Cette rubrique décrit les composants dont dépend le serveur de médiation et les topologies dans lesquelles le serveur de médiation peut être déployé.

## Dépendances

Le serveur de médiation comporte les dépendances suivantes :

  - **Registre.** Obligatoire. Le Registre est le tronçon suivant de signalisation des interactions du serveur de médiation avec le réseau Lync Server 2013. Notez qu’il est possible de colocaliser le serveur de médiation sur serveur frontal avec le Registre, en plus d’être installé en tant que pool autonome constitué uniquement de serveurs de médiation. Le Registre est colocalisé avec un serveur de médiation et une passerelle RTC sur un Survivable Branch Appliance.

  - **Serveur de surveillance.** Facultatif mais fortement recommandé. Le serveur de surveillance permet au serveur de médiation d’enregistrer les mesures de qualité associées à ses sessions multimédias.

  - **Serveur Edge.** Obligatoire pour la prise en charge des utilisateurs externes. Le serveur Edge permet au serveur de médiation d’interagir avec les utilisateurs situés derrière une conversion d’adresses réseau (NAT) ou un pare-feu.

## Topologies

Le serveur de médiationLync Server 2013 est colocalisé par défaut avec une instance du Registre sur un serveur Standard Edition, un pool de serveurs frontaux ou un Survivable Branch Appliance. Tous les serveurs de médiation dans un pool de serveurs frontaux doivent être configurés à l’identique.

Là où les performances posent problème, il est préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié. Ou, si vous déployez la jonction SIP, nous vous conseillons de déployer un pool de serveurs de médiation autonome.

Si vous déployez des connexions SIP directes sur une passerelle RTC qualifiée prenant en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS, un pool de serveurs de médiation n’est pas nécessaire puisque les passerelles qualifiées sont capables d’équilibrer la charge DNS sur un pool de serveurs de médiation et d’accepter du trafic en provenance de n’importe quel serveur de médiation au sein d’un pool.

Nous vous recommandons également de colocaliser le serveur de médiation sur un pool de serveurs frontaux après avoir déployé des systèmes IP-PBX ou vous être connecté au contrôleur SBC d’un fournisseur de serveur de téléphonie Internet si l’une des conditions suivantes est remplie :

  - Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

  - Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia mais le pool de serveurs frontaux chargé d’héberger le serveur de médiation peut gérer le transcodage vocal des appels non concernés par la déviation du trafic multimédia.

L’outil de planification Microsoft Lync Server 2013 peut servir à évaluer si le pool de serveurs frontaux sur lequel s‘effectuera la colocalisation du serveur de médiation peut gérer la charge. Si votre environnement ne satisfait pas les conditions requises, vous devez déployer un pool de serveurs de médiation autonome.

Pour plus d’informations sur la topologie à déployer, reportez-vous à [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison de réseau étendu. Le serveur de médiation est colocalisé avec le Registre sur un pool de serveurs frontaux sur Site 1. Les serveurs de médiation sur Site 1 contrôlent à la fois la passerelle RTC sur Site 1 et la passerelle sur Site 2. Dans cette topologie, la déviation du trafic multimédia est activée globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle RTC (GW1 et GW2).

**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation sur Site 1 et une passerelle RTC sur Site 2**

![Topologie vocale avec passerelle WAN de serveur de médiation](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologie vocale avec passerelle WAN de serveur de médiation")

La figure suivante montre une topologie simple où le serveur de médiation est colocalisé avec le Registre sur le pool de serveurs frontaux sur Site 1 et dispose d’une connexion SIP directe vers l’IP-PBX sur Site 1. Dans cette figure, le serveur de médiation contrôle également une passerelle RTC sur Site 2. Supposez qu’il existe des utilisateurs Lync sur les Sites 1 et 2. Supposez également que l’IP-PBX dispose d’un processeur multimédia associé par lequel transitent tous les médias en provenance des points de terminaison Lync avant d’être envoyés sur les extrémités de média contrôlés par l’IP-PBX. Dans cette topologie, la déviation du trafic multimédia est activée globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et RTC.

**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation sur Site 1 et un PBX sur Site 2**

![Topologie vocale - PBX WAN de serveur de médiation](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topologie vocale - PBX WAN de serveur de médiation")

Pour plus d’informations sur la planification des topologies PBX, reportez-vous à [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) et [Options de déploiement SIP direct dans Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

La dernière figure de cette rubrique montre une topologie où le serveur de médiation est connecté au contrôleur SBC d’un fournisseur de services de téléphonie Internet. Pour plus d’informations sur les topologies de jonction SIP, reportez-vous à [Jonction SIP dans Lync Server 2013](lync-server-2013-sip-trunking.md).

