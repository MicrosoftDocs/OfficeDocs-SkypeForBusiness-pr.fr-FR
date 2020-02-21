---
title: 'Lync Server 2013 : interopérabilité des clients dans Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interopérabilité des clients dans Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-04_

Cette rubrique décrit la capacité des clients Microsoft Lync Server 2013 à coexister et interagir avec les clients à partir de versions antérieures de Lync Server et Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilité serveur-client

Le tableau suivant indique les combinaisons prises en charge des versions de client et de serveur. Ce tableau indique également si la connexion est prise en charge lorsque le client tente de se connecter au serveur indiqué. Lync Server 2013 prend en charge la version précédente du client. Par ailleurs, à la différence des versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Cela permet aux organisations qui effectuent une mise à niveau à partir de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Supported5</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>conversation de groupe Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Non Supported3</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Application Lync du Windows Store</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
</tbody>
</table>


1Pour plus d’informations, consultez la rubrique [migration from Lync server 2010, Group chat ou Office Communications Server 2007 R2 Group chat to Lync server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, la fonctionnalité de conversation de groupe était disponible avec le serveur de conversation de groupe, une application tierce approuvée pour Lync Server 2010. Les clients Lync 2013 ne sont pas compatibles avec Lync Server 2010, Group chat.

3Lync Web App 2013 offre désormais une expérience complète en matière de réunion, y compris l’audio et la vidéo de l’ordinateur, et est considérée comme le remplacement de Lync 2010 Attendee. Lync 2010 Attendee se connectera à Lync Server 2013 uniquement lorsque vous utilisez un navigateur non pris en charge (Internet Explorer 6 ou Internet Explorer 7) et Windows XP.

les fonctionnalités de présence et de messagerie instantanée 4The dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 convient à l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour rejoindre des réunions Lync Server 2013.

5 pour des limitations, voir « prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010 » plus loin dans cette rubrique.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interopérabilité entre les clients

Avec la version Lync Server 2013, différentes versions de client peuvent interagir de façon transparente dans les scénarios d’égal à égal et de conférence. Cette section décrit la disponibilité des fonctionnalités lorsque les utilisateurs interagissent avec d’autres utilisateurs exécutant des versions différentes de client et de serveur.

<div>

## <a name="peer-to-peer-feature-support"></a>Prise en charge de la fonctionnalité d’égal-à-égal

Les fonctionnalités d’égal-à-égal sont prises en charge pour les utilisateurs qui sont hébergés sur différentes versions du serveur et qui utilisent différentes versions du client. L’expérience de l’utilisateur final et les fonctionnalités disponibles reflètent les capacités du client de l’utilisateur et de la version du serveur auquel l’utilisateur est connecté. En d’autres termes :

  - Si un utilisateur est connecté à Lync Server 2013 avec un ancien client, l’expérience de l’utilisateur sera la même que pour. Aucune des nouvelles fonctionnalités introduites dans Lync Server 2013 ne sera disponible tant que le client de l’utilisateur n’aura pas été mis à niveau. Les exemples incluent la Galerie vidéo, la vidéo HD, le partage PowerPoint mis à jour et l’option de désactivation de l’audio et de la vidéo de tous les participants lors de l’entrée de la réunion. Les nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et les nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un utilisateur est connecté à Lync Server 2010 avec un client Lync 2013, toutes les nouvelles fonctionnalités non prises en charge par Lync Server 2010 seront indisponibles jusqu’à ce que l’utilisateur soit déplacé vers Lync Server 2013.

Le tableau suivant compare la disponibilité des fonctionnalités dans les sessions P2P où le client est connecté à Lync Server 2013 ou Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App et Lync 2010 Attendee sont des clients de réunion uniquement et ne sont pas inclus dans ce tableau.



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Messagerie instantanée</th>
<th>Présence</th>
<th>Voix</th>
<th>Vidéo</th>
<th>Partage d’application</th>
<th>Transfert de fichiers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Yes1</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Messagerie instantanée publique (AOL, Yahoo!)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Messagerie instantanée publique (MSN, Windows Live Messenger)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>..</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !. Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</P></LI></UL>



</div>

1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programmes) est disponible.

<div>


> [!NOTE]  
> Le partage de bureau entre Office Communicator 2007 R2 et Skype entreprise 2015 ne peut pas être initié à partir du client plus récent lorsque l’interface utilisateur du client Skype entreprise 2015 est appliquée.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010

Lorsque les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013, ils ont accès aux fonctionnalités clientes de Lync 2013 avec les exceptions suivantes :

  - Dans les options de gestion des **participants** , qui sont accessibles en pointant sur l’icône contacts dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.

  - La vue de la galerie ne fonctionne pas dans les vidéoconférences. L’utilisateur voit uniquement le haut-parleur actif au lieu de tous les haut-parleurs. Dans la liste des options de **sélection de disposition** , le **mode Galerie** n’est pas disponible.

  - La liste des participants s’affiche par défaut dans les vidéoconférences.

  - Lorsque vous cliquez avec le bouton droit de la souris sur un utilisateur dans la liste des participants, les options **verrouiller les vidéos en vedette** de la vidéo et **accrocher aux participants de la Galerie** ne sont pas disponibles.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Prise en charge des fonctionnalités de conférence dans les réunions Lync Server 2013

Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois que leurs comptes sont déplacés vers Lync Server 2013 et qu’ils se connectent avec le client Lync 2013. Les exemples incluent la Galerie vidéo, la vidéo HD, le partage PowerPoint et l’option de mise en sourdine de tous les participants audio et vidéo lors de l’entrée de la réunion. Les nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et les nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Dans les réunions Lync Server 2013, certaines fonctionnalités de conférence sont prises en charge pour les utilisateurs qui sont hébergés sur des versions différentes du serveur et qui utilisent des clients et des versions de client différents. Lorsque les clients rejoignent une réunion Lync Server 2013, les utilisateurs ont accès aux fonctionnalités et aux fonctionnalités présentées dans ce tableau.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Messagerie instantanée d’égal-à-égal</th>
<th>Voix</th>
<th>Vidéo</th>
<th>Partage d’application</th>
<th>PowerPoint</th>
<th>Transfert de fichiers</th>
<th>Tableau blanc collaboratif</th>
<th>Interrogation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui2</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Yes3</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programmes) est disponible.

2 Lync Server 2013 utilise un mécanisme mis à jour pour télécharger des fichiers PowerPoint. Les utilisateurs de Lync Web App qui rejoignent une réunion initialement planifiée sur Lync Server 2010 peuvent afficher et naviguer dans les présentations PowerPoint, mais ne peuvent pas télécharger de fichiers PowerPoint.

3 Si la réunion a été planifiée sur Lync Server 2013 et que les diapositives PowerPoint ont été téléchargées par un client Lync 2013, les utilisateurs de Lync 2010 disposent d’un accès en lecture seule aux diapositives. À l’inverse, si les diapositives PowerPoint ont été téléchargées par un utilisateur de Lync 2010, les utilisateurs de Lync Server 2013 peuvent visualiser et diapositives et, si Office Web Apps Server est configuré, accéder à de nouvelles fonctionnalités telles que l’affichage à haute résolution, les animations, les transitions de diapositives et vidéo incorporée. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

les fonctionnalités de présence et de messagerie instantanée 4The dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 convient à l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour rejoindre des réunions Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Prise en charge des compléments de planification

La prise en charge par le serveur des différents compléments de planification reflète la compatibilité de la version du serveur et du client. En règle générale, les compléments de planification suivants sont pris en charge sur Lync Server 2013. Toutefois, les versions précédentes des compléments ne fournissent pas de nouvelles fonctionnalités de complément Lync 2013, telles que l’option de désactivation de l’audio et de la vidéo de tous les participants lors de l’entrée de la réunion.

  - **Le complément de réunion en ligne pour Lync 2013**   fournit les mêmes fonctionnalités que le complément de réunion en ligne pour Lync 2010, avec l’ajout de contrôles muet des participants, qui permettent aux organisateurs de la réunion de planifier les conférences qui ont désactivé l’audio et la vidéo des participants par défaut. Les administrateurs peuvent également personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL de support, une URL de clause d’exclusion de responsabilité ou un texte de pied de page personnalisé.

  - **Le complément de réunion en ligne pour Lync 2010**   fournit une planification pour les réunions Lync et supprime la possibilité de planifier des conférences Office Live Meeting.

  - **Office Communicator 2007 R2 Conferencing Add-in**   fournit la planification des conférences Office Live Meeting et Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> Les conférences Live Meeting ne peuvent pas être planifiées sur Lync Server 2013.



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
<th>Client de planification</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Complément de réunion en ligne pour Lync 2013 (peut être utilisé avec Office 2013, Outlook 2010 et Outlook 2007)</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge (nouvelles fonctionnalités de complément non disponible)</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Planificateur Web Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>complément de réunion en ligne pour Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Complément de conférence pour Office Communicator 2007 R2</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Prise en charge de la participation aux réunions

Tous les clients pris en charge par Lync Server 2013 sont autorisés à rejoindre des réunions Lync 2013. Dans la mesure où Lync Web App est un composant Web du serveur, dans les cas où Lync Web App est utilisé pour rejoindre une réunion Lync Server 2013, la version plus récente de Lync Web App est toujours utilisée.

Les clients Lync 2013 peuvent rejoindre des réunions hébergées sur Lync 2010 et Office Communications Server 2007 R2 avec des fonctionnalités réduites. Les fonctionnalités de réunion sont limitées par la version du serveur sur lequel la réunion est hébergée.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour les applications Lync Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

