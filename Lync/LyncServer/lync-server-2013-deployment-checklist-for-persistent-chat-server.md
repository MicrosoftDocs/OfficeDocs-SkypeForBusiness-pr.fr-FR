---
title: 'Lync Server 2013 : liste de vérification du déploiement pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a01d38cec8d03a75d5f295c61f6e591da43f4a61
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Le déploiement de Lync Server 2013, le serveur de conversation permanente nécessite que vous le déployiez dans l’ordre correct et que vous terminiez toutes les étapes de déploiement requises.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

Vous pouvez déployer le serveur de conversation permanente après avoir déployé votre topologie initiale, notamment au moins un serveur Lync Server 2013, un pool frontal ou un serveur Lync Server 2013, Standard Edition. Cette rubrique décrit comment déployer le serveur de conversation permanente en l’ajoutant à un déploiement existant.

</div>

<div>

## <a name="deployment-process"></a>Processus de déploiement

Le tableau suivant répertorie les étapes de base pour déployer le serveur de conversation permanente et fournit des liens pour obtenir plus de détails.

### <a name="persistent-chat-server-deployment-process"></a>Processus de déploiement du serveur de conversation permanente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tâche</th>
<th>Étapes</th>
<th>Rôles et appartenance aux groupes nécessaires</th>
<th>Rubriques associées</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installer le matériel et les logiciels prérequis</strong></p></td>
<td><p>Sur le matériel conforme à la configuration système requise, installez ce qui suit :</p>
<ul>
<li><p>Sur les serveurs frontaux du serveur de conversation permanente :</p></li>
</ul>
<ul>
<li><p>Un système d’exploitation conforme à la configuration système requise</p></li>
<li><p>Conditions préalables logicielles pour les ordinateurs exécutant Lync Server 2013</p></li>
<li><p>SQL Server sur le serveur qui hébergera la base de données du serveur de conversation permanente</p></li>
</ul>
<p>Si la conformité du serveur de conversation permanente est requise :</p>
<ul>
<li><p>SQL Server sur le serveur qui hébergera la base de données de conformité du serveur de conversation permanente</p></li>
</ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge le serveur de conversation permanente (et éventuellement la conformité de la conversation permanente)</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter un pool de serveurs de conversation permanente à votre topologie :</p>
<ul>
<li><p>Ajouter des composants de serveur de conversation permanente à la topologie</p></li>
<li><p>Créer une base de données SQL Server pour le magasin de serveurs de conversation permanente (et un serveur SQL Server de sauvegarde pour la récupération d’urgence)</p></li>
<li><p>Définir un nouveau magasin de fichiers Lync ou utiliser un magasin de fichiers Lync existant pour les fichiers du serveur de conversation permanente</p></li>
<li><p>Associer le pool Lync Server 2013 qui peut acheminer les demandes à ce pool de serveurs de conversation permanente</p></li>
</ul>
<p>Si la conformité de la conversation permanente est requise :</p>
<ul>
<li><p>Ajouter un magasin de conformité de conversation permanente</p></li>
<li><p>Cliquez sur la case à cocher définition de pool de serveurs de conversation permanente pour activer la conformité.</p></li>
<li><p>Publier la topologie</p></li>
</ul>
<p>Si vous installez le serveur de conversation permanente sur Standard Edition, le nom de domaine complet (FQDN) du pool de serveurs de conversation permanente doit correspondre au serveur Standard Edition et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express sur la version standard. Serveur d’édition</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins, ainsi que l’utilisateur doivent également disposer d’autorisations de contrôle complètes (lecture/écriture/modification) sur le magasin de fichiers Lync pour les fichiers du serveur de conversation permanente (afin que le générateur de topologie puisse configurer les DACL requises).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Déployer le serveur de conversation permanente</strong></p></td>
<td><p>Exécutez le programme d’installation de Lync Server sur tous les ordinateurs exécutant le serveur de conversation permanente. Le programme d’installation du serveur de conversation permanente est intégré à l’Assistant Déploiement de Lync Server 2013, qui fournit les instructions suivantes :</p>
<ul>
<li><p>Déployer le magasin de gestion local</p></li>
<li><p>Installer les services de serveur de conversation permanente</p></li>
<li><p>Demander et assigner des certificats</p></li>
<li><p>Exécuter et démarrer les services</p></li>
</ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p><strong>Créer un administrateur de conversation permanente</strong></p></td>
<td><p>Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.</p></td>
<td><p>Un utilisateur membre des administrateurs de domaines.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Ajout d’un administrateur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configuration du serveur de conversation permanente</strong></p></td>
<td><p>Configurez les utilisateurs :</p>
<ul>
<li><p>La stratégie d’accès à un serveur de conversation permanente doit être activée pour l’utilisateur. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur.</p></li>
<li><p>Configurer les paramètres</p></li>
</ul></td>
<td><p>L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuration du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Vous pouvez déployer un ou plusieurs pools de serveurs de conversation permanente. Nous prenons en charge plusieurs pools de serveurs de conversation permanente pour des raisons réglementaires selon lesquelles les données générées dans une région donnée doivent rester dans cette région. Par exemple, si vous déployez un pool de serveurs de conversation permanente à Chicago et un autre à Zurich pour vous conformer aux réglementations relatives aux données en Suisse, les utilisateurs peuvent se connecter à des salles dans les pools de serveurs de conversation permanente, à condition qu’ils disposent d’un accès.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

