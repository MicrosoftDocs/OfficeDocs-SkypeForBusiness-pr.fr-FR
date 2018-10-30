---
title: 'Lync Server 2013 : Processus de déploiement de Response Group'
TOCTitle: Processus de déploiement de Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205270(v=OCS.15)
ms:contentKeyID: 49298935
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement de Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les phases et la procédure pour déployer l’application Response Group.

### Processus de déploiement du groupe Response Group

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
<td><p>Installer l’application Response Group</p></td>
<td><p>L’application Response Group est installée et activée par défaut quand vous déployez Voix Entreprise.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de Voix Entreprise dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installer les composants pour Response Group</p></td>
<td><p>Les applets de commande Lync Server, le Panneau de configuration Lync Server, l’outil de configuration Response Group, la console de connexion et de déconnexion des agents ainsi que le service web du client Response Group sont installés dans les services web, c’est-à-dire quand vous déployez un pool Enterprise Edition ou un serveur Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Activer les utilisateurs pour Lync 2013 et Voix Entreprise</p></td>
<td><p>Activer les utilisateurs qui seront des agents pour Lync Server et Voix Entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En règle générale, les utilisateurs sont activés pour Lync Server lors du déploiement de Enterprise Edition ou du serveur Standard Edition. Les utilisateurs sont activés pour Voix Entreprise lors du déploiement de Voix Entreprise.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail</p></td>
<td><ol>
<li><p>Utilisez le Panneau de configuration Lync Server ou Lync Server Management Shell pour effectuer les opérations suivantes :</p>
<ol>
<li><p>Créez et configurez des groupes d’agents.</p></li>
<li><p>Créez et configurez des files d’attente.</p></li>
</ol></li>
<li><p>De manière facultative, utilisez Lync Server Management Shell pour créer des heures ouvrées et des congés pour un groupe Response Group prédéfini.</p></li>
<li><p>Utilisez l’outil de configuration Response Group ou Lync Server Management Shell pour créer des flux de travail (flux de groupes de recherche ou d’appels de réponse vocale interactive [IVR]), dont des heures ouvrées et des congés pour un groupe Response Group personnalisé.</p>

> [!NOTE]  
> Vous pouvez accéder à l’outil de configuration Response Group via le Panneau de configuration Lync Server.

</li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Création des groupes d’agents Response Group Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Création des files d’attente Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Facultatif) Définition des heures ouvrées des groupes Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Facultatif) Définition des groupes de congés des groupes Response Group dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Création ou modification d’un workflow dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Facultatif) Personnaliser les paramètres au niveau de l’application</p></td>
<td><p>Utilisez Lync Server Management Shell pour personnaliser la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de la reprise d’appel parqué des agents ainsi que la configuration du contexte de l’appel.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestion des paramètres de Response Group au niveau de l’application dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Facultatif) Déléguer la gestion des groupes Response Group</p></td>
<td><p>Pour déléguer la configuration de groupes Response Group, attribuez aux utilisateurs le rôle CsResponseGroupManager. Les gestionnaires Response Group peuvent ensuite configurer les groupes Response Group qui leur ont été affectés.</p></td>
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

