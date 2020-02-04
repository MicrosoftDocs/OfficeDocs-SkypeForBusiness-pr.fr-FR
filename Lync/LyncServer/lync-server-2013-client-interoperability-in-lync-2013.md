---
title: 'Lync Server 2013 : Interopérabilité des clients dans Lync 2013'
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
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interopérabilité des clients dans Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-04_

Cette rubrique explique la possibilité pour les clients Microsoft Lync Server 2013 de cohabiter et d’interagir avec les clients provenant de versions antérieures de Lync Server et d’Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilité entre le serveur et le client

Le tableau ci-dessous indique les combinaisons prises en charge par les versions de client et serveur. Ce tableau indique si la connexion est prise en charge lorsque le client tente de se connecter au serveur indiqué. Lync Server 2013 prend en charge la version précédente du client. Par ailleurs, contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Cela permet aux organisations qui effectuent la mise à niveau de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau de Lync Server.


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
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Supported5</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 de base</p></td>
<td><p>Pris en charge </p></td>
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
<td><p>Lync 2010</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 attendant</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Conversation de groupe Lync 2010</p></td>
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
<td><p>Lync 2010 participant</p></td>
<td><p>Non Supported3</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 attendant</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>application Lync du Windows Store</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
</tbody>
</table>


1Pour plus d’informations, reportez-vous à la section [migration de Lync server 2010, discussion de groupe ou Office Communications Server 2007 R2 en conversation de groupe vers Lync server 2013, serveur de conversation persistant](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, les fonctionnalités de discussion de groupe étaient disponibles avec le serveur de discussion de groupe, une application de confiance tierce pour Lync Server 2010. Les clients 2013 Lync ne sont pas compatibles avec Lync Server 2010 et la discussion de groupe.

3Lync Web App 2013 offre désormais une prise en compte complète de la réunion, y compris le son et la vidéo de l’ordinateur, et est considérée comme un élément de remplacement de Lync 2010 Attendee. Lync 2010 Attendee se connecte à Lync Server 2013 uniquement si vous utilisez un navigateur non pris en charge (Internet Explorer 6 ou Internet Explorer 7) et Windows XP.

4Synthèse les fonctionnalités de présence et de messagerie instantanée d’Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 est approprié pour l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013.

5 pour plus d’limitations, voir la section « assistance technique pour les clients Lync 2013 dans les réunions Lync Server 2010 » plus loin dans cette rubrique.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interopérabilité entre les clients

Avec la version 2013 du serveur Lync, les différentes versions du client peuvent interagir en toute transparence dans les scénarios d’égal à égal et de conférence. Cette section traite de la disponibilité des fonctionnalités lorsque les utilisateurs interagissent avec d’autres utilisateurs qui utilisent des versions différentes de clients et de serveurs.

<div>

## <a name="peer-to-peer-feature-support"></a>Prise en charge des fonctionnalités d’égal à égal

Les fonctionnalités d’égal à égal sont prises en charge pour les utilisateurs hébergés sur des versions différentes du serveur et utilisant des versions de clients différentes. L’utilisation des fonctionnalités finales et des fonctionnalités disponibles est cohérente avec les fonctionnalités du client de l’utilisateur et celle du serveur auquel il est connecté. En d’autres termes :

  - Si un utilisateur est connecté à Lync Server 2013 avec un client plus ancien, il aura la même connaissance qu’il est utilisé. Aucune des nouvelles fonctionnalités introduites dans Lync Server 2013 ne sera disponible tant que le client de l’utilisateur n’a pas été mis à niveau. Il s’agit notamment de l’affichage Galerie de vidéos, de la vidéo HD, de la mise à jour du partage PowerPoint et de l’option désactiver l’audio et la vidéo des participants lors de la réunion. Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un utilisateur est connecté à Lync Server 2010 avec un client 2013 Lync, toutes les nouvelles fonctionnalités non prises en charge par Lync Server 2010 ne seront pas disponibles tant que l’utilisateur n’aura pas été déplacé vers Lync Server 2013.

Le tableau suivant compare la disponibilité des fonctionnalités dans les sessions d’égal à égal où le client est connecté à Lync Server 2013 ou Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App et Lync 2010 ne sont pas des clients de réunion et ne sont pas inclus dans ce tableau.



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
<th>Audio</th>
<th>Vidéo</th>
<th>Partage d’application</th>
<th>Transfert de fichiers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 de base</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 attendant</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 mobile</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui 1</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Messagerie instantanée publique (AOL, Yahoo !)</p></td>
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
> <P>À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</P></LI></UL>



</div>

1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programme) est disponible.

<div>


> [!NOTE]  
> Le partage de bureau entre Office Communicator 2007 R2 et Skype entreprise 2015 ne peut pas être démarré à partir du client plus récent lorsque l’interface utilisateur du client Skype entreprise 2015 est appliquée.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Prise en charge des fonctionnalités de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010

Lorsque des utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013, ils ont accès aux fonctionnalités du client Lync 2013 avec les exceptions suivantes :

  - Dans les options de gestion des **participants** accessibles en pointant sur l’icône personnes dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.

  - Le mode Galerie ne fonctionne pas dans les conférences vidéo. L’utilisateur ne voit que le haut-parleur actif au lieu de ses haut-parleurs. Dans la liste des options **choisir une disposition, la** **vue Galerie** n’est pas disponible

  - La liste des participants s’affiche par défaut dans les conférences vidéo.

  - Lorsque vous cliquez avec le bouton droit sur un utilisateur dans la liste des participants, les options **verrouiller les actualités vidéo** et **épingler aux participants à la Galerie** ne sont pas disponibles.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Prise en charge des fonctionnalités de conférence dans les réunions Lync Server 2013

Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois leur compte déplacé vers Lync Server 2013 et se connectant avec le client Lync 2013. Il s’agit notamment de l’affichage Galerie de vidéos, de la vidéo HD, du partage PowerPoint et de l’option désactiver l’audio et la vidéo des participants à la réunion. Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Dans les réunions Lync Server 2013, certaines fonctions de conférence sont prises en charge pour les utilisateurs qui sont hébergés sur des versions différentes du serveur et qui utilisent des clients et des versions de clients différents. Lorsque des clients rejoignent une réunion Lync Server 2013, les utilisateurs ont accès aux fonctionnalités et fonctionnalités présentées dans le tableau ci-dessous.


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
<th>Messagerie instantanée d’égal à égal</th>
<th>Audio</th>
<th>Vidéo</th>
<th>Partage d’application</th>
<th>PowerPoint</th>
<th>Transfert de fichiers</th>
<th>Tableau blanc</th>
<th>Interrogation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
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
<td><p>Lync 2013 de base</p></td>
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
<td><p>Lync Web App</p></td>
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
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui3</p></td>
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


1 dans Office Communicator 2007 R2, seul le partage de bureau (et non le partage de programme) est disponible.

2 Lync Server 2013 utilise un mécanisme de mise à jour pour télécharger des fichiers PowerPoint. Les utilisateurs Lync Web App qui rejoignent une réunion planifiée à l’origine sur Lync Server 2010 peuvent afficher et parcourir les présentations PowerPoint, mais ne peuvent pas télécharger de fichiers PowerPoint.

3 Si la réunion a été planifiée sur Lync Server 2013 et les diapositives PowerPoint téléchargées par un client 2013 Lync, les utilisateurs de Lync 2010 disposent d’un accès en affichage seul aux diapositives. À l’inverse, si les diapositives PowerPoint ont été téléchargées par un utilisateur de Lync 2010, les utilisateurs de Lync Server 2013 pourront afficher et des diapositives et, si Office Web Apps Server est configuré, accéder aux nouvelles fonctionnalités telles que l’affichage d’une résolution supérieure, des animations, des transitions entre les diapositives et vidéo incorporée. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Synthèse les fonctionnalités de présence et de messagerie instantanée d’Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 est approprié pour l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Planification de la prise en charge des compléments

La prise en charge du serveur pour les divers compléments de planification est cohérente avec la compatibilité entre les versions serveur et client. En général, les compléments de planification suivants sont pris en charge sur Lync Server 2013. Toutefois, les versions précédentes des compléments ne fournissent pas de nouvelles fonctionnalités de complément Lync 2013, comme l’option permettant de désactiver l’audio et la vidéo de tous les participants lors de la réunion.

  - **Le complément réunion en ligne pour Lync 2013**   fournit les mêmes fonctionnalités que le complément réunion en ligne pour Lync 2010, ainsi que l’ajout de contrôles d’activation du son pour les participants, qui permettent aux organisateurs de la réunion de programmer des conférences qui présentent le son et la vidéo en sourdine par défaut. Les administrateurs peuvent également personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL d’assistance, une URL d’exclusion de responsabilité ou un texte de pied de page personnalisé.

  - **Le complément réunion en ligne pour Lync 2010**   fournit une planification pour les réunions Lync et supprime la possibilité de planifier des conférences Office Live Meeting.

  - **Le complément de**   conférence Office Communicator 2007 R2 fournit une planification pour les conférences Office Live Meeting et les conférences Office Communicator 2007 R2. 

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
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Complément réunion en ligne pour Lync 2013 (peut être utilisé avec Office 2013, Outlook 2010 et Outlook 2007)</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge (les nouvelles fonctionnalités des compléments ne sont pas disponibles)</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web Scheduler</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Complément réunion en ligne pour Lync 2010</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Complément de conférence Office Communicator 2007 R2</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Prise en charge de la participation aux réunions

Tous les clients pris en charge par Lync Server 2013 sont autorisés à participer à des réunions Lync 2013. Comme Lync Web App est un composant Web du serveur, dans les cas où Lync Web App est utilisé pour participer à une réunion Lync Server 2013, la version la plus récente de Lync Web App est toujours utilisée.

Les clients 2013 Lync peuvent rejoindre des réunions hébergées sur Lync 2010 et Office Communications Server 2007 R2 avec des fonctionnalités mises à l’échelle. Les fonctionnalités en réunion sont limitées par la version du serveur sur lequel la réunion est hébergée.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour l’application Lync du Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

