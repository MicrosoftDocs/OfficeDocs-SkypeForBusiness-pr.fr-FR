---
title: 'Lync Server 2013 : liste de vérification du déploiement pour l’archivage'
description: 'Lync Server 2013 : liste de vérification du déploiement pour l’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557710"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Liste de vérification du déploiement pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

L’archivage est automatiquement installé sur chaque serveur frontal de votre déploiement Lync Server 2013, mais vous devez toujours le configurer pour pouvoir l’utiliser. Les étapes de configuration requises, comme indiqué dans cette section, constituent le déploiement de l’archivage.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

La manière de configurer l’archivage dépend de l’option de stockage choisie :

  - Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer les stratégies d’archivage Lync Server 2013 pour vos utilisateurs. Au lieu de cela, configurez vos stratégies de blocage Exchange In-Place afin de prendre en charge l’archivage pour les utilisateurs hébergés sur Exchange 2013, dont les boîtes aux lettres sont placées In-Place blocage. Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange 2013.

  - Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez ajouter les bases de données d’archivage Lync Server (bases de données SQL Server) à votre topologie, puis les publier, ainsi que configurer des stratégies et des paramètres pour vos utilisateurs, avant de pouvoir archiver les données de ces utilisateurs. Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition. Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.

Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.

<div>


> [!IMPORTANT]  
> Si l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, veillez à déployer l’archivage, à configurer les stratégies et les autres options au niveau approprié, et à l’activer pour tous les utilisateurs appropriés, avant d’activer ces utilisateurs pour Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processus de déploiement de l’archivage

Le tableau suivant décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Rôles et appartenance aux groupes</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installer le matériel et les logiciels prérequis</strong></p></td>
<td><ul>
<li><p>Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange 2013 pour l’archivage de stockage pour tout ou partie des utilisateurs), vous avez besoin d’un déploiement Exchange 2013 existant.</p></li>
<li><p>Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.</p></li>
</ul>
<div>

> [!NOTE]  
> L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.


</div></td>
<td><p>Utilisateur du domaine membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure de serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configuration des systèmes et de l’infrastructure pour l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013</a> dans la documentation de prise en charge.</p></td>
</tr>
<tr class="even">
<td><p><strong>Créez la topologie interne appropriée pour prendre en charge l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement).</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter des bases de données d’archivage Lync Server 2013 (bases de données SQL Server) à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Ajout de bases de données d’archivage à un déploiement Lync Server 2013 existant</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer l’authentification de serveur à serveur (uniquement en cas d’utilisation de l’intégration de Microsoft Exchange)</strong></p></td>
<td><p>Configurez les serveurs pour activer l’authentification entre Lync Server 2013 et Exchange 2013. Nous vous recommandons d’exécuter <strong>le test-CsExchangeStorageConnectivity testuser_sipUri – benne de dossier</strong> pour valider la connectivité de stockage d’archivage Exchange avant d’activer l’archivage.</p></td>
<td><p>Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing Server-to-Server Authentication (OAuth) and Partner applications dans Lync server 2013</a> dans la documentation de déploiement ou la documentation des opérations.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les stratégies et les paramètres de l’archivage</strong></p></td>
<td><p>Configurez l’archivage, y compris s’il faut utiliser l’intégration de Microsoft Exchange, la stratégie globale et les stratégies de site et d’utilisateur (lorsque vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage de données) et des options d’archivage spécifiques, telles que le mode critique et l’exportation et la purge des données.</p>
<p>Si vous utilisez l’intégration de Microsoft Exchange, configurez les stratégies de blocage d’Exchange In-Place en fonction de vos besoins.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p>Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Déploiement de Lync Server et Microsoft Exchange dans des forêts différentes

Si Microsoft Exchange Server n’est pas déployé dans la même forêt que Lync Server, vous devez vous assurer que les attributs Active Directory d’Exchange suivants sont synchronisés avec la forêt où Lync Server est déployé :

1.  msExchUserHoldPolicies

2.  proxyAddresses

Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.

</div>

</div>

<span> </span>

</div>

</div>

</div>

