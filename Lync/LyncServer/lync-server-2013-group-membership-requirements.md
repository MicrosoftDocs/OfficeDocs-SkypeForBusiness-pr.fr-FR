---
title: 'Lync Server 2013 : conditions requises d’appartenance au groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041bba31a4c8225a4326e3409475210a46261a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498771"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a>Configuration requise pour l’appartenance à un groupe pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le tableau suivant résume le ou les groupes auxquels une personne doit appartenir afin d’installer, de gérer et de dépanner Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exécutable Lync Server 2013</th>
<th>Appartenance au groupe requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong> – exécutable qui démarre l’installation des outils d’administration Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe utilisateurs du domaine pour lire les informations dans les services de domaine Active Directory. Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).</p>
<div>

> [!TIP]  
> Vous pouvez également déléguer des autorisations de configuration aux utilisateurs ou groupes auxquels vous ne voulez pas accorder d’appartenance au groupe Administrateurs de domaine. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</A> dans la documentation de déploiement.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> : appelé par setup.exe, deploy.exe est chargé du déploiement des composants logiciels pour les rôles serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS). Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local). L’appartenance au groupe RtcUniversalReadOnlyAdmins est nécessaire pour lire le magasin central de gestion.</p>
<div>

> [!NOTE]  
> Si vous exécutez le système d’exploitation Windows Vista ou Windows 7, vous serez invité par le contrôle de compte d’utilisateur pour poursuivre l’installation. Si vous avez ouvert la session avec un compte d’utilisateur standard, vous devrez demander à une personne membre du groupe Administrateurs local de vous fournir les informations d’identification requises qui vous seront demandées pour installer le logiciel avec le compte approprié.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> : appelé par setup.exe, bootstrapper.exe est responsable du déploiement et de la configuration des rôles serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe RTCUniversalServerAdmins pour exécuter Bootstrapper.exe. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS). Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).
</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – interface utilisateur basée sur l’Assistant pour créer, afficher, ajuster et valider des topologies Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel le fichier exécutable est exécuté pour examiner la topologie. Membre du groupe RTCUniversalServerAdmins pour modifier les paramètres de configuration. Membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs de domaine ou membre du groupe RTCUniversalServerAdmins (uniquement si le groupe s’est vu accorder des autorisations de configuration déléguées) pour publier la topologie. Pour plus d’informations sur la délégation d’autorisations de configuration pour permettre aux membres du groupe RTCUniversalServerAdmins de publier la topologie sans être membres du groupe administrateurs du domaine, consultez la rubrique <a href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> : interface utilisateur Web basée sur le Web pour la gestion de Lync Server 2013.</p></td>
<td><p>Membre du groupe CsAdministrator ou membre d’un autre rôle RBAC (contrôle d’accès basé sur un rôle) auquel la tâche d’administration spécifique est affectée. Le panneau de configuration Lync Server 2013 implémente les modifications de configuration en exécutant les applets de commande de Lync Server 2013 Management Shell. Pour obtenir la liste des rôles prédéfinis et les membres des cmdlets autorisés à s’exécuter, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell.exe avec le module Lync Server 2013 chargé</strong> – outil d’administration en ligne de commande avec cmdlets spécifique à la gestion de Lync Server 2013.</p></td>
<td><p>Membre du groupe CsAdministrator ou d’un autre rôle RBAC auquel l’applet de commande spécifique a été affectée. Pour obtenir la liste des rôles prédéfinis et les membres des cmdlets autorisés à s’exécuter, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> dans la documentation de planification.</p>
<p>Ou bien, membre d’un ou plusieurs des groupes suivants, en fonction de l’applet de commande :</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

