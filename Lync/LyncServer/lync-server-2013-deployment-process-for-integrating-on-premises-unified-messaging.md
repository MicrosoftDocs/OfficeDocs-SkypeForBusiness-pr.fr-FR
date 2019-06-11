---
title: Processus de déploiement pour l’intégration de la messagerie unifiée locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-12-17_

Si vous souhaitez intégrer la messagerie unifiée Exchange avec Lync Server 2013, vous devez effectuer les tâches décrites dans cette rubrique. Veillez également à consulter les meilleures pratiques en matière de planification et de déploiement décrites dans [recommandations en matière d’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Cette rubrique part du principe que vous avez déployé Lync Server 2013 avec un serveur de médiation colocalisé et que vous avez activé les utilisateurs pour Lync Server 2013, mais pas nécessairement que vous avez effectué toutes les étapes de déploiement et de configuration pour activer Enterprise Voice, comme décrit dans la rubrique [déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

<div>

## <a name="unified-messaging-integration-process"></a>Procédure d’intégration de la messagerie unifiée

<div>


> [!IMPORTANT]
> Il est important que vous vous mettiez en relation avec les administrateurs Exchange de votre organisation pour valider les tâches que chacun de vous sera amené à effectuer afin que l’intégration se déroule le mieux possible.



</div>


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
<td><p>Déployez l’un des éléments suivants :</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou le dernier Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 ou le dernier Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Si vous utilisez Microsoft Exchange Server 2013, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013:</p>
<ul>
<li><p>Accès client</p></li>
<li><p>Boîte aux lettres</p></li>
</ul>
<p>Si Microsoft Exchange Server 2013 et la messagerie unifiée Exchange (UM) sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013.</p>
<p>Si vous utilisez Exchange 2010, installez les rôles Exchange Server suivants au sein d’une même forêt ou d’une autre forêt que Lync Server 2013:</p>
<ul>
<li><p>Messagerie unifiée</p></li>
<li><p>Transport Hub</p></li>
<li><p>Accès client</p></li>
<li><p>Boîte aux lettres</p></li>
</ul>
<p>Si Lync Server 2013 et la messagerie unifiée Exchange (UM) sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013.</p></td>
<td><p>Administrateurs Enterprise (s’il s’agit du premier serveur Exchange Server de l’organisation)</p>
<p>- OU -</p>
<p>Administrateur d’organisation Exchange (s’il ne s’agit pas du premier serveur Exchange Server de l’organisation)</p></td>
<td><p>Reportez-vous à la documentation correspondant à votre serveur Exchange Server :</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentation de déploiement d’Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 à l’adresse.</p>
</dd>
<dt><span></span></dt>
<dd><p>Documentation sur le déploiement d’Exchange Server 2010 ou de <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>la dernière version du Service Pack.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installez les certificats.</p></td>
<td><p>Téléchargez et installez des certificats pour chaque serveur de messagerie unifiée Exchange auprès d’une autorité de certification racine de confiance. Les certificats sont requis pour la sécurité de niveau de transport mutuel (MTLS) entre les serveurs exécutant Exchange UM et Lync Server 2013.</p></td>
<td><p>Administrateurs</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Créez et configurez un nouveau plan de numérotation SIP Exchange UM.</p></td>
<td><p>Sur le serveur de messagerie unifiée Exchange, créez un plan de numérotation SIP en fonction des exigences de déploiement spécifiques de votre organisation.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir Création d’un plan&quot; de numérotation URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2010 ou le dernier Service Pack, &quot;voir créer un plan&quot; de numérotation de messagerie unifiée à l’adresse. <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a></p>
<p>Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurer les paramètres de sécurité pour le plan de numérotation SIP de MU Exchange.</p></td>
<td><p>Pour chiffrer le trafic vocal d’une entreprise, configurez les paramètres de sécurité sur le plan de numérotation SIP Exchange UM en protocole <strong>SIP sécurisé</strong> ou <strong>sécurisé</strong>. Cette étape est particulièrement importante si vous avez déployé ou envisagez de déployer des appareils Lync Phone Edition dans votre environnement. Pour que les appareils Lync Phone Edition fonctionnent dans un environnement avec l’intégration à la messagerie unifiée Exchange, les paramètres de chiffrement de Lync Server doivent être alignés avec les paramètres de sécurité du plan de numérotation de messagerie unifiée Exchange. Pour plus d’informations, reportez-vous à la documentation de déploiement.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p>
<p>Pour Exchange 2007 SP1 ou le dernier Service Pack, voir également:</p>
<p>&quot;Comment configurer la sécurité sur un plan&quot; de numérotation de <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2010 ou le dernier Service Pack, reportez-vous également à :</p>
<p>&quot;Configurer la sécurité VoIP sur un plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de numérotation de messagerie unifiée.</p>
<p>Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ajoutez des serveurs de messagerie unifiée au plan de numérotation SIP Exchange UM.</p></td>
<td><p>Pour qu’un serveur de messagerie unifiée installé récemment puisse répondre aux appels entrants et les traiter, vous devez ajouter le serveur de messagerie unifiée au plan de numérotation de la messagerie unifiée. Dans le cas présent, ajoutez le serveur au plan de numérotation SIP Exchange UM.</p></td>
<td><p>Administrateurs</p>
<p>Administrateurs Exchange Server</p></td>
<td><p>Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir comment ajouter un serveur de messagerie unifiée à&quot; un <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>plan de numérotation à l’adresse.</p>
<p>Pour Exchange 2010 ou le dernier Service Pack, &quot;voir afficher ou configurer les propriétés d’un serveur&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Affectez des adresses SIP aux boîtes aux lettres.</p></td>
<td><p>Attribuez des adresses SIP aux boîtes aux lettres des utilisateurs d’Enterprise Voice qui utiliseront les fonctionnalités de messagerie unifiée Exchange.</p></td>
<td><p>Administrateur Lync Server 2013</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir comment ajouter, supprimer ou modifier une adresse SIP pour un utilisateur&quot; à <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>extension de messagerie unifiée.</p>
<p>Pour Exchange 2010 ou le dernier Service Pack, &quot;voir modifier une adresse SIP pour un utilisateur&quot; de MU à <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>l’adresse.</p>
<p>Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Exécutez le script exchucutil.ps1.</p></td>
<td><p>Sur le serveur exécutant les services de messagerie unifiée Exchange, ouvrez Exchange Management Shell et exécutez le script exchucutil. ps1, qui effectue les opérations suivantes:</p>
<ul>
<li><p>Octroie à Lync Server 2013 l’autorisation de lire les objets services de domaine Active Directory UM Exchange, notamment les plans de numérotation SIP créés dans la tâche précédente.</p></li>
<li><p>Crée un objet passerelle IP de messagerie unifiée dans Active Directory pour chaque pool Lync Server 2013 Enterprise Edition ou Standard Edition Server qui héberge les utilisateurs qui sont activés pour Enterprise Voice.</p></li>
<li><p>Crée un groupe de recherche UM Exchange pour chaque passerelle. L’identificateur pilote du groupe de recherche est le nom du plan de numérotation associé à la passerelle correspondante. S’il existe plusieurs plans de numérotation, ces identificateurs doivent être mappés un à un.</p></li>
</ul></td>
<td><p>Administrateur d’organisation Exchange</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les plans de numérotation Lync Server 2013.</p></td>
<td><p>Si vous intégrez une version d’Exchange 2007 SP1 ou le dernier Service Pack ou Exchange 2010, créez un nouveau plan de numérotation vocale d’entreprise avec un nom qui correspond au nom de domaine complet (FQDN) de votre plan de numérotation de messagerie unifiée.</p>



> [!NOTE]
> Cette opération devra être effectuée pour chaque plan de numérotation de la messagerie unifiée.


<p>S’il s’agit d’une intégration à Exchange 2010 SP1, assurez-vous que les plans de numérotation vocale globale, de niveau de site ou de pool d’entreprise appropriés ont été configurés.</p>



> [!NOTE]
> S’il s’agit d’une intégration à Exchange 2010 SP1, le plan de numérotation de Lync Server et les noms de plan de numérotation SIP de MU ne doivent pas nécessairement correspondre.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configuration des plans de numérotation dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Exécutez l’outil d’intégration de la messagerie unifiée Exchange.</p></td>
<td><p>Sur Lync Server 2013, exécutez <strong>ocsumutil. exe</strong>, qui:</p>
<ul>
<li><p>crée des objets Contact Accès abonné et Standard automatique ;</p></li>
<li><p>Vérifie qu’il existe un plan de numérotation vocale d’entreprise dont le nom correspond au nom de domaine complet du plan de numérotation de messagerie unifiée Exchange. Si vous exécutez Exchange 2010 SP1 ou une version ultérieure, les noms de plan de numérotation n’ont pas besoin d’être identiques et vous pouvez ignorer l’avertissement de l’outil à ce sujet.</p></li>
</ul>
<p>Cet outil fonctionne en analysant l’annuaire Active Directory pour les paramètres de messagerie unifiée Exchange et en permettant à l’administrateur de Lync Server 2013 d’afficher, de créer et de modifier des objets de contact.</p></td>
<td><p>RTCUniversalServerAdmins <em>et</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Pour qu’ocsumutil.exe soit exécuté correctement, l’utilisateur doit être membre de ces deux groupes.





> [!NOTE]
> Pour créer des objets Contact, l’utilisateur qui exécute ocsumutil.exe doit disposer des autorisations d’accès appropriées à l’unité organisationnelle Active Directory dans laquelle les nouveaux objets de contact sont stockés. Cette autorisation peut être accordée en exécutant l’applet de commande <STRONG>Grant-CsOUPermission</STRONG>. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Le cas échéant, effectuez d’autres étapes de configuration de voix entreprise.</p></td>
<td><p>Si vous n’avez pas encore configuré les paramètres voix entreprise sur vos serveurs ou vos utilisateurs, effectuez une ou plusieurs des actions suivantes:</p>
<ul>
<li><p>déployez et configurez</p>
<p>les passerelles de réseau téléphonique commuté (RTC) et les serveurs de médiation ;</p></li>
<li><p>définissez les stratégies vocales, les enregistrements d’utilisation RTC et les itinéraires d’appels sortants ;</p></li>
<li><p>activez les utilisateurs pour Voix Entreprise ;</p></li>
<li><p>configurez éventuellement les plans de numérotation d’utilisateurs spécifiques.</p></li>
</ul>
<p>D’autres étapes de configuration sont parfois nécessaires selon les fonctionnalités vocales d’entreprise que vous activez.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Reportez-vous aux rubriques des sections suivantes :</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement d’Enterprise Voice dans Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Activez les utilisateurs d’Enterprise Voice pour la messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur de messagerie unifiée Exchange, assurez-vous qu’une stratégie de boîte aux lettres de messagerie unifiée a été créée et que chaque utilisateur dispose d’une attribution de numéro d’extension unique, puis activez l’utilisateur pour la messagerie unifiée.</p></td>
<td><p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir activation d’un utilisateur pour la messagerie&quot; unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Pour Exchange 2010 ou le dernier Service Pack, &quot;voir Activer un utilisateur pour la&quot; messagerie <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>unifiée à l’adresse.</p>
<p>Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

