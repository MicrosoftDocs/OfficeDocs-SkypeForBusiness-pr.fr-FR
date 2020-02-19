---
title: 'Lync Server 2013 : comptes d’utilisateur activés pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3545ba99f55e0fa11bcee09791d1a618b92c3d78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Comptes d’utilisateurs activés pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-18_

Les rubriques de cette section comportent des procédures détaillées pour la configuration des paramètres utilisateur que vous pouvez effectuer à l’aide du panneau de configuration Lync Server 2013.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour gérer les utilisateurs membres du groupe administrateurs du domaine Active Directory. Pour les utilisateurs administrateurs du domaine, vous pouvez utiliser le panneau de configuration Lync Server uniquement pour effectuer des opérations de recherche en lecture seule. Pour effectuer des opérations d’écriture sur les utilisateurs des administrateurs du domaine (par exemple, activer ou désactiver le panneau de configuration de Lync Server, modifier les attributions de stratégie ou de pool, les paramètres de téléphonie, l’adresse SIP), vous devez utiliser les applets de commande Windows PowerShell lorsque vous êtes connecté en tant qu’utilisateur administrateurs du domaine. Pour plus d’informations sur l’utilisation des applets de commande Windows PowerShell pour gérer les utilisateurs, voir <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

Lorsque vous effectuez une tâche administrative Lync Server 2013 qui implique la recherche d’un utilisateur ou le filtrage des résultats de la recherche utilisateur, il existe des propriétés utilisateur qui existent en tant qu’attributs dans les services de domaine Active Directory, mais qui ne sont pas répliquées dans le catalogue global. tant que Microsoft Exchange Server n’est pas déployé. Microsoft Exchange, et non Lync Server, marque les attributs suivants pour la réplication dans le catalogue global lors de l’installation :


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
<p>Alphanumérique</p>
<p>Télécopie</p>
<p>Mobile</p></td>
<td><p>Titre</p>
<p>Company</p>
<p>Service</p>
<p>Bureau</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Dans cette section

  - [Affichage des informations sur les comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Gérer la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Applets de commande de gestion des utilisateurs dans Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Gestion des utilisateurs dans Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

