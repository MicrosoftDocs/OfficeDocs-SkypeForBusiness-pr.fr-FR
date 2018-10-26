---
title: Comptes d’utilisateur activés pour Lync Server 2013
TOCTitle: Comptes d’utilisateur activés pour Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182543(v=OCS.15)
ms:contentKeyID: 49297888
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comptes d’utilisateur activés pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les rubriques de cette section comportent des procédures détaillées pour la configuration des paramètres utilisateur que vous pouvez effectuer à l’aide du Panneau de configuration Lync Server 2013.

> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le Panneau de configuration Lync Server pour gérer les utilisateurs membres du groupe Administrateurs du domaine Active Directory. Pour les utilisateurs administrateurs du domaine, vous pouvez utiliser le Panneau de configuration Lync Server uniquement pour effectuer des opérations de recherche en lecture seule. Pour effectuer des opérations d’écriture sur les utilisateurs administrateurs du domaine (par exemple pour les activer ou désactiver pour le Panneau de configuration Lync Server, pour modifier les attributions de pool ou de stratégie, les paramètres de téléphonie ou l’adresse SIP), vous devez utiliser les applets de commande Windows PowerShell tout en étant connecté en tant qu’utilisateur administrateur du domaine. Pour plus d’informations sur l’utilisation des applets de commande Windows PowerShell pour gérer les utilisateurs, voir <a href="lync-server-2013-lync-server-management-shell.md">Lync Server Management Shell</a>.

Lorsque vous effectuez une tâche d’administration Lync Server 2013 qui implique la recherche d’utilisateur ou le filtrage des résultats de recherche d’utilisateur, certaines propriétés utilisateur existent en tant qu’attributs dans les services de domaine Active Directory mais ne sont répliquées dans le catalogue global qu’une fois que Microsoft Exchange Server a été déployé. Microsoft Exchange, et non Lync Server, marque les attributs suivants pour la réplication dans le catalogue global lorsqu’il est installé :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informations utilisateur</th>
<th>Adresse et numéro de téléphone</th>
<th>Organisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initiales</p></td>
<td><p>Rue</p>
<p>Pays/région</p>
<p>Radiomessagerie</p>
<p>Télécopie</p>
<p>Mobile</p></td>
<td><p>Titre</p>
<p>Société</p>
<p>Service</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


## Dans cette section

  - [Affichage des informations sur les comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gestion de Voix Entreprise pour les utilisateurs](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modification des propriétés d’un compte d’utilisateur](lync-server-2013-modifying-user-account-properties.md)

  - [Gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

## Voir aussi

#### Concepts

[Cmdlets de gestion des utilisateurs](lync-server-2013-user-management-cmdlets.md)  

#### Autres ressources

[Gestion des utilisateurs dans Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)

