---
title: Présentation de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Présentation de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

Lync Server 2013 et son logiciel client, comme Lync 2013, permettent aux utilisateurs de se connecter de nouvelles manières et de rester connectés, quel que soit leur emplacement physique. Lync et Lync Server s’associent aux différentes manières dont les personnes communiquent dans une seule interface client, sont déployées en tant que plateforme unifiée et sont administrées par le biais d’une infrastructure de gestion unique.

Ce tableau et les sections suivantes décrivent les principaux Jeux de fonctionnalités, ou *charges de travail*, que Lync Server fournit pour vos utilisateurs.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Travail</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>La messagerie instantanée et la présence permettent aux utilisateurs de les retrouver et de communiquer efficacement.</p>
<p>La messagerie instantanée fournit une plate-forme de messagerie instantanée avec l’historique des conversations et prend en charge la connectivité de messagerie instantanée publique aux utilisateurs de réseaux de messagerie instantanée publics comme MSN/Windows Live, Yahoo!, AOL et Google Talk.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>


</div>
<p>La présence établit et affiche la disponibilité et la volonté personnelles d’un utilisateur pour communiquer par le biais de l’utilisation d’États courants tels que <strong>disponible</strong> ou <strong>occupé</strong>, ainsi que d’États plus détaillés, par exemple, <strong>revenir en arrière</strong> et <strong>ne pas déranger </strong>. Ces informations de présence complètes permettent aux utilisateurs d’apporter immédiatement des choix de communication efficaces.</p></td>
</tr>
<tr class="even">
<td><p>Conférence</p></td>
<td><p>Lync Server inclut la prise en charge de la Conférence par messagerie instantanée, de l’audioconférence, des conférences Web, des conférences vidéo et du partage d’applications pour les réunions planifiées et impromptues. Chacun de ces types de réunion est pris en charge avec un client unique. Lync Server prend également en charge la Conférence rendez-vous pour que les utilisateurs de téléphones RTC (réseau téléphonique commuté) puissent participer à la partie audio des conférences.</p>
<p>Les conférences peuvent changer et augmenter de manière transparente en temps réel. Par exemple, une seule conférence peut démarrer sous la forme de messages instantanés entre quelques utilisateurs et être transvisée en conférence audio avec le partage du bureau et un grand public plus facilement, sans interruption du flux de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>Voix Entreprise</p></td>
<td><p><em>Enterprise Voice</em> est l’offre VoIP (Voice over Internet Protocol) sur Lync Server. Il offre une option de voix permettant d’améliorer ou de remplacer les systèmes PBX (Private Branch Exchange) traditionnels. Outre les fonctionnalités de téléphonie complètes d’un PBX IP, Enterprise Voice est intégré aux fonctionnalités de présence, de messagerie instantanée, de collaboration et de réunions enrichies. Les fonctionnalités telles que la réponse aux appels, la mise en attente, la reprise, le transfert, le renvoi et le détournement sont prises en charge directement, tandis que les touches d’accès rapide personnalisées sont remplacées par les messages instantanés.</p>
<p>Voix entreprise prend en charge la haute disponibilité via le contrôle d’admission des appels (CAC), la survie de succursale et les options étendues de résilience de données.</p></td>
</tr>
<tr class="even">
<td><p>Support pour les utilisateurs distants</p></td>
<td><p>Vous pouvez fournir des fonctionnalités complètes de Lync Server pour les utilisateurs qui se trouvent en dehors des pare-feu de votre organisation en déployant des serveurs appelés <em>serveurs Edge</em> pour proposer une connexion à ces utilisateurs distants. Ces utilisateurs distants peuvent se connecter aux conférences en utilisant un ordinateur personnel sur lequel Lync 2013 est installé, le téléphone ou une interface Web.</p>
<p>Le déploiement de serveurs Edge vous permet également de <em>fédérer</em> avec les organisations partenaires ou fournisseurs. Une relation fédérée permet aux utilisateurs de placer des utilisateurs fédérés dans leurs listes de contacts, d’échanger des informations de présence et de messages instantanés avec ces utilisateurs, et de les inviter à des appels audio, des appels vidéo et des conférences.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge du client mobile</p></td>
<td><p>De plus, avec les services de mobilité Lync Server, vos utilisateurs peuvent accéder à la fonctionnalité Lync en utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia, et effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage des contacts. et affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler par le biais d’un numéro de téléphone, de la messagerie vocale et d’appels manqués. Les notifications de transmission sont également prises en charge pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan.</p></td>
</tr>
<tr class="even">
<td><p>Intégration avec d’autres produits</p></td>
<td><p>Lync Server est intégré à d’autres produits pour offrir des avantages supplémentaires aux utilisateurs et aux administrateurs.</p>
<p>Les outils de réunion sont intégrés à Outlook pour permettre aux organisateurs de planifier une réunion ou de lancer une conférence impromptue d’un simple clic et de la rendre plus facile pour les participants.</p>
<p>Les informations de présence sont intégrées dans Outlook et SharePoint.</p>
<p>La messagerie unifiée Exchange fournit plusieurs fonctionnalités d’intégration. Les utilisateurs peuvent voir s’ils ont un nouveau message vocal dans Lync Server. Il peut cliquer sur un bouton de lecture dans le message Outlook pour écouter la messagerie vocale, ou afficher une transcription de la messagerie vocale dans le message de notification.</p>
<p>Par ailleurs, l’exécution de Lync Server 2013 avec Exchange 2013 offre plusieurs nouvelles fonctionnalités, telles qu’un magasin de contacts unifié, qui est accessible aux clients de ces deux produits, ainsi que des photos de haute résolution pour les contacts stockés dans la base de données Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Déploiement simple</p></td>
<td><p>Pour vous aider à planifier et déployer vos serveurs et clients, Lync Server fournit le générateur de topologie.</p>
<p>Le générateur de topologie est un composant d’installation de Lync Server. Le générateur de topologie vous permet de créer, d’ajuster et de publier votre topologie planifiée. Il valide également votre topologie avant de commencer les installations serveur. Lorsque vous installez Lync Server sur des serveurs individuels, le programme d’installation déploie le serveur conformément aux instructions de la topologie.</p></td>
</tr>
<tr class="even">
<td><p>Gestion simple</p></td>
<td><p>Après le déploiement de Lync Server, les outils de gestion puissants et rationalisés suivants sont proposés:</p>
<ul>
<li><p>Gestion centralisée de la configuration, qui vous permet de gérer les modifications de manière centralisée et de les répliquer rapidement dans l’ensemble du déploiement.</p></li>
<li><p>Panneau de configuration de Lync Server, interface utilisateur Web pour administrateurs. Grâce à cette interface utilisateur basée sur le Web, les administrateurs du serveur Lync peuvent gérer leurs systèmes depuis n’importe où sur le réseau d’entreprise, sans qu’aucun logiciel de gestion spécialisé n’ait été installé sur leur ordinateur.</p></li>
<li><p>Outil de gestion des lignes de commandes de Lync Server Management Shell, qui est basé sur l’interface de ligne de commande Windows PowerShell. Il fournit un ensemble de commandes complet pour l’administration de tous les aspects du produit, et permet aux administrateurs de Lync Server d’automatiser les tâches répétitives à l’aide d’un outil familier.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Si les fonctionnalités de messagerie instantanée et de présence sont automatiquement installées lors du déploiement de Lync Server, vous pouvez choisir de déployer des conférences, des voix d’entreprise et un accès aux utilisateurs distants pour adapter votre déploiement aux besoins de votre organisation.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Messagerie instantanée et présence dans Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conférence dans Lync Server 2013](lync-server-2013-conferencing.md)

  - [Voix Entreprise dans Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Évolutivité avec Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

