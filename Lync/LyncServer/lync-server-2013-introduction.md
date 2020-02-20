---
title: Présentation de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 892985a42e11a7f0b3466ad66e35ad5cf6c29ec4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Présentation de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

Lync Server 2013 et son logiciel client, tels que Lync 2013, permettent à vos utilisateurs de se connecter de nouvelles façons et de rester connectés, quel que soit leur emplacement physique. Lync et Lync Server rassemblent les différentes façons dont les utilisateurs communiquent dans une seule interface client, sont déployés en tant que plateforme unifiée et sont administrés via une infrastructure de gestion unique.

Ce tableau et les sections suivantes illustrent les principaux ensembles de fonctionnalités, ou *charges de travail*, que Lync Server fournit pour vos utilisateurs.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Charge de travail</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>La messagerie instantanée et la présence aident vos utilisateurs à trouver et à communiquer les uns avec les autres efficacement.</p>
<p>La messagerie instantanée fournit une plateforme de messagerie instantanée avec historique des conversations et prend en charge la connectivité PIC avec des utilisateurs de réseaux de messagerie instantanée publics, tels que MSN/Windows Live, Yahoo !, AOL et Google Talk.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>


</div>
<p>La présence établit et affiche la disponibilité et la volonté personnelles d’un utilisateur pour communiquer en utilisant des États communs, tels que <strong>disponible</strong> ou <strong>occupé</strong>, ainsi que des États plus détaillés, tels que les États de <strong>retour</strong> et de <strong>non-dérangation</strong>. Ces informations de présence enrichie permettent aux autres utilisateurs d’effectuer immédiatement des choix de communication efficaces.</p></td>
</tr>
<tr class="even">
<td><p>Vidéoconférence</p></td>
<td><p>Lync Server inclut la prise en charge de la Conférence par messagerie instantanée, de l’audioconférence, de la conférence Web, de la vidéoconférence et du partage d’application pour les réunions planifiées et impromptues. Tous ces types de réunion sont pris en charge avec un seul client. Lync Server prend également en charge la Conférence rendez-vous afin que les utilisateurs de téléphones de réseau téléphonique commuté (PSTN) puissent participer à la partie audio des conférences.</p>
<p>Les conférences peuvent être modifiées et croître en temps réel de façon transparente. Par exemple, une seule conférence peut commencer comme un simple message instantané entre quelques utilisateurs et faire remonter une conférence audio avec le partage du bureau et une audience plus importante instantanément, facilement et sans interrompre le flux de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p><em>Voix entreprise</em> est l’offre voix sur IP (VoIP) de Lync Server. Il offre une option vocale pour améliorer ou remplacer les systèmes PBX (Private Branch Exchange) traditionnels. En plus des fonctionnalités de téléphonie complètes d’un PBX IP, voix entreprise est intégrée à la présence riche, à la messagerie instantanée, à la collaboration et aux réunions. Les fonctionnalités telles que la réponse d’appel, la conservation, la reprise, le transfert, le transfert et le transfert sont prises en charge directement, tandis que les touches de numérotation rapides personnalisées sont remplacées par les listes de contacts et l’intercom automatique est remplacé par la messagerie instantanée.</p>
<p>Voix entreprise prend en charge la haute disponibilité via le contrôle d’admission des appels (CAC), la survivabilité des succursales et les options étendues de résilience des données.</p></td>
</tr>
<tr class="even">
<td><p>Prise en charge des utilisateurs distants</p></td>
<td><p>Vous pouvez fournir des fonctionnalités Lync Server complètes pour les utilisateurs qui se trouvent actuellement en dehors des pare-feu de votre organisation en déployant des serveurs appelés <em>serveurs Edge</em> pour fournir une connexion à ces utilisateurs distants. Ces utilisateurs distants peuvent se connecter à des conférences à l’aide d’un ordinateur personnel avec Lync 2013 installé, le téléphone ou une interface Web.</p>
<p>Le déploiement de serveurs Edge vous permet également de <em>fédérer</em> avec des organisations partenaires ou fournisseurs. Une relation fédérée permet à vos utilisateurs de placer des utilisateurs fédérés dans leurs listes de contacts, d’échanger des informations de présence et de messages instantanés avec ces utilisateurs, et de les inviter à des appels audio, des appels vidéo et des conférences.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge des clients mobiles</p></td>
<td><p>De plus, grâce aux services de mobilité Lync Server, vos utilisateurs peuvent accéder à la fonctionnalité Lync lors de l’utilisation d’appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge et de l’envoi et de la réception de messages instantanés, de l’affichage de contacts et affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. Les notifications de type transmission sont également prises en charge pour les appareils mobiles qui ne prennent pas en charge les applications exécutées en arrière-plan.</p></td>
</tr>
<tr class="even">
<td><p>Intégration à d’autres produits</p></td>
<td><p>Lync Server s’intègre à plusieurs autres produits pour fournir des avantages supplémentaires à vos utilisateurs et administrateurs.</p>
<p>Les outils de réunion sont intégrés à Outlook pour permettre aux organisateurs de planifier une réunion ou de démarrer une conférence impromptue d’un simple clic et de faciliter la participation des participants.</p>
<p>Les informations de présence sont intégrées dans Outlook et SharePoint.</p>
<p>La messagerie unifiée Exchange fournit plusieurs fonctionnalités d’intégration. Les utilisateurs peuvent voir s’ils ont de nouveaux messages vocaux dans Lync Server. Ils peuvent cliquer sur un bouton de lecture dans le message Outlook pour écouter la messagerie vocale audio, ou afficher une transcription de la messagerie vocale dans le message de notification.</p>
<p>De plus, l’exécution de Lync Server 2013 avec Exchange 2013 permet plusieurs nouvelles fonctionnalités, telles qu’un magasin de contacts unifié, accessible par les clients des deux produits, ainsi que des photos haute résolution pour les contacts stockés dans la base de données Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Déploiement simple</p></td>
<td><p>Pour vous aider à planifier et à déployer vos serveurs et clients, Lync Server fournit le générateur de topologies.</p>
<p>Le générateur de topologies est un composant d’installation de Lync Server. Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée. Il valide également votre topologie avant que vous ne commenciez à installer les serveurs. Lorsque vous installez Lync Server sur des serveurs individuels, le programme d’installation déploie le serveur comme indiqué dans la topologie.</p></td>
</tr>
<tr class="even">
<td><p>Gestion simplifiée</p></td>
<td><p>Une fois que vous avez déployé Lync Server, il offre les outils de gestion puissants et rationalisés suivants :</p>
<ul>
<li><p>Gestion centrale de la configuration, qui vous permet de gérer les modifications de façon centralisée et de les répliquer rapidement dans l’ensemble du déploiement.</p></li>
<li><p>Panneau de configuration Lync Server, interface utilisateur graphique Web pour les administrateurs. Grâce à cette interface utilisateur basée sur le Web, les administrateurs de Lync Server peuvent gérer leurs systèmes depuis n’importe quel emplacement sur le réseau d’entreprise, sans avoir besoin de logiciels de gestion spécialisés installés sur leurs ordinateurs.</p></li>
<li><p>Outil de gestion de ligne de commande Lync Server Management Shell, basé sur l’interface de ligne de commande Windows PowerShell. Elle fournit un jeu de commandes enrichi pour l’administration de tous les aspects du produit et permet aux administrateurs de Lync Server d’automatiser les tâches répétitives à l’aide d’un outil familier.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Tandis que les fonctionnalités de messagerie instantanée et de présence sont automatiquement installées dans chaque déploiement Lync Server, vous pouvez choisir de déployer la Conférence, la voix entreprise et l’accès des utilisateurs distants, afin d’adapter votre déploiement aux besoins de votre organisation.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Messagerie instantanée et présence dans Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conférence dans Lync Server 2013](lync-server-2013-conferencing.md)

  - [Voix entreprise dans Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Évolutivité avec Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

