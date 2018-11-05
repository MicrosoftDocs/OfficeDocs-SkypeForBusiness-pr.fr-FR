---
title: "Liste de vér. du dépl. pour la conférence rendez-vous dans Lync Server 2013"
TOCTitle: Liste de vérification du déploiement pour la conférence rendez-vous
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412726(v=OCS.15)
ms:contentKeyID: 49298351
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour la conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les composants requis pour la conférence rendez-vous sont déployés en même temps que la charge de travail de conférence. Avant de pouvoir configurer la conférence rendez-vous, vous devez déployer Voix Entreprise ou un serveur de médiation et une passerelle de réseau téléphonique commuté (RTC).

Toutes les étapes présentées dans le tableau ci-dessous doivent être réalisées pour que les utilisateurs puissent accéder à une conférence audio/vidéo via le réseau téléphonique commuté.

> [!NOTE]  
> Si vous effectuez une migration à partir d’Office Communications Server 2007 R2, vous devez appliquer les mises à jour les plus récentes à votre environnement Office Communications Server 2007 R2 avant de déployer la conférence rendez-vous.

### Processus de déploiement de la conférence rendez-vous

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
<td><p><strong>Créer une topologie qui intègre la charge de travail de conférence, y compris un serveur de médiation et une passerelle RTC, et déployer pool de serveurs frontaux ou serveur Standard Edition</strong></p></td>
<td><ol><li><p>Exécutez le Générateur de topologie pour configurer votre topologie. Lors de la configuration de la topologie, sélectionnez l’option de conférence rendez-vous.</p></li><li><p>Publiez la topologie et déployez le pool de serveurs frontaux ou serveur Standard Edition.</p></li><li><p>Si nécessaire, créez un serveur de médiation autonome et associez-le à une passerelle RTC.</p>
<div>

> [!NOTE]  
> Cette étape n’est nécessaire que si vous ne déployez pas Voix Entreprise et que vous ne colocalisez pas le serveur de médiation avec le serveur frontalEnterprise Edition ou le serveur Standard Edition. Si vous déployez Voix Entreprise, vous installez et configurez les serveurs de médiation et les passerelles RTC dans le cadre du déploiement de Voix Entreprise. Si vous colocalisez le serveur de médiation, vous installez et configurez le serveur de médiation dans le cadre du déploiement du pool de serveurs frontaux ou du serveur Standard Edition.
</div></li></ol></td>
<td><p>DomainAdmins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrateur</p></td>
<td><ul><li><p><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a></p></li><li><p>Pour créer un pool de serveurs de médiation autonome : <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</a></p></li></ul></td>
</tr>
<tr class="even">
<td><p><strong>Configurer des plans de numérotation</strong></p></td>
<td><p>Un plan de numérotation est un ensemble de règles de normalisation des numéros de téléphone qui convertit des numéros de téléphone composés depuis un emplacement spécifique à un format standard (E.164) unique à des fins d’autorisation téléphonique et de routage des appels. Le même numéro de téléphone composé depuis différents emplacements peut, en fonction des plans de numérotation concernés, être résolu en différents numéros E.164, conformément à chaque emplacement. Si vous déployez Voix Entreprise, vous devez configurer les plans de numérotation dans le cadre de ce déploiement et veiller à ce qu’ils correspondent à la conférence rendez-vous. Si vous ne déployez pas Voix Entreprise, vous devez configurer les plans de numérotation à des fins de conférence rendez-vous.</p>
<p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer des plans de numérotation comme suit :</p><ol><li><p>Créez un ou plusieurs plans de numérotation pour le routage des numéros de téléphone d’accès entrant.</p></li><li><p>Attribuez un plan de numérotation par défaut à chaque pool. Définissez la <strong>Région de la conférence rendez-vous</strong> sur l’emplacement géographique auquel le plan de numérotation s’applique. La région associe le plan de numérotation aux numéros d’accès entrant.</p></li></ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Vérifier qu’une région a été affectée aux plans de numérotation</strong></p></td>
<td><p>Exécutez les commandes d’applet <strong>Get-CsDialPlan</strong> et <strong>Set-CsDialPlan</strong> pour vous assurer qu’une région a été affectée à tous les plans de numérotation.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Vérification de l’affectation des régions aux plans de numérotation Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Vérifier ou modifier les conditions relatives au code confidentiel de l’utilisateur (PIN).</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour afficher ou modifier la <strong>Stratégie de code confidentiel</strong> de la conférence. Vous pouvez spécifier une longueur de code confidentiel minimale, un nombre maximal de tentatives d’ouverture de session, une expiration du code confidentiel et si des modèles communs sont autorisés.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Facultatif) Vérification des paramètres de stratégie de code confidentiel dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer une stratégie de conférence pour prendre en charge la conférence rendez-vous</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres <strong>Stratégie de conférence</strong> . Spécifiez si :</p><ul>
> <li><p>l’appel de conférence RTC est activé ;</p></li>
> <li><p>les utilisateurs peuvent inviter des participants anonymes ;</p></li>
> <li><p>des utilisateurs non authentifiés peuvent participer à une conférence en utilisant un appel sortant. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.</p></li></ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les numéros d’accès entrant</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer des numéros d’accès entrant que les utilisateurs composent pour participer à une conférence et spécifiez les régions chargées d’associer le numéro d’accès aux plans de numérotation appropriés. Les trois premiers numéros d’accès pour la région spécifiée par le plan de numérotation de l’organisateur sont inclus dans l’invitation à la conférence. Tous les numéros d’accès sont disponibles dans la page Paramètres de conférence rendez-vous.</p>
<div>

> [!NOTE]  
> Après avoir créé les numéros d’accès entrant, vous pouvez utiliser l’applet de commande <strong>Set-CsDialInConferencingAccessNumber</strong> pour modifier le nom complet des objets Contact Active Directory afin que les utilisateurs puissent identifier plus aisément le numéro d’accès correct.
</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Facultatif) Vérifier les paramètres de conférence rendez-vous</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Get-CsDialinConferencingAccessNumber</strong> pour rechercher des plans de numérotation présentant une région de conférence rendez-vous qui n’est pas utilisée par un numéro d’accès et les numéros d’accès sans affectation de région.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Facultatif) Vérification des paramètres de conférence rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Modifier le mappage des clés des commandes DTMF</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Set-CsDialinConferencingDtmfConfiguration</strong> pour modifier les clés utilisées pour les commandes DTMF (dual-tone multifrequency), que les participants peuvent employer pour contrôler les paramètres de conférence (tels que Muet/Désactiver Muet et Verrouiller/Déverrouiller).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Facultatif) Modifier le comportement des annonces d’entrée et de sortie d’une conférence</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Set-CsDialinConferencingConfiguration</strong> pour modifier le mode de fonctionnement des annonces lorsque les participants accèdent ou quittent une conférence.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Vérifier la conférence rendez-vous</strong></p></td>
<td><p>Utilisez l’applet de commande <strong>Test-CsDialInConferencing</strong> pour tester le fonctionnement des numéros d’accès pour le pool spécifié.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Facultatif) Vérification de la conférence rendez-vous dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Déployer le complément de réunion en ligne pour Lync 2013</strong></p></td>
<td><p>Déployez le complément de réunion en ligne pour Lync 2013 de sorte que les utilisateurs puissent planifier des conférences qui prennent en charge la conférence rendez-vous. Le complément de réunion en ligne pour Lync 2013 est installé automatiquement lorsque vous installez Lync 2013.</p></td>
<td><p>Administrateurs</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Déploiement du complément de réunion en ligne pour Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurer les paramètres des comptes d’utilisateurs</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer l’<strong>URI de ligne</strong> téléphonique comme numéro de téléphone normalisé unique (par exemple, tél. : +14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Recommandé) Configurer des répertoires de conférence</p></td>
<td><p>Utilisez l’applet de commande <strong>New-CsConferenceDirectory</strong> pour créer un répertoire de conférence tous les 999 utilisateurs dans le pool.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Configuration requise pour les conférences rendez-vous dans Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommandé) Création d’annuaires de conférences</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facultatif) Accueillir les utilisateurs à la conférence rendez-vous et définir le code confidentiel initial</strong></p></td>
<td><p>Utilisez le script <strong>Set-CsPinSendCAWelcomeMail</strong> pour définir les codes confidentiels initiaux des utilisateurs et envoyer un message électronique de bienvenue contenant le code confidentiel initial et un lien vers la page Paramètres de conférence rendez-vous.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Facultatif) Accueil des utilisateurs dans les conférences rendez-vous dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

