---
title: 'Lync Server 2013 : Configuration de la déviation du trafic multimédia'
TOCTitle: Configuration de la déviation du trafic multimédia
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413028(v=OCS.15)
ms:contentKeyID: 49299337
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section suppose que vous ayez déjà publié et configuré au moins un ou plusieurs serveurs de médiation (tel que décrit dans [Définition d’un serveur de médiation dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) et [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), ou dans [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) et [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivement, dans la documentation de déploiement).

Cette section suppose également que vous définissez au moins un pair de passerelle pour garantir la connectivité RTC, comme indiqué dans [Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si le pair auquel vous vous connectez est le contrôleur de session en périphérie (SBC) d’un fournisseur de jonctions SIP, assurez-vous qu’il s’agit d’un fournisseur qualifié et qu’il prend en charge la déviation du trafic multimédia. Par exemple, de nombreux fournisseurs de jonctions SIP autoriseront uniquement leurs SBC à recevoir du trafic du serveur de médiation. Dans ce cas, le contournement doit être activé pour la jonction en question. De même, vous ne pouvez pas activer la déviation du trafic multimédia, à moins que l’organisation ne communique les adresses IP de son réseau interne au fournisseur de jonctions SIP.

> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions répertoriés dans « Infrastructure qualifiée pour Microsoft Lync » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</a>.

Cette rubrique explique comment activer la déviation du trafic multimédia pour réduire le traitement nécessaire du serveur de médiation. Avant d’activer ce contournement, vérifiez que votre environnement remplit les conditions requises pour le soutenir, comme indiqué dans la section [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) de la documentation de planification. Veillez également à utiliser les informations fournies dans [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) pour déterminer si les paramètres globaux de la déviation du trafic multimédia doivent toujours contourner le serveur de médiation ou utiliser les informations de site et de région pour savoir s’il faut le contourner.

Si vous avez déjà configuré le contrôle d’admission des appels (CAC), une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel la déviation du trafic multimédia est employée. La vérification de l’emploi du contournement de media est effectué en premier, et s’il est employé, le contrôle d’admission des appels n’est pas utilisé pour l’appel ; ce n’est qu’en cas d’échec de la déviation du trafic multimédia que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont par conséquent mutuellement exclusives pour tout appel particulier acheminé sur le RTC. Il s’agit du comportement logique car la déviation du trafic multimédia suppose que les restrictions de bande passante n’existent pas entre points de terminaison de média sur un appel ; la déviation du trafic multimédia est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel RTC : a) le média contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le media est traité par le serveur de médiation impliqué dans l’appel.

## Étapes suivantes : Activer la déviation du trafic multimédia sur la connexion des jonctions

Après avoir configuré les paramètres initiaux pour la connectivité RTC (plans de numérotation, stratégies de communications vocale, enregistrements d’utilisation RTC, itinéraires d’appels sortants et règles de conversion), commencez le processus d’activation de la déviation du trafic multimédia à l’aide de la procédure décrite dans [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

## Voir aussi

#### Tâches

[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurer le contournement de média dans Lync Server 2013 pour toujours contourner le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurer les paramètres globaux du contournement de média dans Lync Server 2013 pour utiliser les informations relatives aux sites et aux régions](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  

#### Concepts

[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Autres ressources

[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

