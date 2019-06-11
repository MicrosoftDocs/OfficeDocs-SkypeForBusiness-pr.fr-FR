---
title: 'Lync Server 2013 : Exigences d’adhésion à un groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aed308674cc334cfb8f3d4f214ce7388ae89fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Exigences d’adhésion à un groupe pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-05_

Le tableau suivant résume le ou les groupes auxquels une personne doit appartenir pour installer, gérer et dépanner Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exécutable Lync Server 2013</th>
<th>Appartenance au groupe requise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> -exécutable qui démarre l’installation des outils d’administration de Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel l’exécutable s’exécute. Membre du groupe utilisateurs de domaine pour lire les informations dans les services de domaine Active Directory (AD FS). Ce niveau d’autorisation est requis, car l’installation automatique des packages MSI requis sur l’ordinateur local nécessite des privilèges permettant la lecture et l’écriture des ressources de l’ordinateur local protégé telles que des répertoires de fichiers de programme et protégé Registre comme la ruche de l’ordinateur local.</p>
<div>

> [!TIP]  
> Vous pouvez également déléguer les autorisations de configuration pour les utilisateurs ou les groupes auxquels vous ne souhaitez pas être membre du groupe administrateurs de domaine. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</A> dans la documentation de déploiement.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy. exe</strong> (appelé par Setup. exe), deploy. exe, est responsable du déploiement des composants logiciels pour les rôles de serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel l’exécutable s’exécute. Membre du groupe utilisateurs de domaine pour lire des informations dans AD DS. Ce niveau d’autorisation est requis, car l’installation automatique des packages MSI requis sur l’ordinateur local nécessite des privilèges permettant la lecture et l’écriture des ressources de l’ordinateur local protégé telles que des répertoires de fichiers de programme et protégé Registre comme la ruche de l’ordinateur local. L’appartenance au groupe RtcUniversalReadOnlyAdmins est nécessaire pour lire le magasin central de gestion.</p>
<div>

> [!NOTE]  
> Si vous utilisez le système d’exploitation Windows Vista ou Windows 7, le contrôle de compte d’utilisateur vous invite à procéder à l’installation. Si vous avez ouvert une session avec un compte d’utilisateur standard, vous devez disposer d’une personne qui est membre du groupe Administrateurs local pour fournir des informations d’identification lorsque vous y êtes invité à fournir un compte disposant des autorisations d’installation du logiciel.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper. exe</strong> -appelé par Setup. exe, Bootstrapper. exe, est responsable du déploiement et de la configuration des rôles de serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel l’exécutable s’exécute. Membre du groupe RTCUniversalServerAdmins pour exécuter Bootstrapper. exe. Membre du groupe utilisateurs de domaine pour lire des informations dans AD DS. Ce niveau d’autorisation est requis, car l’installation automatique des packages MSI requis sur l’ordinateur local nécessite des privilèges permettant la lecture et l’écriture des ressources de l’ordinateur local protégé telles que des répertoires de fichiers de programme et protégé Registre comme la ruche de l’ordinateur local.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> -interface utilisateur pilotée par l’Assistant pour créer, afficher, ajuster et valider des topologies Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel l’exécutable est exécuté pour afficher la topologie. Membre du groupe RTCUniversalServerAdmins pour modifier les paramètres de configuration. Membre du groupe RTCUniversalServerAdmins et du groupe administrateurs de domaine, ou membre du groupe RTCUniversalServerAdmins (uniquement si le groupe a reçu les autorisations de configuration du délégué), pour publier la topologie. Pour plus d’informations sur la délégation d’autorisations de configuration afin de permettre aux membres du groupe RTCUniversalServerAdmins de publier la topologie sans être membre du groupe administrateurs de domaine, voir <a href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</a> dans le déploiement. accompagnant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> -interface utilisateur graphique basée sur le Web pour la gestion de Lync Server 2013.</p></td>
<td><p>Membre du groupe ou membre CsAdministrator d’un autre rôle de contrôle d’accès basé sur un rôle (RBAC) auquel la tâche administrative spécifique est affectée. Le panneau de configuration de Lync Server 2013 implémente les changements de configuration en exécutant les applets de commande Lync Server 2013 Management Shell. Pour obtenir la liste des rôles prédéfinis et des membres du cmdlet qui peuvent être exécutés, reportez-vous à la section <a href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe avec le module Lync Server 2013 chargé</strong> – outil d’administration de la ligne de commande avec des applets de commande spécifiques à la gestion de Lync Server 2013.</p></td>
<td><p>Membre du groupe ou membre de CsAdministrator d’un autre rôle RBAC auquel l’applet de cmdlet spécifique a été attribuée. Pour obtenir la liste des rôles prédéfinis et des membres du cmdlet qui peuvent être exécutés, reportez-vous à la section <a href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</a> dans la documentation de planification.</p>
<p>Ou membre d’un ou plusieurs des groupes suivants, en fonction de l’applet de commande:</p>
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

