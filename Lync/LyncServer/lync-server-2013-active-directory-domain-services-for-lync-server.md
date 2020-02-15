---
title: 'Lync Server 2013 : services de domaine Active Directory pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b53b878d7f41a5eb83eb67d98fc69d68709a603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Services de domaine Active Directory pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-13_

Les services de domaine Active Directory sont des fonctions de service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2. Les services de domaine Active Directory servent également de base à la création de l’infrastructure de sécurité Microsoft Lync Server 2013. L’objectif de cette section est de décrire comment Lync Server 2013 utilise les services de domaine Active Directory pour créer un environnement de confiance pour la messagerie instantanée, la conférence Web, les médias et la voix. Pour plus d’informations sur les extensions Lync Server aux services de domaine Active Directory et sur la préparation de votre environnement pour les services de domaine Active Directory, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement. Pour des détails sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation concernant votre version du système d’exploitation.

Lync Server 2013 utilise les services de domaine Active Directory pour stocker les éléments suivants :

  - Paramètres globaux requis par tous les serveurs exécutant Lync Server 2013 dans une forêt.

  - Informations de service qui identifient les rôles de tous les serveurs exécutant Lync Server 2013 dans une forêt.

  - Certains paramètres utilisateur.

<div>

## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Les conditions d’infrastructure requises pour Active Directory incluent les suivantes :

  - Configuration de système d’exploitation requise pour les contrôleurs de domaine

  - Configuration requise de niveau fonctionnel du domaine ou de la forêt

  - Configuration de catalogue global requise

Pour plus d’informations, voir [Active Directory infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Préparation des services de domaine Active Directory

<div>


> [!NOTE]  
> Nous vous recommandons de déployer les paramètres globaux du conteneur système au lieu du conteneur de configuration. Cela n’améliore pas la sécurité, mais peut induire des améliorations en termes d’extensibilité pour certaines topologies de service de domaine Active Directory. Si vous effectuez une migration à partir de Microsoft Office Communications Server 2007 et que vous avez utilisé le conteneur système mais que vous envisagez d’utiliser le conteneur de configuration, vous devez déplacer les paramètres dans le conteneur système avant de procéder à une mise à niveau. Pour migrer vos paramètres de conteneur système vers le conteneur de configuration, reportez-vous à l' <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>outil de migration des paramètres globaux d’Office Communications Server 2007 à l’adresse.



</div>

Lors du déploiement de Lync Server 2013, la première étape consiste à préparer les services de domaine Active Directory. La préparation des services de domaine Active Directory pour Lync Server 2013 comprend les trois étapes suivantes :

  - **Préparer le schéma**. Cette tâche étend le schéma dans les services de domaine Active Directory pour inclure des classes et des attributs spécifiques à Lync Server 2013. Pour plus d’informations sur la préparation du schéma, voir exécution de la [préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md) dans la documentation de déploiement. Pour plus d’informations, reportez-vous à [migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Préparer la forêt**. Cette tâche crée les paramètres globaux et les objets dans le domaine racine de la forêt, conjointement aux groupes d’administration et de service universels qui gouvernent l’accès à ces paramètres et objets. Pour plus d’informations sur la préparation de la forêt, voir exécution de la [préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md) dans la documentation de déploiement.

  - **Préparer le domaine**. Cette tâche ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui accordent les autorisations pour héberger et gérer les utilisateurs du domaine. Cette tâche doit être exécutée dans tous les domaines où vous souhaitez déployer des serveurs exécutant Lync Server 2013 et tous les domaines où les utilisateurs de Lync Server sont hébergés. Pour plus d’informations sur la préparation du domaine, voir [Running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) dans la documentation de déploiement.

Pour obtenir une vue d’ensemble du processus complet de préparation d’Active Directory et des droits et autorisations requis pour effectuer chaque étape, voir [Active Directory infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

</div>

<div>

## <a name="universal-groups"></a>Groupes universels

Lors de la préparation de la forêt, Lync Server 2013 crée plusieurs groupes universels dans les services de domaine Active Directory qui ont l’autorisation d’accéder aux paramètres globaux et de les gérer. Ces groupes universels incluent les suivants :

  - **Groupes d’administration**. Ces groupes définissent les rôles d’administrateur fondamentaux d’un réseau Lync Server. Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure Lync Server.

  - **Groupes de services** Ces groupes sont des comptes de service qui sont requis pour accéder aux différents services fournis par Lync Server.

  - **Groupes d’infrastructure**. Ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure Lync Server. Elles fonctionnent comme des composants de groupes d’administration et vous ne devez pas les modifier ni y ajouter des utilisateurs directement. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.

Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Lync Server, ainsi que les groupes de service et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Lync Server 2013 prend en charge les groupes universels dans le Windows Server 2012 pour les serveurs exécutant Lync Server 2013, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine. Les membres des groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arborescence de domaine ou de la forêt et peuvent se voir attribuer des autorisations dans n’importe quel domaine de l’arborescence de domaine ou de la forêt. La prise en charge de groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement Lync Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre pour permettre à un administrateur de gérer les deux.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, voir [Role-Based Access Control (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Il crée des ACE privées spécifiques sur le conteneur de paramètres globaux utilisé par Lync Server. Ce conteneur est utilisé uniquement par Lync Server et se trouve dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.

L’étape de préparation du domaine ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui accordent les autorisations d’hébergement et de gestion des utilisateurs dans le domaine. La préparation du domaine créé des entrées de contrôle d’accès sur la racine du domaine et dans trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine.

Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir [modifications apportées par la préparation de la forêt dans Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) et les [modifications apportées par la préparation du domaine dans Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) dans la documentation de déploiement.

Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) dans le but de réduire les risques liés à la sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013. Cela peut inclure la suppression des entrées de contrôle d’accès des conteneurs et des unités d’organisation ou la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un environnement Active Directory verrouillé, les autorisations doivent être manuellement définies sur les conteneurs et les unités d’organisation qui les requièrent. Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

</div>

<div>

## <a name="server-information"></a>Informations relatives aux serveurs

Lors de l’activation, Lync Server 2013 publie des informations sur le serveur aux trois emplacements suivants dans les services de domaine Active Directory :

  - Un point de connexion de service (SCP) sur chaque objet ordinateur Active Directory correspondant à un ordinateur physique sur lequel Lync Server 2013 est installé.

  - les objets serveur créés dans le conteneur de la classe **msRTCSIP-Pools** ;

  - Serveurs approuvés spécifiés dans le générateur de topologies.

</div>

<div>

## <a name="service-connection-points"></a>Points de connexion de service

Chaque objet Lync Server 2013 dans les services de domaine Active Directory possède un SCP appelé services RTC, qui, à son tour, contient un certain nombre d’attributs qui identifient chaque ordinateur et spécifient les services qu’il fournit. Les principaux attributs d’un point de connexion de service sont notamment *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* et *serviceBindingInformation*. Les applications tierces de gestion des actifs peuvent obtenir des informations sur les serveurs d’un déploiement en recherchant ces attributs, ainsi que d’autres attributs de point de connexion de service.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objets serveur Active Directory

Chaque rôle serveur Lync Server 2013 possède un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle. En outre, lorsqu’un serveur Standard Edition est activé, ou lorsqu’un pool Enterprise Edition est créé, Lync Server 2013 crée un nouvel objet **msRTCSIP-pool** dans le conteneur **msRTCSIP-pools** . La classe **msRTCSIP-Pool** définit le nom de domaine complet (FQDN) du pool, de même que l’association entre les composants frontal et principal du pool. (Un serveur Standard Edition Server est considéré comme un pool logique dont les composants frontal et principal sont colocalisés sur un même ordinateur.)

</div>

<div>

## <a name="trusted-servers"></a>Serveurs approuvés

Dans Lync Server 2013, les serveurs de confiance sont ceux qui sont spécifiés lorsque vous exécutez le générateur de topologies et que vous publiez votre topologie. La topologie publiée, avec toutes les informations sur les serveurs, est stockée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Lync Server 2013, un serveur approuvé est un serveur qui répond aux critères suivants :

  - Le nom de domaine complet (FQDN) du serveur existe dans la topologie stockée dans le magasin central de gestion.

  - Le serveur présente un certificat valide émanant d’une autorité de certification approuvée. Pour plus d’informations, reportez-vous à [Certificate infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si un de ces critères n’est pas respecté, le serveur n’est pas approuvé et la connexion au serveur est refusée. Cette double exigence permet de contrer une attaque, peu probable, au cours de laquelle un serveur non autorisé tente de s’approprier le nom de domaine complet d’un serveur valide.

De plus, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et de Microsoft Office Communications Server 2007 de communiquer avec des serveurs Lync Server 2013, Lync Server 2013 crée des conteneurs lors de la préparation de la forêt pour les listes de serveurs approuvés pour les versions précédentes. Le tableau ci-dessous décrit les conteneurs créés dans un but de compatibilité avec les déploiements précédents.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listes de serveurs approuvés et leurs conteneurs Active Directory pour compatibilité avec les éditions précédentes

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
<td><p>Serveurs Standard Edition Server et serveurs frontaux de pool d’entreprise</p></td>
<td><p>Service RTC/Paramètres globaux</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de conférence</p></td>
<td><p>RTC Service/Serveurs MCU approuvés (Trusted MCUs)</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de composants web</p></td>
<td><p>Service RTC/Serveurs de composants web approuvés</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)</p></td>
<td><p>Service RTC/Services approuvés</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs proxy</p></td>
<td><p>Lync Server 2013 ne prend pas en charge la compatibilité descendante pour les serveurs proxy</p></td>
</tr>
</tbody>
</table>


Pour prendre en charge les serveurs de confiance des versions précédentes, vous devez exécuter l’outil Best Practices Analyzer. Pour plus d’informations sur l’exécution de Best Practices [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)Analyzer, reportez-vous à la rubrique.

</div>

</div>

<span> </span>

</div>

</div>

</div>

