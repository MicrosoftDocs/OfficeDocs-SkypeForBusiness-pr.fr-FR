---
title: 'Lync Server 2013: comptes d’utilisateurs activés pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Comptes d’utilisateurs activés pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-04-18_

Les rubriques de cette section fournissent des procédures pas à pas permettant de configurer les paramètres utilisateur que vous pouvez effectuer à l’aide du panneau de configuration de Lync Server 2013.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer les utilisateurs membres du groupe administrateurs de domaine Active Directory. Pour les utilisateurs de Domain Admins, vous pouvez utiliser le panneau de configuration de Lync Server uniquement pour effectuer des opérations de recherche en lecture seule. Pour effectuer des opérations d’écriture sur des utilisateurs de Domain Admins (par exemple, activer ou désactiver pour le panneau de configuration de Lync Server, modifier les affectations de la liste ou des stratégies, paramètres de téléphonie, adresse SIP), vous devez utiliser les applets de commande Windows PowerShell lorsque vous êtes connecté en tant qu’utilisateur administrateurs de domaine. Pour plus d’informations sur l’utilisation des cmdlets Windows PowerShell pour gérer les utilisateurs, voir <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

Lors de l’exécution d’une tâche administrative Lync Server 2013 qui implique de rechercher un utilisateur ou de filtrer les résultats de la recherche utilisateur, il existe des propriétés utilisateur qui existent en tant qu’attributs dans les services de domaine Active Directory (AD FS), mais qui ne sont pas répliquées dans le catalogue global. tant que Microsoft Exchange Server n’est pas déployé. Microsoft Exchange, et non Lync Server, marque les attributs suivants pour la réplication dans le catalogue global lors de son installation:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informations utilisateur</th>
<th>Adresse et téléphone</th>
<th>Organisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initiales</p></td>
<td><p>Adresse postale</p>
<p>Pays/région</p>
<p>Radiomessagerie</p>
<p>DelrinaFax</p>
<p>Mobile</p></td>
<td><p>Titre</p>
<p>Elle</p>
<p>Service</p>
<p>Bureau</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Dans cette section

  - [Affichage d’informations sur les comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Cmdlets de gestion des utilisateurs dans Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Gestion des utilisateurs dans Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

