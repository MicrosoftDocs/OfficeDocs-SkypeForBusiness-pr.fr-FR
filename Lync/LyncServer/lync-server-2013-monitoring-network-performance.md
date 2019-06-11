---
title: 'Skype Entreprise Server 2015 : surveillance des performances du réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Surveillance des performances du réseau dans Skype Entreprise Server 2015

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-04-27_

Lync Server 2013 est une technologie de communication en temps réel dont le contenu repose essentiellement sur le réseau pour permettre la communication entre les utilisateurs (messagerie instantanée, messagerie instantanée, appels vocaux ou communication vidéo). Il est par conséquent important de surveiller les performances du réseau en continu pour garantir la meilleure utilisation possible de la modalité de communication choisie par un utilisateur.

Les performances du réseau peuvent être mesurées à deux niveaux:

  - **Performances globales du réseau**   ce niveau de mesure des performances permet à une organisation de créer une vue de «grande image» de son réseau et est généralement implémentée par le biais de systèmes de surveillance réseau tiers. Ces systèmes recevront des données de performances et de capacité provenant de périphériques réseau distants tels que des routeurs et commutés sur le réseau pour permettre aux administrateurs de déterminer l’état d’un composant réseau donné à tout moment.

  - **Performances individuelles du serveur**   ce niveau de mesure de performance est limité à un serveur spécifique et permettra aux administrateurs d’identifier les performances du réseau d’un serveur spécifique pour vous aider à résoudre les problèmes liés aux performances spécifiques. problème ou pour évaluer les performances respectives du serveur sur une période donnée dans le cadre d’un processus de planification de capacité.

Vous pouvez surveiller le réseau en utilisant les outils décrits dans les sections suivantes.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Outils d’analyse des performances globales du réseau

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager fournit une gestion des services de bout en bout, facile à personnaliser et à prolonger pour améliorer les niveaux de service au sein d’un environnement informatique. Cela permet aux opérations et aux équipes de gestion informatiques d’identifier les problèmes et de résoudre les problèmes affectant l’état des services informatiques distribués. La gestion de service de bout en bout n’est pas limitée aux environnements Microsoft. La prise en charge des services Web pour la gestion (WS-Management), le protocole SNMP (simple Network Management Protocol) et les solutions de partenariat permettent aux systèmes qui n’exécutent pas les systèmes d’exploitation Microsoft et le matériel d’être inclus dans la surveillance du service dans System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>Les solutions de gestion de réseau de System Center Operations Manager 2012 et tierces

****   Les solutions EMC Smarts pour Operations Manager vous aident à résoudre les problèmes liés aux niveaux de service. À l’aide d’EMC Solutions for Operations Manager, vous pouvez gérer et surveiller votre chaîne de services informatiques en une solution intégrée et automatisée. Vous identifierez facilement les causes racines des problèmes de performances et de disponibilité, et vous pouvez les résoudre plus rapidement pour réduire les effets et les coûts. Les principaux avantages sont les suivants:

  - Une gestion avancée et facile à utiliser, qui vous permet de fournir une valeur stratégique commerciale au lieu de trier et de filtrer manuellement des alertes confuses.

  - **Résolution plus rapide**   : résolvez les problèmes informatiques et répondez aux besoins de votre entreprise plus rapidement et réduisez les coûts et l’impact.

  - **Les opérations**   rationalisées évite qu’elles soient plus complexes en combinant plusieurs outils de gestion, applications et terminaux.

Pour plus d’informations, consultez la page suivante:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Solutions pour Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Solutions tierces

**Centre de gestion réseau HP (auparavant appelé HP OpenView)** Le    [Centre de gestion réseau HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) fournit une gestion intégrée des pannes et des performances permettant d’améliorer la disponibilité et les performances du réseau. Le centre de gestion réseau fait partie de la solution de gestion de réseau automatisé HP qui unifie la gestion des erreurs, des performances, de la configuration et de la gestion des modifications.

**Produits de gestion et d’automatisation du réseau Cisco**   pour l’entreprise, Cisco dispose de plusieurs produits de gestion, notamment la solution de gestion LAN CiscoWorks et le module Cisco Network Analysis pour améliorer l’efficacité opérationnelle et réduction du temps d’arrêt du réseau. Pour obtenir des données supplémentaires sur ces produits, consultez le site Web [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)Cisco à l’adresse.

SNMP (simple Network Management Protocol) est une norme de gestion de réseau qui définit une stratégie de gestion des réseaux TCP/IP. SNMP vous permet de capturer les informations de configuration et d’État relatives au réseau, et d’envoyer les informations à un ordinateur désigné pour le suivi des événements. Ce protocole de gestion de réseau standard utilise une architecture distribuée qui inclut les éléments suivants:

  - Plusieurs nœuds gérés, chacun avec une entité SNMP appelé agent assurant l’accès à distance à l’instrumentation de gestion.

  - Au moins une entité SNMP désignée sous le nom de responsable qui exécute des applications de gestion pour surveiller et contrôler les éléments gérés. Les éléments managés sont des appareils tels que des hôtes, des routeurs, etc. Ils sont surveillés et contrôlés en accédant à leurs informations de gestion.

  - Le protocole de gestion SNMP est utilisé pour communiquer des informations de gestion entre les stations de gestion et les agents. Les informations de gestion font référence à une collection d’objets gérés qui résident dans un magasin d’informations virtuel appelé base de données de gestion (MIB).

<div>


> [!NOTE]  
> Vous trouverez ci-dessous des exemples de solutions de contrôle de réseau tierces. Cette liste n’est pas définitive et Microsoft ne favorise pas une solution de fournisseur spécifique. Contactez un fournisseur de services réseau et votre fournisseur de technologie pour déterminer la meilleure solution de surveillance réseau pour votre organisation.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Outils d’analyse des performances du réseau d’un serveur individuel

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 permettra aux administrateurs d’afficher les performances réseau de chaque serveur via le pack d’administration Windows Server 2012: le Pack de gestion du système d’exploitation Windows Server inclut un pack d’administration des performances Cela permettra aux administrateurs de surveiller les performances et l’intégrité des cartes réseau.

</div>

<div>

## <a name="windows-network-monitor"></a>Moniteur réseau Windows

Recueille, affiche, analyse l’utilisation des ressources sur un serveur et mesure le trafic réseau. Le moniteur réseau vérifie uniquement l’activité du réseau. En capturant et en analysant les données du réseau et en utilisant ces données avec les journaux de performance, vous pouvez déterminer l’utilisation du réseau, identifier les problèmes du réseau et prévoir les besoins futurs du réseau.

Pour plus d’informations sur le moniteur réseau 3,4 et sur l’installation et la configuration de l’analyse réseau et la capture et l’analyse des données, reportez-vous à la section vue d’ensemble du moniteur réseau 3,3. Consultez également le [blog Moniteur réseau](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

