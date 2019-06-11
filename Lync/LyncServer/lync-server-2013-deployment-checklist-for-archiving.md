---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Liste de vérification du déploiement pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

L’archivage est automatiquement installé sur chaque serveur frontal de votre déploiement Lync Server 2013, mais vous devez le configurer pour pouvoir l’utiliser. Les étapes nécessaires pour les configurer, telles qu’elles sont résumées dans cette section, constituent le déploiement de l’archivage.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

La configuration de l’archivage dépend de l’option de stockage que vous choisissez:

  - Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer des stratégies d’archivage Lync Server 2013 pour vos utilisateurs. Au lieu de cela, configurez vos stratégies de conservation inaltérable pour la prise en charge de l’archivage pour les utilisateurs hébergés sur Exchange 2013 et leurs boîtes aux lettres sont placées dans la conservation inaltérable. Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange 2013.

  - Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs dans le cadre de votre déploiement, vous devez ajouter des bases de données d’archivage de Lync Server (bases de données SQL Server) à votre topologie, puis les publier, ainsi que configurer des stratégies et des paramètres pour vos utilisateurs, avant de pouvoir archiver des données pour ces utilisateurs. Vous pouvez déployer des bases de données d’archivage en même temps que le déploiement de votre topologie initiale ou après le déploiement d’au moins un pool frontal ou d’un serveur Standard Edition Server. Ce document décrit le déploiement de bases de données d’archivage en les ajoutant à un déploiement existant.

Si vous activez l’archivage dans une liste frontale ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools front-end et serveurs Standard Edition dans votre déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.

<div>


> [!IMPORTANT]  
> Si l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, veillez à déployer l’archivage, à configurer les stratégies et autres options au niveau approprié, puis à l’activer pour tous les utilisateurs appropriés avant d’activer ces utilisateurs pour Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processus de déploiement d’archivage

Le tableau ci-dessous décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.


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
<li><p>Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange 2013 pour l’archivage du stockage pour certains ou pour tous les utilisateurs), vous avez besoin d’un déploiement Exchange 2013 existant.</p></li>
<li><p>Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour l’archivage du stockage pour tout ou partie des utilisateurs, SQL Server sur le serveur qui stockera les données d’archivage.</p></li>
</ul>
<div>

> [!NOTE]  
> L’archivage s’exécute sur les serveurs front-end d’un pool d’entreprise et de serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.


</div></td>
<td><p>Utilisateur du domaine membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation relative à la prise en charge.</p>
<p>La <a href="lync-server-2013-server-software-and-infrastructure-support.md">prise en charge des logiciels et de l’infrastructure du serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configuration de systèmes et d’infrastructure pour l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p>La <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">prise en charge de l’intégration d’Exchange Server et SharePoint dans Lync Server 2013</a> dans la documentation de prise en charge.</p></td>
</tr>
<tr class="even">
<td><p><strong>Créez la topologie interne appropriée pour la prise en charge de l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement).</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter des bases de données d’archivage Lync Server 2013 (bases de données SQL Server) à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie afin d’incorporer des bases de données d’archivage, un compte membre du groupe utilisateurs locaux.</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers 2013 Lync Server (de façon à ce que le générateur de topologie puisse Configurez les DACL requis).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Ajouter des bases de données d’archivage à un déploiement 2013 Lync Server existant</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer l’authentification de serveur à serveur (uniquement si vous utilisez l’intégration de Microsoft Exchange)</strong></p></td>
<td><p>Configurer des serveurs pour activer l’authentification entre Lync Server 2013 et Exchange 2013. Nous vous recommandons d’exécuter <strong>test-CsExchangeStorageConnectivity testuser_sipUri – benne de dossiers</strong> pour valider la connectivité de stockage d’archivage Exchange avant de procéder à l’archivage.</p></td>
<td><p>Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync server 2013</a> dans la documentation de déploiement ou la documentation des opérations.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les stratégies et configurations d’archivage</strong></p></td>
<td><p>Configuration de l’archivage, y compris l’utilisation de l’intégration de Microsoft Exchange, de la stratégie globale et des stratégies de site et d’utilisateur (si vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage des données) et des options d’archivage spécifiques, telles que le mode et les données critiques exportation et suppression définitive.</p>
<p>Dans le cadre de l’utilisation de l’intégration de Microsoft Exchange, configurez les stratégies de blocage sur place Exchange, le cas échéant.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p>Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Déploiement de Lync Server et Microsoft Exchange dans différentes forêts

Si Microsoft Exchange Server n’est pas déployé dans la même forêt que Lync Server, vous devez vous assurer que les attributs Active Directory suivants sont synchronisés avec la forêt sur laquelle Lync Server est déployé:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.

</div>

</div>

<span> </span>

</div>

</div>

</div>

