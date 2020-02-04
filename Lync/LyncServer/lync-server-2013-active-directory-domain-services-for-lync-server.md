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
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Services de domaine Active Directory pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-13_

Les fonctions des services de domaine Active Directory comme service d’annuaire pour Windows Server 2003, Windows Server 2008, Windows Server 2012 et les réseaux Windows Server 2012 R2. Les services de domaine Active Directory servent également de base sur l’infrastructure de sécurité de Microsoft Lync Server 2013. Cette section décrit la façon dont Lync Server 2013 utilise les services de domaine Active Directory (AD FS) pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix. Pour plus d’informations sur les extensions serveur Lync aux services de domaine Active Directory et sur la préparation de votre environnement pour les services de domaine Active Directory, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement. Pour plus d’informations sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation relative à la version du système d’exploitation que vous utilisez.

Lync Server 2013 utilise les services de domaine Active Directory pour stocker les éléments suivants :

  - Paramètres globaux pour lesquels tous les serveurs exécutant Lync Server 2013 dans une forêt nécessitent.

  - Des informations de service qui identifient les rôles de tous les serveurs exécutant Lync Server 2013 dans une forêt.

  - Certains paramètres utilisateur.

<div>

## <a name="active-directory-infrastructure"></a>Infrastructure Active Directory

Les exigences en matière d’infrastructure pour Active Directory sont les suivantes :

  - Systèmes d’exploitation requis pour les contrôleurs de domaine

  - Exigences de niveau fonctionnel de domaine et de forêt

  - Exigences de domaine de catalogue global

Pour plus d’informations, voir [Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Préparation des services de domaine Active Directory

<div>


> [!NOTE]  
> Nous vous recommandons de déployer des paramètres globaux sur le conteneur de configuration au lieu du conteneur système. Cela ne renforce pas la sécurité, mais peut entraîner des améliorations de l’extensibilité pour certaines topologies de services de domaine Active Directory. Si vous effectuez une migration à partir de Microsoft Office Communications Server 2007 et que vous avez utilisé le conteneur système mais que vous envisagez d’utiliser le conteneur de configuration, vous devez déplacer les paramètres dans le conteneur système avant de procéder à des préparations de mise à niveau. Pour migrer vos paramètres de conteneur système vers le conteneur de configuration, voir l’outil de migration des paramètres <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>globaux d’Office Communications Server 2007 à l’adresse.



</div>

Lors du déploiement de Lync Server 2013, la première étape consiste à préparer les services de domaine Active Directory. La préparation des services de domaine Active Directory pour Lync Server 2013 comprend les trois étapes suivantes :

  - **Préparer le schéma**. Cette tâche étend le schéma dans les services de domaine Active Directory pour inclure des classes et des attributs spécifiques à Lync Server 2013. Pour plus d’informations sur la préparation du schéma, voir exécution de la [préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md) dans la documentation de déploiement. Pour plus d’informations, reportez-vous à [migration d’Office Communications Server 2007 R2 vers Lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Préparer la forêt**. Cette tâche crée des paramètres globaux et des objets dans le domaine racine de la forêt, ainsi que les groupes de services et d’administration universels régissant l’accès à ces paramètres et aux objets. Pour plus d’informations sur la préparation de la forêt, voir exécution de la [préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md) dans la documentation de déploiement.

  - **Préparer le domaine**. Cette tâche ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui accordent des autorisations d’hébergement et de gestion des utilisateurs au sein du domaine. Cette tâche doit être effectuée dans tous les domaines dans lesquels vous souhaitez déployer des serveurs exécutant Lync Server 2013 et les domaines dans lesquels résident les utilisateurs de Lync Server. Pour plus d’informations sur la préparation du domaine, voir exécution de la [préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md) dans la documentation de déploiement.

Pour obtenir une vue d’ensemble du processus complet de préparation d’Active Directory et des droits et autorisations nécessaires à chaque étape, voir la [Configuration requise en matière d’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.

</div>

<div>

## <a name="universal-groups"></a>Groupes universels

Lors de la préparation de la forêt, Lync Server 2013 crée divers groupes universelles dans les services de domaine Active Directory, qui sont autorisés à accéder à des services globaux et à gérer les services et les paramètres globaux. Ces groupes universels incluent :

  - **Groupes administratifs**. Ces groupes définissent les rôles d’administrateur de base pour un réseau Lync Server. Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure de Lync Server.

  - **Groupes de service**. Il s’agit des comptes de service nécessaires pour accéder aux différents services fournis par Lync Server.

  - **Groupes d’infrastructure**. Ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure du serveur Lync. Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs. Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.

Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Lync Server, ainsi que les groupes de services et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Lync Server 2013 prend en charge les groupes universels dans Windows Server 2012 pour les serveurs exécutant Lync Server 2013, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. La prise en charge des groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement de Lync Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Contrôle d’accès basé sur un rôle

En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC). Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement. Pour plus d’informations sur les groupes RBAC, voir [contrôle de contrôle d’accès basé sur les rôles (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entrées de contrôle d’accès (ACE) et héritage

La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée. Il crée des entrées ACE privées spécifiques sur le conteneur de paramètres globaux utilisé par Lync Server. Ce conteneur est utilisé uniquement par Lync Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.

L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.

Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir [modifications apportées par la préparation de la forêt dans Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) et [modifications apportées par la préparation du domaine dans Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) dans la documentation de déploiement.

Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) pour réduire les risques liés à la sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013. Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur. Dans un environnement Active Directory verrouillé, les autorisations doivent être définies manuellement sur les conteneurs et les unités d’organisation qui en ont besoin. Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

</div>

<div>

## <a name="server-information"></a>Informations du serveur

Au cours de l’activation, Lync Server 2013 publie les informations du serveur aux trois emplacements suivants dans les services de domaine Active Directory (AD FS) :

  - Un point de connexion de service (SCP) sur chaque objet d’ordinateur Active Directory correspondant à un ordinateur physique sur lequel Lync Server 2013 est installé.

  - Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.

  - Serveurs de confiance spécifiés dans le générateur de topologie.

</div>

<div>

## <a name="service-connection-points"></a>Points de connexion de service

Chaque objet Lync Server 2013 dans les services de domaine Active Directory possède un SCP appelé services RTC, qui à son tour contient un certain nombre d’attributs identifiant chaque ordinateur et spécifiant les services qu’il fournit. Parmi les attributs des points de connexion de service les plus importants se trouvent *serviceDNSName *, *serviceDNSNameType *, *serviceClassname * et *serviceBindingInformation *. Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs de points de connexion de service.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objets serveur Active Directory

Chaque rôle serveur Lync Server 2013 possède un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle. Par ailleurs, lorsqu’un serveur Standard Edition Server est activé ou qu’un pool Enterprise Edition est créé, Lync Server 2013 crée un nouvel objet de **pool msRTCSIP** dans le conteneur **msRTCSIP-pools** . La classe **msRTCSIP-Pool ** spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool. (Un serveur Standard Edition Server est considéré comme une réserve logique dont les extrémités avant et arrière sont colocalisées sur un seul ordinateur.)

</div>

<div>

## <a name="trusted-servers"></a>Serveurs approuvés

Dans Lync Server 2013, les serveurs de confiance sont ceux spécifiés lors de l’exécution du générateur de topologie et de la publication de votre topologie. La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion. Seuls les serveurs définis dans le magasin central de gestion sont approuvés. Dans Lync Server 2013, un serveur approuvé est l’un des critères suivants :

  - Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.

  - Le serveur présente un certificat valide d’une autorité de certification approuvée. Pour plus d’informations, voir [Configuration requise en matière d’infrastructure de certificats pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette double exigence évite une attaque éventuelle, mais peu probable, dans laquelle un serveur malveillant tente de s’emparer du nom de domaine complet d’un serveur valide.

Par ailleurs, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et de Microsoft Office Communications Server 2007 de communiquer avec des serveurs Lync Server 2013, Lync Server 2013 crée des conteneurs lors de la préparation de la forêt pour les listes de serveurs de confiance pour les versions précédentes. Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listes de serveurs approuvés et leurs conteneurs Active Directory pour la compatibilité avec les versions précédentes

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
<td><p>Serveurs Standard Edition et serveurs frontaux du pool d’entreprise</p></td>
<td><p>RTC Service/Paramètres globaux</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de conférence</p></td>
<td><p>RTC Service/MCU approuvés</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs de composants Web</p></td>
<td><p>RTC Service/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)</p></td>
<td><p>RTC Service/Services approuvés</p></td>
</tr>
<tr class="odd">
<td><p>Serveurs proxy</p></td>
<td><p>Lync Server 2013 ne prend pas en charge la compatibilité descendante pour les serveurs proxy</p></td>
</tr>
</tbody>
</table>


Pour prendre en charge des serveurs de confiance de versions précédentes, vous devez exécuter l’outil d’analyse des pratiques recommandées. Pour plus d’informations sur l’exécution de l’analyseur [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)de recommandations, voir.

</div>

</div>

<span> </span>

</div>

</div>

</div>

