---
title: 'Skype Entreprise Server 2015 : surveillance des performances du réseau'
TOCTitle: Surveillance des performances du réseau
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn720923(v=OCS.15)
ms:contentKeyID: 62240068
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Surveillance des performances du réseau dans Skype Entreprise Server 2015

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 est une technologie de communication en temps réel qui fait appel au réseau pour permettre aux utilisateurs de communiquer, par le biais de la messagerie instantanée (MI), d’appels vocaux ou de communications vidéo. Il est donc important de surveiller en continu les performances du réseau afin de s’assurer que les utilisateurs peuvent tirer le meilleur parti du mode de communication choisi.

Les performances réseau peuvent être mesurées à deux niveaux :

  - **Performances réseau globales** : ce niveau de mesure des performances permet à une organisation de créer une image du réseau « à grande échelle ». Il est généralement appliqué via des systèmes de surveillance réseau tiers. Ces systèmes reçoivent des données sur les performances et la capacité, qui sont transmises par des périphériques réseau tels que des routeurs et des commutateurs. Cela permet aux administrateurs de déterminer l’intégrité de n'importe quel composant du réseau à un moment donné de la journée.

  - **Performances de chaque serveur** : ce niveau de mesure des performances se limite à un serveur spécifique. Il permet aux administrateurs d’estimer les performances réseau d’un serveur spécifique pour aider à résoudre un problème de performances spécifique ou à évaluer les performances du serveur correspondant sur une période, dans le cadre d’une procédure de planification des capacités.

Vous pouvez surveiller le réseau à l’aide des outils décrits dans les sections qui suivent.

## Outils de surveillance des performances réseau globales

## System Center Operations Manager 2012

System Center Operations Manager offre des fonctions de gestion des services de bout en bout faciles à personnaliser et à étendre afin d'améliorer les niveaux de service disponibles dans un environnement informatique donné. Cela permet aux équipes de gestion des opérations et de l’informatique d’identifier et de résoudre les problèmes affectant l’intégrité des services informatiques distribués. La gestion des services de bout en bout ne se limite pas aux environnements Microsoft. La prise en charge des services Web de gestion (WS-Management), du protocole SNMP (Simple Network Management Protocol) et des solutions partenaires permet d’inclure dans les services surveillés sous System Center Operations Manager 2012 des systèmes exécutant un système d’exploitation non Microsoft et utilisant un type de matériel différent.

## System Center Operations Manager 2012 et solutions de gestion réseau tierces

**EMC Smarts** : EMC Solutions for Operations Manager permet de résoudre rapidement les problèmes affectant les niveaux de service. Vous pouvez gérer et surveiller votre chaîne de service informatique dans son intégralité à l’aide d’EMC Solutions for Operations Manager, en utilisant une solution automatisé intégrée. Vous identifierez facilement les causes principales des problèmes de performances et de disponibilité et les résoudrez plus vite, ce qui réduit les conséquences et les coûts. Voici les principaux avantages :

  - Gestion avancée et facilité d’emploi : concentrez-vous sur la valeur stratégique pour l’entreprise que vous pouvez apporter au lieu de trier et de filtrer manuellement des alertes qui créent la confusion.

  - **Résolution rapide** : résolvez les problèmes informatiques et répondez plus rapidement aux besoins de votre entreprise, en réduisant les conséquences et les coûts.

  - **Rationalisation des opérations** : évitez la complexité informatique en combinant différents outils, applications et terminaux de gestion.

Pour plus d’informations :

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Solutions pour Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

## Solutions tierces

**HP Network Management Center (anciennement HP OpenView)** : [HP Network Management Center](https://h10078.www1.hp.com/cda/hpms/display/main/hpms_content.jsp?zn=bto%26cp=1-11-15-119_4000_100__) permet une gestion intégrée des pannes et des performances afin d’améliorer la disponibilité et les performances du réseau. Network Management Center fait partie de la solution de gestion réseau automatisée de HP, qui centralise la gestion des pannes, des performances, des configurations et des modifications.

**Produits de gestion et d’automatisation du réseau de Cisco** : Cisco propose différents produits de gestion pour l’entreprise, dont CiscoWorks LAN Management Solution et Cisco Network Analysis Module, pour permettre d’améliorer l’efficacité des opérations et de réduire les temps d’indisponibilité du réseau. Pour plus d’informations sur ces produits, reportez-vous au site web de Cisco, à l’adresse [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

Protocole SNMP (Simple Network Management Protocol) : le protocole SNMP est une norme de gestion des réseaux qui définit une stratégie de gestion des réseaux TCP/IP. Le protocole SNMP permet d’acquérir des informations sur la configuration et le statut du réseau et d’envoyer des informations à un ordinateur désigné pour la surveillance des événements. Ce protocole de gestion des réseaux basé sur des normes utilise une architecture distribuée, qui inclut les possibilités suivantes :

  - Plusieurs nœuds gérés, chacun avec une entité SNMP appelée « agent » , qui permet d’accéder à distance aux instruments de gestion.

  - Au moins une entité SNMP considérée comme un gestionnaire exécutant des applications de gestion pour surveiller et contrôler les éléments gérés. Les éléments gérés sont des périphériques, comme des hôtes, des routeurs, etc. Ils sont surveillés et contrôlés en accédant à leurs informations de gestion.

  - Un protocole de gestion, le protocole SNMP, est utilisé pour communiquer les informations de gestion entre les postes de gestion et les agents. Les informations de gestion sont un ensemble d’objets gérés, qui se trouvent dans un magasin d’informations virtuel appelé « base d’informations de gestion » (MIB).

> [!NOTE]  
> Des exemples de solutions de surveillance tierces sont indiqués ci-dessus. Cette liste n’est pas définitive et Microsoft ne privilégie aucune solution tierce spécifique. Pour déterminer la meilleure solution de surveillance du réseau pour votre organisation, prenez conseil auprès d’un fournisseur de services réseau et/ou de votre fournisseur de technologies.

## Outils de surveillance des performances réseau de serveurs individuels

## System Center Operations Manager 2012

System Center Operations Manager 2012 permet aux administrateurs d’afficher les performances réseau de serveurs individuels par le biais du pack de gestion de Windows Server 2012 : le pack de gestion du système d’exploitation Windows Server inclut un pack de gestion des « performances » qui permet aux administrateurs de surveiller les performances et l’intégrité de la carte réseau.

## Windows Network Monitor

Collecte, affiche, analyse l’utilisation des ressources sur un serveur et mesure le trafic réseau. Network Monitor surveille exclusivement l’activité du réseau. En acquérant et en analysant des données relatives au réseau et en les utilisant avec des journaux des performances, vous pouvez déterminer l’utilisation du réseau, identifier les problèmes du réseau et anticiper les besoins futurs du réseau.

Pour plus d’informations sur Network Monitor 3.4, sur l’installation et la configuration de Network Monitor et sur l’acquisition et l’analyse des données, reportez-vous à cette session : Présentation de Network Monitor 3.3. Reportez-vous également au blog Network Monitor, à l’adresse : <http://blogs.technet.com/b/netmon/>.

