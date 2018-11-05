---
title: 'Lync Server 2013 : Exigences d’adhésion à un groupe'
TOCTitle: Exigences d’adhésion à un groupe
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204623(v=OCS.15)
ms:contentKeyID: 49296061
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences d’adhésion à un groupe pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau suivant indique les groupes auxquels une personne doit appartenir pour installer, gérer Lync Server 2013, identifier ses problèmes et les résoudre.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 Exécutable</th>
<th>Appartenance au groupe requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong>  : fichier exécutable permettant de démarrer l’installation des outils d’administration Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory. Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).</p>

> [!TIP]  
> Vous pouvez également déléguer des autorisations de configuration aux utilisateurs ou groupes auxquels vous ne voulez pas accorder d’appartenance au groupe Administrateurs de domaine. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-granting-setup-permissions.md">Octroi d’autorisations de configuration dans Lync Server 2013</a> dans la documentation de déploiement.

</td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong>  : appelé par setup.exe, deploy.exe est chargé du déploiement des composants logiciels pour les rôles serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS). Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local). L’appartenance au groupe RtcUniversalReadOnlyAdmins est nécessaire pour lire le magasin central de gestion.</p>

> [!NOTE]  
> Si vous exécutez système d’exploitation Windows Vista ou système d’exploitation Windows 7, le Contrôle de compte d’utilisateur vous invitera à procéder à l’installation. Si vous avez ouvert la session avec un compte d’utilisateur standard, vous devrez demander à une personne membre du groupe Administrateurs local de vous fournir les informations d’identification requises qui vous seront demandées pour installer le logiciel avec le compte approprié.

</td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong>  : appelé par setup.exe, bootstrapper.exe est responsable du déploiement et de la configuration des rôles serveur.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe RTCUniversalServerAdmins pour exécuter Bootstrapper.exe. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS). Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong>  : interface utilisateur reposant sur un Assistant permettant de créer, examiner, ajuster et valider les topologies Lync Server 2013.</p></td>
<td><p>Membre du groupe Administrateurs local sur l’ordinateur à partir duquel le fichier exécutable est exécuté pour examiner la topologie. Membre du groupe RTCUniversalServerAdmins pour modifier les paramètres de configuration. Membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs de domaine ou membre du groupe RTCUniversalServerAdmins (uniquement si le groupe s’est vu accorder des autorisations de configuration déléguées) pour publier la topologie. Pour plus d’informations sur la délégation d’autorisations de configuration visant à permettre aux membres du groupe RTCUniversalServerAdmins de publier la topologie sans être membre du groupe Administrateurs de domaine, reportez-vous à <a href="lync-server-2013-granting-setup-permissions.md">Octroi d’autorisations de configuration dans Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong>  : interface graphique utilisateur web destinée à administrer Lync Server 2013.</p></td>
<td><p>Membre du groupe CsAdministrator d’un autre rôle RBAC (Contrôle d’’accès basé sur un rôler) auquel la tâche d’administration concernée est affectée. Panneau de configuration Lync Server 2013 applique les modifications de configuration en exécutant les commandes d’applet Lync Server 2013 Management Shell. Pour obtenir la liste des rôles prédéfinis et les commandes d’’applet que les membres peuvent exécuter, reportez-vous à <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentatio de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell.exe avec le module Lync Server 2013 chargé</strong>  : outil d’administration activable depuis une ligne de commande assorti d’applets de commande spécialement conçues pour administrer Lync Server 2013.</p></td>
<td><p>Membre du groupe CsAdministrator ou d’un autre rôle RBAC auquel l’applet de commande concernée est affectée. Pour obtenir la liste des rôles prédéfinis et des applets de commande que les membres sont autorisés à exécuter, reportez-vous à <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification.</p>
<p>Ou bien, membre d’un ou plusieurs des groupes suivants, en fonction de l’applet de commande :</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>

