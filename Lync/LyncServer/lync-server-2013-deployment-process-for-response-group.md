---
title: 'Lync Server 2013 : processus de déploiement pour Response Group'
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
ms.openlocfilehash: 2eb302f57cd335decf3523c271ff464f2954db86
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Processus de déploiement pour Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-27_

Cette section fournit une vue d’ensemble des phases et étapes du déploiement de l’application Response Group.

### <a name="response-group-deployment-process"></a>Procédure de déploiement du groupe Response Group

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
<td><p>L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement d’Enterprise Voice dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installer des composants pour Response Group</p></td>
<td><p>Les applets de commande Lync Server, le panneau de configuration de Lync Server, l’outil de configuration de Response Group, l’outil de connexion des agents et la console de connexion et le service Web du client de groupe de réponse sont installés dans le cadre de services Web. Les services Web sont installés lorsque vous déployez un pool Enterprise Edition ou un serveur Standard Edition Server.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Activer les utilisateurs pour Lync 2013 et voix entreprise</p></td>
<td><p>Activez les utilisateurs qui seront agents de Lync Server et de voix entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En général, les utilisateurs sont activés pour Lync Server lors du déploiement Enterprise Edition ou Standard Edition Server. Les utilisateurs sont activés pour voix entreprise pendant le déploiement de voix entreprise.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail</p></td>
<td><ol>
<li><p>Utilisez le panneau de configuration de Lync Server ou Lync Server Management Shell pour effectuer les opérations suivantes :</p>
<ol>
<li><p>Créez et configurez des groupes d’agents.</p></li>
<li><p>Créez et configurez des files d’attente.</p></li>
</ol></li>
<li><p>Vous pouvez également utiliser Lync Server Management Shell pour créer des heures de travail et des jours fériés prédéfinis.</p></li>
<li><p>Utilisez l’outil de configuration de Response Group ou Lync Server Management Shell pour créer des flux de travail (groupes de recherche ou flux de réponse vocale interactifs), y compris des heures et des jours fériés de groupe de réponse personnalisés.</p>
<div>

> [!NOTE]  
> Vous pouvez accéder à l’outil de configuration de Response Group par le biais du panneau de configuration de Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Création des groupes d’agents Response Group Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Création des files d’attente Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Créer ou modifier un flux de travail dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Facultatif) Personnaliser les paramètres au niveau de l’application</p></td>
<td><p>Utilisez Lync Server Management Shell pour personnaliser la configuration par défaut de Music-Holding, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestion des paramètres du groupe de réponses au niveau de l’application dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Facultatif) Déléguer la gestion des groupes Response Group</p></td>
<td><p>Affectez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration de Response groups. Les responsables de groupe de réponse peuvent alors configurer les groupes de réponse qui leur sont attribués.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier votre déploiement Response Group</p></td>
<td><p>Testez la réponse aux appels des flux de travail de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.</p></td>
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

