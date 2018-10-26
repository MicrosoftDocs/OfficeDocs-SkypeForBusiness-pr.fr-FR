---
title: "Lync Server 2013 : Liste de vérif. du déploiement pour le serv. de conv. Perm."
TOCTitle: Liste de vérification du déploiement pour le serveur de conversation permanente
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412851(v=OCS.15)
ms:contentKeyID: 49298542
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le déploiement de Lync Server 2013serveur de conversations permanentes nécessite de respecter l’ordre de la séquence de déploiement et d’effectuer toutes les étapes de déploiement nécessaires.

## Séquence de déploiement

Vous pouvez déployer un serveur de conversations permanentes après le déploiement de la topologie initiale, y compris au moins un pool de serveurs frontauxLync Server 2013 ou un serveur Standard EditionLync Server 2013. Cette rubrique indique la marche à suivre pour déployer un serveur de conversations permanentes en l’ajoutant à un déploiement existant.

## Processus de déploiement

Le tableau ci-dessous répertorie les étapes de base impliquées dans le déploiement d’un serveur de conversations permanentes et fournit des liens permettant d’obtenir plus d’informations.

### Processus de déploiement d’un serveur de conversations permanentes

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
<td><p>Sur le matériel conforme à la configuration système requise, installez ce qui suit :</p><ul><li><p>Sur les serveurs frontaux du serveur de conversations permanentes :</p></li></ul><ul><li><p>Un système d’exploitation conforme à la configuration système requise</p></li><li><p>Les logiciels prérequis pour les ordinateurs exécutant Lync Server 2013</p></li><li><p>SQL Server sur le serveur qui hébergera la base de données du serveur de conversations permanentes</p></li></ul>
<p>Si la conformité du serveur de conversations permanentes est requise :</p><ul><li><p>SQL Server sur le serveur qui hébergera la base de données de conformité du serveur de conversations permanentes</p></li></ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge le serveur de conversations permanentes (et, éventuellement, la conformité de la conversation permanente)</strong></p></td>
<td><p>Exécutez le Générateur de topologie pour ajouter un pool de serveurs de conversations permanentes à votre topologie :</p><ul><li><p>Ajouter les composants de serveur de conversations permanentes à la topologie</p></li><li><p>Créer une base de données SQL Server pour le magasin de serveur de conversations permanentes (et un serveur SQL Server de sauvegarde pour la récupération d’urgence)</p></li><li><p>Définir un nouveau magasin de fichiers Lync ou utiliser un magasin de fichiers Lync existant pour les fichiers de serveur de conversations permanentes</p></li><li><p>Associer le pool Lync Server 2013 qui peut effectuer le routage des demandes à ce pool de serveurs de conversations permanentes</p></li></ul>
<p>Si la conformité du conversation permanente est requise :</p><ul><li><p>Ajouter un magasin de conformité de la conversation permanente</p></li><li><p>Cliquer sur la case à cocher de définition du pool de serveurs de conversations permanentes pour activer la conformité</p></li><li><p>Publier la topologie</p></li></ul>
<p>Si vous installez un serveur de conversations permanentes sur l’édition Standard Edition, le nom de domaine complet (FQDN) du pool de serveurs de conversations permanentes doit correspondre au serveur Standard Edition, et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express présente sur le serveur Standard Edition</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins ainsi que l’utilisateur doivent également disposer d’autorisations de contrôle complètes (lecture/écriture/modification) sur le magasin de fichiers Lync pour les fichiers de serveur de conversations permanentes (afin que le générateur de topologie puisse configurer les DACL requises).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Déployer un serveur de conversations permanentes</strong></p></td>
<td><p>Exécutez le programme d’installation de Lync Server sur tous les ordinateurs exécutant le serveur de conversations permanentes. Le programme d’installation de serveur de conversations permanentes est intégré à l’Assistant Déploiement de Lync Server 2013 qui fournit les instructions suivantes :</p><ul><li><p>Déployer le magasin de gestion local</p></li><li><p>Installer les services du serveur de conversations permanentes</p></li><li><p>Demander et affecter des certificats</p></li><li><p>Exécuter et démarrer les services</p></li></ul></td>
<td><p>Un utilisateur membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement d’un serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="even">
<td><p><strong>Créer un administrateur conversation permanente</strong></p></td>
<td><p>Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.</p></td>
<td><p>Un utilisateur membre des administrateurs de domaines.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Ajout d’un administrateur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer le serveur de conversations permanentes</strong></p></td>
<td><p>Configurez les utilisateurs :</p><ul><li><p>L’utilisateur doit être autorisé par une stratégie à accéder au serveur de conversations permanentes. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur.</p></li><li><p>Configurer les paramètres</p></li></ul></td>
<td><p>L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuration du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Vous pouvez déployer un ou plusieurs pools de serveurs de conversations permanentes. Nous prenons en charge plusieurs pools de serveurs de conversations permanentes à des fins de contrôle au cours duquel les données générées dans une région données doivent rester dans cette région. Par exemple, si vous déployez un pool de serveurs de conversations permanentes à Chicago, et un autre à Zurich afin de respecter des règles applicables aux données en Suisse, les utilisateurs peuvent se connecter à des salles dans les deux pools de serveurs de conversations permanentes, à condition qu’ils y aient accès.
