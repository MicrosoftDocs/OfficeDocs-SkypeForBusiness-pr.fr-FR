---
title: 'Lync Server 2013 : processus de déploiement du groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Processus de déploiement du groupe Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-27_

Cette section fournit une vue d’ensemble des phases et des étapes nécessaires au déploiement de l’application Response Group.

### <a name="response-group-deployment-process"></a>Processus de déploiement de Response Group

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
<th>Autorisations</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Installer l’application Response Group</p></td>
<td><p>L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de voix entreprise dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installer les composants de Response Group</p></td>
<td><p>Applets de commande Lync Server, le panneau de configuration Lync Server, l’outil de configuration Response Group, la console de connexion et de déconnexion des agents et le service Web du client Response Group sont installés dans le cadre des services Web. Les services Web sont installés lorsque vous déployez un pool Enterprise Edition ou un serveur Standard Edition Server.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Microsoft Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Activer les utilisateurs pour Lync 2013 et voix entreprise</p></td>
<td><p>Autorisez les utilisateurs qui seront des agents pour Lync Server et voix entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En règle générale, les utilisateurs sont activés pour Lync Server pendant le déploiement du serveur Enterprise Edition ou Standard Edition. Les utilisateurs sont activés pour voix entreprise pendant le déploiement de voix entreprise.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activer les utilisateurs pour voix entreprise dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail</p></td>
<td><ol>
<li><p>Utilisez le panneau de configuration Lync Server ou Lync Server Management Shell pour effectuer les opérations suivantes :</p>
<ol>
<li><p>Créez et configurez des groupes d’agents.</p></li>
<li><p>Créez et configurez des files d’attente.</p></li>
</ol></li>
<li><p>Si vous le souhaitez, utilisez Lync Server Management Shell pour créer des heures ouvrées et des congés d’un groupe Response Group prédéfinis.</p></li>
<li><p>Utilisez l’outil de configuration Response Group ou Lync Server Management Shell pour créer des flux de travail (groupes de recherche ou flux d’appels de réponse vocale interactive), y compris les heures ouvrées et les congés des groupes Response Group personnalisés.</p>
<div>

> [!NOTE]  
> Vous pouvez accéder à l’outil de configuration Response Group via le panneau de configuration Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Créer des groupes d’agents Response Group Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Créer des files d’attente Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Module Définition des heures d’ouverture d’un groupe Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Module Définir les groupes de congés Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Création ou modification d’un flux de travail dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Facultatif) Personnaliser les paramètres au niveau de l’application</p></td>
<td><p>Utilisez Lync Server Management Shell pour personnaliser la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de l’appel d’invocation d’un agent et la configuration du contexte de l’appel.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestion des paramètres de groupe Response Group au niveau de l’application dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Facultatif) Déléguer la gestion des groupes Response Group</p></td>
<td><p>Attribuez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration des groupes Response Group. Les responsables des groupes Response Group peuvent ensuite configurer les groupes Response Group qui leur sont attribués.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier votre déploiement Response Group</p></td>
<td><p>Testez la réponse aux appels des workflows de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

