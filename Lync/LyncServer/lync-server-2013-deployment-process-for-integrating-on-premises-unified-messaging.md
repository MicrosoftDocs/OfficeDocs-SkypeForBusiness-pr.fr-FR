---
title: Processus de déploiement pour l’intégration de la messagerie unifiée locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f8edade1ed4f0480d776e77eb66816c033a7e3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-17_

Si vous souhaitez intégrer la messagerie unifiée Exchange avec Lync Server 2013, vous devez effectuer les tâches décrites dans cette rubrique. Veillez également à consulter les meilleures pratiques de planification et de déploiement décrites dans la rubrique [recommandations pour l’intégration de la messagerie unifiée locale et Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Cette rubrique suppose que vous avez déployé Lync Server 2013 avec un serveur de médiation colocalisé et que vous avez activé les utilisateurs pour Lync Server 2013, mais pas nécessairement que vous ayez effectué toutes les étapes de déploiement et de configuration pour activer voix entreprise, comme décrit dans [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

<div>

## <a name="unified-messaging-integration-process"></a>Processus d’intégration de la messagerie unifiée

<div>


> [!IMPORTANT]
> Il est important de se concerter avec les administrateurs Exchange de votre organisation pour confirmer les tâches que chacun de vous effectuera afin de garantir une intégration sans problème.



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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack le plus récent</p></li>
<li><p>Microsoft Exchange Server 2010 ou Service Pack le plus récent</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Si vous utilisez Microsoft Exchange Server 2013, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013 :</p>
<ul>
<li><p>Accès client</p></li>
<li><p>Boîte aux lettres</p></li>
</ul>
<p>Si Microsoft Exchange Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</p>
<p>Si vous utilisez Exchange 2010, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013 :</p>
<ul>
<li><p>Messagerie unifiée</p></li>
<li><p>Transport Hub</p></li>
<li><p>Accès client</p></li>
<li><p>Boîte aux lettres</p></li>
</ul>
<p>Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</p></td>
<td><p>Administrateurs Enterprise (s’il s’agit du premier serveur Exchange Server de l’organisation)</p>
<p>OU</p>
<p>Administrateur d’organisation Exchange (s’il ne s’agit pas du premier serveur Exchange Server de l’organisation)</p></td>
<td><p>Voir la documentation correspondant à votre serveur Exchange Server :</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentation de déploiement d’Exchange Server <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 à l’adresse.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 ou la documentation de déploiement du service <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>Pack la plus récente à l’adresse.</p>
</dd>
<dt><span></span></dt>
<dd><p>Planification et déploiement de Microsoft Exchange Server 2013 <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>à l’adresse.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installez les certificats.</p></td>
<td><p>Téléchargez et installez des certificats pour chaque serveur de messagerie unifiée Exchange à partir d’une autorité de certification racine de confiance. Les certificats sont requis pour la sécurité MTLS (Mutual Transport Level Security) entre les serveurs exécutant la messagerie unifiée Exchange et Lync Server 2013.</p></td>
<td><p>Administrateurs</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Créez et configurez un nouveau plan de numérotation SIP de messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur de messagerie unifiée Exchange, créez un plan de numérotation SIP basé sur les exigences spécifiques de votre organisation en matière de déploiement.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le Service Pack le plus &quot;récent, consultez la rubrique How to Create a&quot; Unified Messaging SIP URI SIP dial plan at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</p>
<p>Pour Exchange 2010 ou le Service Pack le plus &quot;récent, consultez la rubrique&quot; créer <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>un plan de numérotation de messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurez les paramètres de sécurité pour le plan de numérotation SIP de messagerie unifiée Exchange.</p></td>
<td><p>Pour chiffrer le trafic voix entreprise, configurez les paramètres de sécurité du plan de numérotation SIP de messagerie unifiée Exchange en mode <strong>sécurisé SIP</strong> ou <strong>sécurisé</strong>. Cette étape est particulièrement importante si vous avez déployé ou si vous envisagez de déployer des appareils Lync Phone Edition dans votre environnement. Pour que les appareils Lync Phone Edition fonctionnent dans un environnement avec l’intégration de la messagerie unifiée Exchange, les paramètres de chiffrement de Lync Server doivent s’aligner sur les paramètres de sécurité du plan de numérotation de messagerie unifiée Exchange. Pour plus d’informations, voir la documentation de déploiement.</p></td>
<td><p>Administrateur d’organisation Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p>
<p>Pour Exchange 2007 SP1 ou le Service Pack le plus récent, voir également :</p>
<p>&quot;Comment configurer la sécurité sur un plan&quot; de numérotation de <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2010 ou Service Pack le plus récent, voir également :</p>
<p>&quot;Configurez la sécurité VoIP sur un&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>plan de numérotation de messagerie unifiée.</p>
<p>Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ajoutez des serveurs de messagerie unifiée au plan de numérotation SIP de messagerie unifiée Exchange.</p></td>
<td><p>Pour qu’un serveur de messagerie unifiée récemment installé puisse répondre aux appels entrants et les traiter, vous devez ajouter le serveur de messagerie unifiée au plan de numérotation de la messagerie unifiée. Dans ce cas, ajoutez le serveur au plan de numérotation SIP de messagerie unifiée Exchange.</p></td>
<td><p>Administrateurs</p>
<p>Administrateurs Exchange Server</p></td>
<td><p>Pour Exchange 2007 SP1 ou le Service Pack le plus &quot;récent, consultez la rubrique ajouter un serveur de messagerie&quot; unifiée à un plan de numérotation à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</p>
<p>Pour Exchange 2010 ou le Service Pack le plus &quot;récent, voir afficher ou configurer les propriétés d'&quot; un <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>serveur de messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Attribuez des adresses SIP aux boîtes aux lettres.</p></td>
<td><p>Attribuer des adresses SIP aux boîtes aux lettres des utilisateurs voix entreprise qui utiliseront les fonctionnalités de messagerie unifiée Exchange.</p></td>
<td><p>Administrateur Lync Server 2013</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le Service Pack le plus &quot;récent, voir comment ajouter, supprimer ou modifier une adresse SIP pour un utilisateur&quot; à extension messagerie <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>unifiée à l’adresse.</p>
<p>Pour Exchange 2010 ou le Service Pack le plus &quot;récent, consultez la rubrique modifier une adresse SIP pour&quot; un <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>utilisateur à extension messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Exécutez le script exchucutil.ps1.</p></td>
<td><p>Sur le serveur exécutant les services de messagerie unifiée Exchange, ouvrez l’environnement de commande Exchange Management Shell et exécutez le script exchucutil. ps1, qui effectue les opérations suivantes :</p>
<ul>
<li><p>Autorise Lync Server 2013 à lire les objets des services de domaine Active Directory de messagerie unifiée Exchange, en particulier les plans de numérotation SIP créés lors de la tâche précédente.</p></li>
<li><p>Crée un objet passerelle IP de messagerie unifiée dans Active Directory pour chaque pool Lync Server 2013 Enterprise Edition ou serveur Standard Edition qui héberge les utilisateurs activés pour voix entreprise.</p></li>
<li><p>Crée un groupement de postes de messagerie unifiée Exchange pour chaque passerelle. L’identificateur pilote du groupe de recherche est le nom du plan de numérotation associé à la passerelle correspondante. S’il existe plusieurs plans de numérotation, ces identificateurs doivent être mappés un à un.</p></li>
</ul></td>
<td><p>Administrateur d’organisation Exchange</p>
<p>Administrateur de destinataires Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez les plans de numérotation Lync Server 2013.</p></td>
<td><p>Si vous intégrez Exchange 2007 SP1 ou le Service Pack le plus récent, ou Exchange 2010, créez un nouveau plan de numérotation voix entreprise dont le nom correspond au nom de domaine complet (FQDN) du plan de numérotation de messagerie unifiée Exchange.</p>



> [!NOTE]
> Vous devrez effectuer cette opération pour chaque plan de numérotation de messagerie unifiée.


<p>Si vous intégrez Exchange 2010 SP1, assurez-vous que des plans de numérotation voix entreprise appropriés au niveau du site ou au niveau du pool ont été configurés.</p>



> [!NOTE]
> Si vous intégrez avec Exchange 2010 SP1, le plan de numérotation Lync Server et les noms de plan de numérotation SIP de la messagerie unifiée Exchange ne doivent pas nécessairement correspondre.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configuration des plans de numérotation dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Exécutez l’outil d’intégration de la messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur Lync Server 2013, exécutez <strong>ocsumutil. exe</strong>, qui :</p>
<ul>
<li><p>crée des objets Contact Accès abonné et Standard automatique ;</p></li>
<li><p>Vérifie qu’il existe un plan de numérotation voix entreprise dont le nom correspond au nom de domaine complet du plan de numérotation de messagerie unifiée Exchange. Si vous exécutez Exchange 2010 SP1 ou une version ultérieure, les noms de plan de numérotation n’ont pas besoin de correspondre, et vous pouvez ignorer l’avertissement de l’outil à ce sujet.</p></li>
</ul>
<p>Cet outil fonctionne en analysant Active Directory pour les paramètres de messagerie unifiée Exchange et en autorisant l’administrateur Lync Server 2013 à afficher, créer et modifier des objets contact.</p></td>
<td><p>RTCUniversalServerAdmins <em>et</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Pour qu’ocsumutil.exe s’exécute correctement, l’utilisateur doit être membre de ces deux groupes.





> [!NOTE]
> Pour créer des objets Contact, l’utilisateur qui exécute ocsumutil.exe doit disposer des autorisations d’accès appropriées à l’unité organisationnelle Active Directory dans laquelle les nouveaux objets de contact sont stockés. Cette autorisation peut être accordée en exécutant l’applet de commande <STRONG>Grant-CsOUPermission</STRONG> . Pour plus d’informations, voir la documentation Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurer Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Si nécessaire, procédez à d’autres étapes de configuration de Voix Entreprise.</p></td>
<td><p>Si vous n’avez pas déjà configuré les paramètres Voix Entreprise sur vos serveurs ou pour vos utilisateurs, effectuez une ou plusieurs des actions suivantes :</p>
<ul>
<li><p>Déployer et configurer</p>
<p>Passerelles PSTN (réseau téléphonique commuté) et serveurs de médiation</p></li>
<li><p>définissez les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires d’appels sortants ;</p></li>
<li><p>activez les utilisateurs pour Voix Entreprise ;</p></li>
<li><p>configurez éventuellement les plans de numérotation d’utilisateurs spécifiques.</p></li>
</ul>
<p>D’autres étapes de configuration peuvent être nécessaires selon les fonctionnalités Voix Entreprise que vous activez.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Voir les rubriques des sections suivantes :</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de voix entreprise dans Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Activez les utilisateurs voix entreprise pour la messagerie unifiée Exchange.</p></td>
<td><p>Sur le serveur de messagerie UNIFIÉe Exchange, vérifiez qu’une stratégie de boîte aux lettres de messagerie unifiée a été créée et que chaque utilisateur a une attribution unique de numéro de poste, puis activez l’utilisateur pour la messagerie unifiée.</p></td>
<td><p>Administrateur de destinataires Exchange</p></td>
<td><p>Pour Exchange 2007 SP1 ou le Service Pack le plus &quot;récent, consultez la rubrique How to Enable&quot; a <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>User for Unified Messaging à l’adresse.</p>
<p>Pour Exchange 2010 ou le Service Pack le plus &quot;récent, voir Activer un utilisateur&quot; pour <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>la messagerie unifiée à l’adresse.</p>
<p>Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

