---
title: Services de domaine Active Directory pour Lync Server 2013
TOCTitle: Services de domaine Active Directory pour Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59679139
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Services de domaine Active Directory pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

services de domaine Active Directory fonctionne comme le service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. services de domaine Active Directory sert également de base sur laquelle l’infrastructure de sécurité Microsoft Lync Server 2013 est conçue. L’objectif de cette section est de décrire comment Lync Server 2013 utilise services de domaine Active Directory pour créer un environnement fiable pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur les extensions de Lync Server vers services de domaine Active Directory et sur la préparation de votre environnement pour services de domaine Active Directory, voir [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement. Pour plus d’informations sur le rôle de services de domaine Active Directory dans les réseaux Windows Server, consultez la documentation pour la version du système d’exploitation que vous utilisez.

Lync Server 2013 utilise services de domaine Active Directory pour enregistrer les éléments suivants :

  - Paramètres globaux nécessaires à tous les serveurs exécutant Lync Server 2013 dans une forêt.

  - Informations de service qui identifient les rôles de tous les serveurs exécutant Lync Server 2013 dans une forêt.

  - Certains paramètres utilisateur.

## Infrastructure de Active Directory

Les exigences d’infrastructure pour Active Directory incluent les éléments suivants :

  - Systèmes d’exploitation requis pour les contrôleurs de domaine

  - Exigences de niveau fonctionnel de domaine et de forêt

  - Exigences de domaine de catalogue global

Pour plus d’informations, voir [Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

## Préparation de services de domaine Active Directory

> [!NOTE]  
> Nous vous conseillons de déployer les paramètres globaux sur le conteneur Configuration au lieu du conteneur Système. Ceci n’améliore pas la sécurité, mais peut entraîner des améliorations d’extensibilité pour certaines topologies services de domaine Active Directory. Si vous effectuez une migration à partir de Microsoft Office Communications Server 2007 et que vous avez utilisé le conteneur Système mais que vous prévoyez d’utiliser le conteneur Configuration, vous DEVEZ déplacer les paramètres dans le conteneur Système AVANT de mettre à niveau les préparations. Pour migrer les paramètres de votre conteneur Système vers le conteneur Configuration, voir l’outil de migration des paramètres globaux de Office Communications Server 2007 à l’adresse : <a href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</a>.

Lors du déploiement de Lync Server 2013, la première étape consiste à préparer services de domaine Active Directory. La préparation de services de domaine Active Directory pour Lync Server 2013 se compose des trois étapes suivantes :

  - **Préparer le schéma**. Cette tâche étend le schéma dans services de domaine Active Directory afin d’inclure les classes et les attributs spécifiques à Lync Server 2013. Pour plus d’informations sur la préparation du schéma, voir [Exécution de la préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md) dans la documentation de déploiement. Pour plus d’informations, voir [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Préparer la forêt**. Cette tâche crée les paramètres globaux et les objets dans le domaine racine de la forêt, ainsi que le service universel et les groupes administratifs qui régissent l’accès à ces paramètres et objets. Pour plus d’informations sur la préparation de la forêt, voir [Exécution de la préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md) dans la documentation de déploiement.

  - **Préparer le domaine**. Cette tâche ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. Cette tâche doit être accomplie dans l’ensemble des domaines sur lesquels vous souhaitez déployer des serveurs exécutant Lync Server 2013 et sur les domaines sur lesquels se trouvent vos utilisateurs Lync Server. Pour plus d’informations sur la préparation du domaine, voir [Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md) dans la documentation de déploiement.

Pour obtenir une présentation du processus complet pour la préparation de Active Directory et des droits et autorisations requis pour effectuer chaque étape, voir [Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

## Groupes universels

Lors de la préparation de la forêt, Lync Server 2013 crée divers groupes universels dans services de domaine Active Directory qui disposent de l’autorisation permettant d’accéder aux paramètres globaux et aux services ainsi que de les gérer. Ces groupes universels incluent :

  - **Groupes administratifs**. Ces groupes définissent les rôles d’administrateur fondamentaux pour un réseau Lync Server. Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure de Lync Server.

  - **Groupes de service**. Ces groupes sont des comptes de service requis pour accéder à divers services fournis par Lync Server.

  - **Groupes d’infrastructure**. Ces groupes permettent d’accéder à des zones spécifiques de l’infrastructure de Lync Server. Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.

Pour plus d’informations sur les groupes universels spécifiques associés lors de la préparation d’AD pour Lync Server, ainsi que sur les groupes de service et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [Modifications effectuées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.

> [!NOTE]  
> Lync Server 2013 prend en charge les groupes universels dans Windows Server 2012 pour les serveurs exécutant Lync Server 2013, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. La prise en charge des groupes universels, combinée à la délégation d’administrateurs, simplifie la gestion d’un déploiement Lync Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux.

## Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [Modifications effectuées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, voir [Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

## Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Elle crée des ACE privées spécifiques sur le conteneur des paramètres globaux utilisé par Lync Server. Ce conteneur n’est utilisé que par Lync Server et se trouve soit dans le conteneur Configuration soit dans le conteneur Système du domaine racine, selon l’emplacement où sont enregistrés les paramètres globaux.

L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.

Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et du domaine, voir [Modifications effectuées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) et [Modifications effectuées par la préparation de domaine dans Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) dans la documentation de déploiement.

Les organisations verrouillent souvent services de domaine Active Directory (AD DS) afin de limiter les risques de sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013. Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un environnement Active Directory verrouillé, les autorisations doivent être définies manuellement sur les conteneurs et OU qui en ont besoin. Pour plus d’informations, voir [Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

## Informations du serveur

Lors de l’activation, Lync Server 2013 publie les informations du serveur aux trois emplacements suivants de services de domaine Active Directory :

  - Un point de connexion de service (SCP) sur chaque objet ordinateur de Active Directory correspondant à un ordinateur physique sur lequel Lync Server 2013 est installé.

  - Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.

  - Les serveurs approuvés spécifiés dans Générateur de topologie.

## Points de connexion de service

Chaque objet Lync Server 2013 dans services de domaine Active Directory présente un SCP appelé RTC Services, qui contient un certain nombre d’attributs qui identifient chaque ordinateur et indiquent les services fournis. Parmi les attributs SCP les plus importants se trouvent *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* et *serviceBindingInformation*. Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs SCP.

## Objets Serveur Active Directory

Chaque rôle serveur Lync Server 2013 dispose d’un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle. De plus, lorsqu’un serveur Standard Edition est activé, ou lorsqu’un pool Enterprise Edition est créé, Lync Server 2013 crée un nouvel objet **msRTCSIP-Pool** dans le conteneur **msRTCSIP-Pools**. La classe **msRTCSIP-Pool** spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool. (Un serveur Standard Edition est considéré comme un pool logique dont les parties frontales et principales sont colocalisées sur un même ordinateur.)

## Serveurs approuvés

Dans Lync Server 2013, les serveurs approuvés sont ceux spécifiés lorsque vous exécutez Générateur de topologie et que vous publiez votre topologie. La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Lync Server 2013, un serveur approuvé est un serveur qui répond aux critères suivants :

  - Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.

  - Le serveur présente un certificat valide d’une autorité de certification approuvée. Pour plus d’informations, voir [Configuration requise pour les infrastructures de certificat pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette double exigence évite une attaque éventuelle, mais peu probable, dans laquelle un serveur malveillant tente de s’emparer du FQDN d’un serveur valide.

De plus, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et Microsoft Office Communications Server 2007 de communiquer avec les serveurs Lync Server 2013, Lync Server 2013 crée des conteneurs lors de la préparation de la forêt qui contiendront les listes des serveurs approuvés pour les versions précédentes. Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.

### Listes des serveurs approuvés et leurs conteneurs Active Directory pour compatibilité avec les versions précédentes

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Liste des serveurs approuvés</th>
<th>Conteneur Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveurs Standard Edition et serveurs frontaux du pool d’entreprise</p></td>
<td><p>RTC Service/Paramètres globaux</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de conférence</p></td>
<td><p>RTC Service/MCU approuvés</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de composants Web</p></td>
<td><p>RTC Service/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)</p></td>
<td><p>RTC Service/Services approuvés</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs proxy</p></td>
<td><p>Lync Server 2013 ne prend pas en charge la compatibilité descendante pour les serveurs proxy</p></td>
</tr>
</tbody>
</table>


Pour prendre en charge les serveurs approuvés des versions précédentes, vous devez exécuter l’outil Best Practices Analyzer. Pour plus d’informations sur l’exécution de Best Practices Analyzer, voir [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).

