---
title: 'Lync Server 2013 : surveillance des performances du réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efeba476609ad293cd94e67f8dfdbe674b42f3f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500641"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a>Surveillance des performances réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-04-27_

Lync Server 2013 est une technologie de communication en temps réel qui repose largement sur le réseau pour permettre la communication entre les utilisateurs, via la messagerie instantanée, les appels vocaux ou la communication vidéo. Il est donc important de surveiller en permanence les performances du réseau afin de garantir que la modalité de communication choisie par un utilisateur offre la meilleure expérience possible.

Les performances du réseau peuvent être mesurées à deux niveaux :

  - Performances globales du **réseau**     Ce niveau de mesure des performances permettra à une organisation de créer une vue « grande image » de son réseau et est généralement implémentée par le biais de systèmes de surveillance réseau tiers. Ces systèmes recevront des données de performances et de capacité provenant d’appareils réseau distants tels que des routeurs et basculés sur le réseau pour permettre aux administrateurs de déterminer l’intégrité d’un composant réseau donné à tout moment de la journée.

  - Performances des serveurs **individuels**     Ce niveau de mesure des performances est limité à un serveur spécifique et aidera les administrateurs à évaluer les performances réseau d’un serveur spécifique en vue d’aider à résoudre un problème de performances spécifique ou à évaluer les performances du serveur respectif sur une période donnée dans le cadre d’un processus de planification de la capacité.

Vous pouvez surveiller le réseau à l’aide des outils décrits dans les sections suivantes.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Outils d’analyse des performances réseau globales

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager offre une gestion des services de bout en bout, facile à personnaliser et permettant d’étendre les niveaux de service améliorés au sein d’un environnement informatique. Cela permet aux équipes opérationnelles et de gestion informatique d’identifier et de résoudre les problèmes affectant l’intégrité des services informatiques distribués. La gestion des services de bout en bout n’est pas limitée aux environnements Microsoft. La prise en charge des services Web pour la gestion (WS-Management), du protocole SNMP (simple Network Management Protocol) et des solutions partenaires permettent aux systèmes qui n’exécutent pas les systèmes d’exploitation et le matériel Microsoft d’être inclus dans la surveillance des services dans System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 et solutions de gestion de réseau tierces

**EMC Smarts**     EMC Solutions for Operations Manager vous aide à résoudre rapidement les problèmes affectant les niveaux de service dans tout le. En utilisant les solutions EMC pour les opérations Manager, vous pouvez gérer et surveiller l’ensemble de votre chaîne de service informatique à l’aide d’une solution automatisée intégrée. Vous identifierez facilement les causes des problèmes de performances et de disponibilité, et vous les corrigerez plus rapidement, ce qui réduira les effets et les coûts. Les principaux avantages sont les suivants :

  - Une gestion avancée et facile à utiliser permet de fournir une valeur commerciale stratégique au lieu de trier et de filtrer manuellement les alertes.

  - **Résolution**     plus rapide Résoudre les problèmes informatiques et répondre aux besoins de l’entreprise plus rapidement, réduire l’impact et les coûts.

  - **Opérations**     rationalisées Évitez la complexité informatique en combinant plusieurs outils de gestion, applications et terminaux.

Des informations supplémentaires sont disponibles ici :

[Microsoft System Center Operations Manager](https://go.microsoft.com/fwlink/p/?linkid=243651)

[Solutions pour Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Solutions tierces

**HP Network Management Center (précédemment appelé HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) offre une gestion intégrée des pannes et des performances pour améliorer la disponibilité et les performances du réseau. Network Management Center fait partie de la solution HP Automated Network Management qui unifie les pannes, les performances, la configuration et la gestion des modifications.

Produits d’automatisation **et de gestion réseau Cisco**     Pour l’entreprise, Cisco dispose de plusieurs produits de gestion, dont la solution de gestion LAN CiscoWorks et le module Cisco Network Analysis, pour améliorer l’efficacité opérationnelle et réduire les temps morts du réseau. Pour plus d’informations sur ces produits, reportez-vous au site Web de Cisco à l’adresse [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) .

Le protocole SNMP (simple Network Management Protocol) (SNMP) est une norme de gestion réseau qui définit une stratégie de gestion des réseaux TCP/IP. SNMP vous permet de capturer des informations de configuration et d’État relatives au réseau, et d’envoyer les informations à un ordinateur désigné pour la surveillance des événements. Ce protocole de gestion de réseau basé sur des normes utilise une architecture distribuée qui inclut les éléments suivants :

  - Plusieurs nœuds gérés, chacun avec une entité SNMP appelée agent qui fournit l’accès à distance à l’instrumentation de gestion.

  - Au moins une entité SNMP appelée gestionnaire qui exécute les applications de gestion pour surveiller et contrôler les éléments gérés. Les éléments gérés sont des périphériques tels que des hôtes, des routeurs et ainsi de suite. Ils sont surveillés et contrôlés en accédant à leurs informations de gestion.

  - Un protocole de gestion, SNMP, est utilisé pour communiquer les informations de gestion entre les stations de gestion et les agents. Les informations de gestion font référence à une collection d’objets gérés qui résident dans une banque d’informations virtuelle appelée MIB (Management Information base).

<div>


> [!NOTE]  
> Des exemples de solutions de surveillance réseau tierces sont fournis ci-dessus. Cette liste n’est pas définitive et Microsoft ne privilégie pas une solution de fournisseur spécifique. Consultez un fournisseur de services réseau et ou votre fournisseur de technologies pour déterminer la meilleure solution de surveillance réseau pour votre organisation.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Outils de surveillance des performances du réseau d’un serveur individuel

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 permettrait aux administrateurs d’afficher les performances réseau de chaque serveur via le pack d’administration Windows Server 2012 : le pack d’administration du système d’exploitation Windows Server inclut un pack d’administration des performances qui permettrait aux administrateurs de surveiller les performances des cartes réseau et l’intégrité de la carte.

</div>

<div>

## <a name="windows-network-monitor"></a>Moniteur réseau Windows

Collecte, affiche, analyse l’utilisation des ressources sur un serveur et mesure le trafic réseau. Le moniteur réseau surveille exclusivement l’activité réseau. En capturant et en analysant les données réseau, et en utilisant ces données avec les journaux de performances, vous pouvez déterminer l’utilisation du réseau, identifier les problèmes réseau et prévoir les futurs besoins en matière de réseau.

Pour plus d’informations sur le moniteur réseau 3,4 et sur l’installation et la configuration du moniteur réseau, ainsi que sur la capture et l’analyse des données, consultez cette session : Moniteur réseau 3,3. Consultez également le [blog du moniteur réseau](https://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

