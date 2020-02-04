---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour le serveur de conversation permanente'
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
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Le déploiement de Lync Server 2013, de chat permanent serveur nécessite que vous le déployiez dans l’ordre approprié et que vous ayez effectué toutes les étapes de déploiement requises.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

Vous pouvez déployer le serveur de chat permanent après le déploiement de votre topologie initiale, y compris au moins un serveur Lync Server 2013, un pool frontal ou un serveur Lync Server 2013, Standard Edition Server. Cette rubrique décrit la procédure de déploiement d’un serveur de chat permanent en l’ajoutant à un déploiement existant.

</div>

<div>

## <a name="deployment-process"></a>Processus de déploiement

Le tableau suivant répertorie les étapes de base de déploiement d’un serveur de conversation permanent et fournit des liens pour plus d’informations.

### <a name="persistent-chat-server-deployment-process"></a>Processus de déploiement d’un serveur de chat permanent

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
<li><p>Sur les serveurs front-end serveur Chat permanent :</p></li>
</ul>
<ul>
<li><p>Un système d’exploitation conforme à la configuration système requise</p></li>
<li><p>Configuration logicielle requise pour les ordinateurs exécutant Lync Server 2013</p></li>
<li><p>Serveur SQL Server sur le serveur qui héberge la base de données de serveur Chat permanent</p></li>
</ul>
<p>Si la conformité du serveur Chat permanent est requise :</p>
<ul>
<li><p>Serveur SQL Server sur le serveur qui héberge la base de données de compatibilité serveur Chat permanent</p></li>
</ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Support du logiciel serveur et de l’infrastructure dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Configuration requise pour le serveur de chat permanent dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge le serveur de chat permanent (et éventuellement la conformité avec la conversation permanente)</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter un pool de serveurs de chat permanent à votre topologie :</p>
<ul>
<li><p>Ajouter des composants serveur de chat permanent à la topologie</p></li>
<li><p>Créer une base de données SQL Server pour le magasin serveur Chat permanent (et un serveur SQL de sauvegarde pour la récupération d’urgence)</p></li>
<li><p>Définir un nouveau magasin de fichiers Lync ou utiliser un magasin de fichiers Lync existant pour les fichiers du serveur de chat permanent</p></li>
<li><p>Associez le pool Lync Server 2013 qui peut acheminer les demandes vers ce pool de serveurs de chat permanent.</p></li>
</ul>
<p>Si la conformité de conversation permanente est requise :</p>
<ul>
<li><p>Ajouter un magasin de conformité des conversations permanentes</p></li>
<li><p>Cliquez sur la case à cocher de la définition de pool de serveurs de conversation permanente pour activer la conformité</p></li>
<li><p>Publication de la topologie</p></li>
</ul>
<p>Si vous installez le serveur Chat permanent sur l’édition standard, le nom de domaine complet (FQDN) du pool de serveurs de chat permanent doit correspondre au serveur Standard Edition Server, et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express sur le standard. Serveur édition</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et l’utilisateur doit également disposer des autorisations de contrôle total (lecture/écriture/modification) sur le magasin de fichiers Lync pour les fichiers du serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les DACL requis).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur de chat permanent à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Déployer un serveur de conversation permanente</strong></p></td>
<td><p>Exécutez le programme d’installation de Lync Server sur tous les ordinateurs exécutant la fonction de chat permanent serveur. La configuration du serveur de chat permanent est intégrée à l’Assistant Déploiement de Lync Server 2013, qui fournit les instructions suivantes :</p>
<ul>
<li><p>Déployer le magasin de gestion local</p></li>
<li><p>Installer les services serveur de chat permanent</p></li>
<li><p>Demander et affecter des certificats</p></li>
<li><p>Exécuter et démarrer les services</p></li>
</ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement d’un serveur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p><strong>Créer un administrateur de conversation permanente</strong></p></td>
<td><p>Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.</p></td>
<td><p>Un utilisateur membre des administrateurs de domaines.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Ajouter un administrateur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configuration du serveur de conversation permanente</strong></p></td>
<td><p>Configurez les utilisateurs :</p>
<ul>
<li><p>La stratégie doit être activée pour permettre à l’utilisateur d’accéder au serveur de chat permanent. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur.</p></li>
<li><p>Configurer les paramètres</p></li>
</ul></td>
<td><p>L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuration du serveur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Vous pouvez déployer un ou plusieurs pools de serveurs de chat permanent. Nous prenons en charge plusieurs pools de serveurs de chat permanent pour des raisons réglementaires dans lesquelles les données générées dans une région donnée doivent rester dans cette région. Par exemple, si vous déployez un pool de serveurs de chat permanent à Chicago et un autre sur Zurich pour se conformer aux réglementations relatives aux données en Suisse, les utilisateurs peuvent se connecter aux salles dans les pools de serveurs de chat permanent, à condition qu’ils y aient accès.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

