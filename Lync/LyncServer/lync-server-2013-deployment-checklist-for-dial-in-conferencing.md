---
title: Liste de vérification du déploiement de Lync Server 2013 pour les conférences rendez-vous
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1cbf5d732cbd30ac7d59e3bcedafadb0759ce2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Liste de vérification du déploiement pour les conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-03_

Les composants requis pour la conférence rendez-vous sont déployés en même temps que la charge de travail de conférence. Avant de pouvoir configurer la Conférence rendez-vous, vous devez déployer voix entreprise ou un serveur de médiation et une passerelle PSTN (réseau téléphonique commuté).

Toutes les étapes présentées dans le tableau ci-dessous doivent être réalisées pour que les utilisateurs puissent accéder à une conférence audio/vidéo via le réseau téléphonique commuté.

<div>


> [!NOTE]  
> Si vous effectuez une migration à partir d’Office Communications Server 2007 R2, vous devez appliquer les mises à jour les plus récentes à votre environnement Office Communications Server 2007 R2 avant de déployer la Conférence rendez-vous.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Processus de déploiement de la conférence rendez-vous

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
<td><p><strong>Créer une topologie qui inclut la charge de travail de conférence, y compris un serveur de médiation et une passerelle PSTN, et déployer le pool frontal ou le serveur Standard Edition</strong></p></td>
<td><ol>
<li><p>Exécutez le générateur de topologie pour configurer votre topologie. Lors de la configuration de la topologie, sélectionnez l’option de conférence rendez-vous.</p></li>
<li><p>Publiez la topologie et déployez le pool frontal ou le serveur Standard Edition.</p></li>
<li><p>Si nécessaire, créez un serveur de médiation autonome et associez-le à une passerelle RTC.</p>
<div>

> [!NOTE]  
> Cette étape n’est requise que si vous ne déployez pas voix entreprise et que vous ne colocaliser pas le serveur de médiation avec le serveur final Enterprise EditionFront ou le serveur Standard Edition. Si vous déployez voix entreprise, vous installez et configurez les serveurs de médiation et les passerelles PSTN dans le cadre du déploiement voix entreprise. Si vous colocaliser le serveur de médiation, vous installez et configurez le serveur de médiation dans le cadre du déploiement du pool frontal ou du serveur Standard Edition.


</div></li>
</ol></td>
<td><p>DomainAdmins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrateur</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Microsoft Lync Server 2013</a></p></li>
<li><p>Pour créer un pool de serveurs de médiation autonomes : <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configurer des plans de numérotation</strong></p></td>
<td><p>Un plan de numérotation est un ensemble de règles de normalisation des numéros de téléphone qui convertit des numéros de téléphone composés à partir d’un emplacement spécifique dans un format standard (E.164) unique à des fins d’autorisation téléphonique et de routage des appels. Le même numéro de téléphone composé depuis différents emplacements peut, en fonction des plans de numérotation respectifs, être résolu en différents numéros E.164, conformément à chaque emplacement. Si vous déployez voix entreprise, vous configurez des plans de numérotation dans le cadre de ce déploiement et vous devez vous assurer que les plans de numérotation s’intègrent également à la Conférence rendez-vous. Si vous ne déployez pas voix entreprise, vous devez configurer des plans de numérotation pour la Conférence rendez-vous.</p>
<p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les plans de numérotation comme suit :</p>
<ol>
<li><p>Créez un ou plusieurs plans de numérotation pour le routage des numéros de téléphone d’accès entrant.</p></li>
<li><p>Attribuez un plan de numérotation par défaut à chaque pool. Définissez la <strong>Région de la conférence rendez-vous</strong> sur l’emplacement géographique auquel le plan de numérotation s’applique. La région associe le plan de numérotation aux numéros d’accès entrant.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Vérifier que les plans de numérotation sont affectés à des régions</strong></p></td>
<td><p>Exécutez les cmdlets <strong>Get-CsDialPlan</strong> et <strong>Set-CsDialPlan</strong> pour vous assurer que tous les plans de numérotation ont une région affectée.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Vérifier que les plans de numérotation Lync Server 2013 ont des régions affectées</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Vérifier ou modifier les conditions relatives au code confidentiel de l’utilisateur (PIN).</strong></p></td>
<td><p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour afficher ou modifier la <strong>stratégie de code confidentiel</strong>de conférence. Vous pouvez spécifier une longueur de code confidentiel minimale, un nombre maximal de tentatives d’ouverture de session, une expiration du code confidentiel et si des modèles communs sont autorisés.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Module Vérifier les paramètres de stratégie de code confidentiel dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer une stratégie de conférence pour prendre en charge la conférence rendez‑vous</strong></p></td>
<td><p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de <strong>stratégie de conférence</strong> . Spécifiez si :</p>
<ul>
<li><p>l’appel de conférence PSTN est activé ;</p></li>
<li><p>les utilisateurs peuvent inviter des participants anonymes ;</p></li>
<li><p>des utilisateurs non authentifiés peuvent participer à une conférence en utilisant un appel sortant. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurer la stratégie de conférence pour les appels entrants dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les numéros d’accès entrant</strong></p></td>
<td><p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les numéros d’accès entrant que les utilisateurs appellent pour se connecter à une conférence, puis spécifiez les régions qui associent le numéro d’accès aux plans de numérotation appropriés. Les trois premiers numéros d’accès pour la région spécifiée par le plan de numérotation de l’organisateur sont inclus dans l’invitation à la conférence. Tous les numéros d’accès sont disponibles dans la page Paramètres de conférence rendez-vous.</p>
<div>

> [!NOTE]  
> Une fois que vous avez créé les numéros d’accès entrants, vous pouvez utiliser la cmdlet <STRONG>Set-applet csdialinconferencingaccessnumber</STRONG> pour modifier le nom d’affichage des objets contact Active Directory afin que les utilisateurs puissent identifier plus facilement le numéro d’accès correct.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurer les numéros d’accès aux conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Facultatif) Vérifier les paramètres de conférence rendez-vous</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Get-CsDialinConferencingAccessNumber</strong> pour rechercher des plans de numérotation présentant une région de conférence rendez-vous qui n’est pas utilisée par un numéro d’accès et les numéros d’accès sans affectation de région.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Module Vérifier les paramètres de conférence rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Modifier le mappage des clés des commandes DTMF</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Set-CsDialinConferencingDtmfConfiguration</strong> pour modifier les clés utilisées pour les commandes DTMF (dual-tone multifrequency), que les participants peuvent employer pour contrôler les paramètres de conférence (tels que Muet/Désactiver Muet et Verrouiller/Déverrouiller).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Module Modifier le mappage des clés pour les commandes DTMF dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Facultatif) Modifier le comportement des annonces d’entrée et de sortie d’une conférence</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Set-CsDialinConferencingConfiguration</strong> pour modifier le mode de fonctionnement des annonces lorsque les participants accèdent ou quittent une conférence.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Module Activer et désactiver les annonces de participation et de sortie de conférence dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Vérifier la conférence rendez-vous</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Test-CsDialInConferencing</strong> pour tester le fonctionnement des numéros d’accès pour le pool spécifié.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Module Vérifier les conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Déploiement du complément de réunion en ligne pour Lync 2013</strong></p></td>
<td><p>Déployez le complément de réunion en ligne pour Lync 2013 afin que les utilisateurs puissent planifier des conférences qui prennent en charge la Conférence rendez-vous. Le complément de réunion en ligne pour Lync 2013 est installé automatiquement lorsque vous installez Lync 2013.</p></td>
<td><p>Administrateurs</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Déploiement du complément de réunion en ligne pour Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les paramètres des comptes d’utilisateurs</strong></p></td>
<td><p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer l' <strong>URI de ligne</strong> téléphonique comme numéro de téléphone normalisé unique (par exemple, Tél : + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configurer les paramètres de compte d’utilisateur dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Recommandation Configurer les annuaires des conférences</p></td>
<td><p>La cmdlet <strong>New-CsConferenceDirectory</strong> permet de créer un annuaire de conférences pour chaque utilisateur de 999 dans le pool.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Exigences en matière de conférence rendez-vous dans Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recommandé) créer des annuaires de conférence</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Accueillir les utilisateurs à la conférence rendez-vous et définir le code confidentiel initial</strong></p></td>
<td><p>Utilisez le script <strong>Set-CsPinSendCAWelcomeMail</strong> pour définir les codes confidentiels initiaux des utilisateurs et envoyer un message électronique de bienvenue contenant le code confidentiel initial et un lien vers la page des paramètres de conférence rendez-vous.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Module Bienvenue les utilisateurs à la Conférence rendez-vous dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

