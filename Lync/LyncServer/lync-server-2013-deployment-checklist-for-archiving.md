---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour l’archivage'
TOCTitle: Liste de vérification du déploiement pour l’archivage
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205009(v=OCS.15)
ms:contentKeyID: 49297734
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’archivage est automatiquement installé sur chaque serveur frontal de votre déploiement Lync Server 2013, mais vous devez quand même le configurer avant de pouvoir l’utiliser. Les étapes de configuration requises, comme indiqué dans cette section, constituent le déploiement de l’archivage.

## Séquence de déploiement

La manière de configurer l’archivage dépend de l’option de stockage choisie :

  - Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, il n’est pas nécessaire de configurer des stratégies d’archivage Lync Server 2013 pour vos utilisateurs. Configurez plutôt vos stratégies d’archive permanente Exchange afin de prendre en charge l’archivage pour les utilisateurs hébergés sur Exchange 2013, avec leurs boîtes aux lettres placées en archive permanente. Pour plus d’informations sur la configuration de ces stratégies, reportez-vous à la documentation du produit Exchange 2013.

  - Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez ajouter des bases de données d’archivage Lync Server (bases de données SQL Server) à votre topologie, puis la publier, ainsi que configurer des stratégies et des paramètres pour vos utilisateurs, avant de pouvoir archiver des données pour ces derniers. Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition. Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.

Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.

> [!IMPORTANT]  
> Si l’archivage est primordial dans votre organisation à des fins de conformité, veillez à le déployer, à configurer les stratégies et les autres options au niveau approprié, ainsi qu’à l’activer pour tous les utilisateurs concernés, avant d’activer Lync Server 2013 pour ces utilisateurs.

## Processus de déploiement de l’archivage

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
<td><ul><li><p>Pour utiliser l’intégration de Microsoft Exchange (avec Exchange 2013 pour le stockage d’archives d’une partie ou de la totalité des utilisateurs), vous avez besoin d’un déploiement Exchange 2013 existant.</p></li><li><p>Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.</p></li></ul>
<div>

> [!NOTE]  
> L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.
</div></td>
<td><p>Utilisateur du domaine membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configuration des systèmes et de l’infrastructure pour l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013</a> dans la documentation de prise en charge.</p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge l’archivage (uniquement en cas de non-utilisation de l’intégration de Microsoft Exchange pour tous les utilisateurs du déploiement)</strong></p></td>
<td><p>Exécutez le Générateur de topologie pour ajouter des bases de données d’archivage Lync Server 2013 (bases de données SQL Server) à la topologie, puis publiez cette dernière.</p></td>
<td><p>Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.</p>
<p>Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (pour que le générateur de topologie puisse configurer les DACL requises) est requis.</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Ajout des bases de données d’archivage à un déploiement Lync Server 2013 existant</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer l’authentification de serveur à serveur (uniquement en cas d’utilisation de l’intégration de Microsoft Exchange)</strong></p></td>
<td><p>Configurez les serveurs de sorte à permettre une authentification entre Lync Server 2013 et Exchange 2013. Nous vous recommandons d’exécuter <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> pour valider la connectivité du stockage d’archives Exchange avant d’activer l’archivage.</p></td>
<td><p>Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013</a> dans la documentation de déploiement ou la documentation des opérations.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les stratégies et les paramètres de l’archivage</strong></p></td>
<td><p>Configurez l’archivage, notamment l’utilisation ou non de l’intégration de Microsoft Exchange, la stratégie globale et les éventuelles stratégies au niveau de l’utilisateur et du site (en cas de non-utilisation de l’intégration de Microsoft Exchange pour le stockage de toutes les données), ainsi que des options d’archivage spécifiques, telles que le mode critique et l’exportation ou le vidage des données.</p>
<p>En cas d’utilisation de l’intégration de Microsoft Exchange, configurez des stratégies d’archive permanente Exchange en fonction des besoins.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</p>
<p>Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


## Déploiement de Lync Server et de Microsoft Exchange dans des forêts différentes

Si Microsoft Exchange Server n’est pas déployé dans la même forêt que Lync Server, vous devez vous assurer que les attributs Active Directory d’Exchange suivants sont synchronisés avec la forêt sur laquelle Lync Server est déployé :

1.  msExchUserHoldPolicies

2.  proxyAddresses

Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.

