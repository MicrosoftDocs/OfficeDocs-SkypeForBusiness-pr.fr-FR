---
title: "Lync Server 2013 : Processus de dépl. pour l’intégration de la mes. un. loc."
TOCTitle: Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425737(v=OCS.15)
ms:contentKeyID: 49296656
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous voulez intégrer la messagerie unifiée Exchange à Lync Server 2013, vous devez effectuer les tâches présentées dans cette rubrique. Veillez également à prendre connaissance des bonnes pratiques en matière de planification et de déploiement présentées à la rubrique [Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Cette rubrique suppose que vous ayez déployé Lync Server 2013 avec un serveur de médiation colocalisé et activé les utilisateurs pour Lync Server 2013. Il n’est cependant pas nécessaire d’avoir effectué toutes les étapes de déploiement et de configuration pour activer Voix Entreprise. Ces étapes sont présentées à la section [Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

## Processus d’intégration de la messagerie unifiée

> [!IMPORTANT]  
> Il est important que vous vous mettiez en relation avec les administrateurs Exchange de votre organisation pour valider les tâches que chacun de vous sera amené à effectuer afin que l’intégration se déroule le mieux possible.


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
<th>Groupes et rôles requis</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Déployez l’un des éléments suivants :</p><ul><li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou le Service Pack le plus récent</p></li><li><p>Microsoft Exchange Server 2010 ou le Service Pack le plus récent</p></li><li><p>Microsoft Exchange Server 2013</p></li></ul></td>
<td><p>Si vous utilisez Microsoft Exchange Server 2013, installez les rôles Exchange Server suivants dans la même forêt que Lync Server 2013 ou dans une forêt différente :</p><ul><li><p>Accès client</p></li><li><p>Boîte aux lettres</p></li></ul>
<p>Si Microsoft Exchange Server 2013 et messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</p>
<p>Si vous utilisez Exchange 2010, installez les rôles Exchange Server suivants dans la même forêt que Lync Server 2013 ou dans une forêt différente :</p><ul><li><p>Messagerie unifiée</p></li><li><p>Transport Hub</p></li><li><p>Accès client</p></li><li><p>Boîte aux lettres</p></li></ul>
<p>Si Lync Server 2013 et messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</p></td>
<td><p>Administrateurs Enterprise (s’il s’agit du premier serveur Exchange Server de l’organisation)</p>
<p>- OU -</p>
<p>Administrateur d’organisation Exchange (s’il ne s’agit pas du premier serveur Exchange Server de l’organisation)</p></td>
<td><p>Reportez-vous à la documentation correspondant à votre serveur Exchange Server :</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentation de déploiement d’Exchange Server 2007 à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Documentation de déploiement d’Exchange Server 2010 ou Service Pack le plus récent à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 Planification et déploiement à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installez les certificats.</p></td>
<td><p>Téléchargez et installez les certificats pour chaque serveur messagerie unifiée Exchange à partir d’une autorité de certification racine approuvée. Les certificats sont requis pour que Mutual TLS (MTLS) fonctionne entre les serveurs exécutant messagerie unifiée Exchange et Lync Server 2013.</p></td>
<td><p>Administrateurs</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurer les certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Créez et configurez un nouveau plan de numérotation SIP pour messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur de messagerie unifiée Exchange, créez un plan de numérotation SIP basé sur les exigences de déploiement spécifiques à votre organisation.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou Service Pack le plus récent, reportez-vous à « Procédure de création d’un plan de numérotation SIP URI de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, reportez-vous à « Créer un plan de numérotation de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</p>
<p>Pour Exchange 2013, reportez-vous à « Messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurez les paramètres de sécurité du plan de numérotation SIP de la messagerie unifiée Exchange.</p></td>
<td><p>Pour chiffrer le trafic Voix Entreprise, configurez les paramètres de sécurité du plan de numérotation de la messagerie unifiée Exchange sur <strong>Sécurisé SIP</strong> ou <strong>Sécurisé</strong>. Cette étape est particulièrement importante si vous avez déployé ou envisagez de déployer des périphériques Lync Phone Edition dans votre environnement. Pour que les périphériques Lync Phone Edition fonctionnent dans un environnement intégrant la messagerie unifiée Exchange, les paramètres de chiffrement de Lync Server doivent être en adéquation avec les paramètres de sécurité du plan de numérotation de la messagerie unifiée Exchange. Pour plus d’informations, reportez-vous à la documentation de déploiement.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p>
<p>Pour Exchange 2007 SP1 ou Service Pack le plus récent, reportez-vous également à :</p>
<p>« Procédure de configuration des paramètres de sécurité sur un plan de numérotation de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</p>
<p></p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, reportez-vous également à :</p>
<p>« Configurer des paramètres de sécurité sur un plan de numérotation de messagerie » <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</p>
<p></p>
<p>Pour Exchange 2013, reportez-vous à « Messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ajoutez des serveurs de messagerie unifiée au plan de numération SIP de la messagerie unifiée Exchange.</p></td>
<td><p>Pour qu’un serveur de messagerie unifiée récemment installé puisse répondre aux appels entrants et les traiter, vous devez ajouter le serveur de messagerie unifiée au plan de numérotation de la messagerie unifiée. Dans ce cas, ajoutez le serveur au plan de numérotation SIP de la messagerie unifiée Exchange.</p></td>
<td><p>Administrateurs</p>
<p>Administrateurs Exchange Server</p></td>
<td><p>Pour Exchange 2007 SP1 ou Service Pack le plus récent, reportez-vous à « Procédure d’ajout d’un serveur de messagerie unifiée à un plan de numérotation » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, reportez-vous à « Afficher ou configurer les propriétés d’un serveur de messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</p>
<p></p>
<p>Pour Exchange 2013, reportez-vous à « Messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Attribuez des adresses SIP aux boîtes aux lettres.</p></td>
<td><p>Attribuez des adresses SIP aux utilisateurs de boîtes aux lettres Voix Entreprise qui utiliseront les fonctionnalités de messagerie unifiée Exchange.</p></td>
<td><p>Administrateur Lync Server 2013</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou Service Pack le plus récent, reportez-vous à « Procédures d’ajout, de suppression ou de modification d’une adresse SIP pour un utilisateur à extension messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, reportez-vous à « Modifier une adresse SIP pour un utilisateur à extension messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</p>
<p></p>
<p>Pour Exchange 2013, reportez-vous à « Messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Exécutez le script exchucutil.ps1.</p></td>
<td><p>Sur le serveur exécutant les services messagerie unifiée Exchange, ouvrez l’environnement de ligne de commande Exchange Management Shell et exécutez le script exchucutil.ps1, qui :</p><ul><li><p>accorde l’autorisation à Lync Server 2013 de lire les objets messagerie unifiée Exchange de services de domaine Active Directory, en particulier les plans de numérotation SIP créés lors de la tâche précédente ;</p></li><li><p>crée un objet passerelle IP de messagerie unifiée dans Active Directory pour chaque pool Lync Server 2013 Édition Entreprise ou serveur Édition Standard qui héberge des utilisateurs activés pour Voix Entreprise ;</p></li><li><p>crée un groupe de recherche messagerie unifiée Exchange pour chaque passerelle. L’identificateur pilote du groupe de recherche est le nom du plan de numérotation associé à la passerelle correspondante. S’il existe plusieurs plans de numérotation, ces identificateurs doivent être mappés un à un.</p></li></ul></td>
<td><p>Administrateur d’organisation Exchange</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez les plans de numérotation Lync Server 2013.</p></td>
<td><p>Dans le cas d’une intégration à Exchange 2007 SP1 ou Service Pack le plus récent, ou à Exchange 2010, créez un plan de numérotation Voix Entreprise dont le nom correspond au nom de domaine complet (FQDN) du plan de numérotation de la messagerie unifiée Exchange.</p>
<div>

> [!NOTE]  
> Cette opération devra être effectuée pour chaque plan de numérotation de la messagerie unifiée.
</div>
<p>Dans le cas d’une intégration à Exchange 2010 SP1, assurez-vous que des plans de numérotation Voix Entreprise adaptés ont été définis au niveau global/du site ou du pool.</p>
<div>

> [!NOTE]  
> Dans le cas d’une intégration à Exchange 2010 SP1, le nom du plan de numérotation Lync Server et celui du plan de numérotation SIP de la messagerie unifiée Exchange ne doivent pas obligatoirement correspondre.
</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configuration des plans de numérotation dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Exécutez l’outil d’intégration de la messagerie unifiée Exchange.</p></td>
<td><p>Sur Lync Server 2013, exécutez <strong>ocsumutil.exe</strong>. Cet outil :</p><ul><li><p>crée des objets Contact Accès abonné et Standard automatique ;</p></li><li><p>vérifie que le nom du plan de numérotation Voix Entreprise correspond au nom de domaine complet du plan de numérotation de la messagerie unifiée Exchange. Si vous exécutez Exchange 2010 SP1 ou une version plus récente, il n’est pas nécessaire que ces noms correspondent. Vous pouvez ignorer le message d’avertissement généré par l’outil.</p></li></ul>
<p>Cet outil analyse l’annuaire Active Directory et recherche les paramètres de messagerie unifiée Exchange. Il permet à l’administrateur Lync Server 2013 d’afficher, de créer et de modifier les objets Contact.</p></td>
<td><p>RTCUniversalServerAdmins <em>et</em> RTCUniversalUserAdmins</p>
<div>

> [!IMPORTANT]  
> Pour qu’ocsumutil.exe s’exécute correctement, l’utilisateur doit être membre de ces deux groupes.
</div>
<div>

> [!NOTE]  
> Pour créer des objets Contact, l’utilisateur qui exécute ocsumutil.exe doit disposer des autorisations d’accès appropriées à l’unité organisationnelle Active Directory dans laquelle les nouveaux objets de contact sont stockés. Cette autorisation peut être accordée en exécutant l’applet de commande <strong>Grant-CsOUPermission</strong>. Pour plus d’informations, reportez-vous à la documentation relative à Lync Server Management Shell.
</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Si nécessaire, procédez à d’autres étapes de configuration de Voix Entreprise.</p></td>
<td><p>Si vous n’avez pas déjà configuré les paramètres Voix Entreprise sur vos serveurs ou pour vos utilisateurs, effectuez une ou plusieurs des actions suivantes :</p><ul><li><p>déployez et configurez</p>
<p>les passerelles de réseau téléphonique commuté (RTC) et les serveurs de médiation</p></li><li><p>définissez les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires d’appels sortants ;</p></li><li><p>activez les utilisateurs pour Voix Entreprise ;</p></li><li><p>configurez éventuellement les plans de numérotation d’utilisateurs spécifiques.</p></li></ul>
<p>D’autres étapes de configuration peuvent être nécessaires selon les fonctionnalités Voix Entreprise que vous activez.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Reportez-vous aux rubriques des sections suivantes :</p><ul><li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013</a></p></li><li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de Voix Entreprise dans Lync Server 2013</a></p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Activez les utilisateurs Voix Entreprise pour la messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur de messagerie unifiée Exchange, vérifiez que la stratégie de boîte aux lettres de la messagerie unifiée a été créée et qu’un numéro de poste unique a été affecté à chaque utilisateur, puis activez les utilisateurs pour la messagerie unifiée.</p></td>
<td><p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou Service Pack le plus récent, reportez-vous à « Procédure d’activation de la messagerie unifiée pour un utilisateur » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, reportez-vous à « Activer la messagerie unifiée pour un utilisateur » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p></p>
<p>Pour Exchange 2013, reportez-vous à « Messagerie unifiée » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>

