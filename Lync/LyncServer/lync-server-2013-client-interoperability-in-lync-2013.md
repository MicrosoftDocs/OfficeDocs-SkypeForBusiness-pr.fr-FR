---
title: 'Lync Server 2013 : Interopérabilité des clients dans Lync 2013'
TOCTitle: Interopérabilité des clients dans Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204672(v=OCS.15)
ms:contentKeyID: 49296262
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Interopérabilité des clients dans Lync 2013

 

_**Dernière rubrique modifiée :** 2016-03-04_

Cette rubrique présente la capacité des clients Microsoft Lync Server 2013 à coexister et à interagir avec les clients des anciennes versions de Lync Server et d’Office Communications Server.

## Compatibilité serveur-client

Le tableau suivant indique les combinaisons prises en charge des versions de client et de serveur. Ce tableau indique également si la connexion est prise en charge lorsque le client tente de se connecter au serveur indiqué. Lync Server 2013 prend en charge la version de client précédente. En outre, contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Les organisations qui procèdent à une mise à niveau depuis Lync Server 2010 peuvent ainsi déployer de nouveaux clients indépendamment des mises à niveau de Lync Server.


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
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge5</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Concepts de base Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Intendant Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Conversation de groupe Lync 2010</p></td>
<td><p>Pris en charge1</p></td>
<td><p>Pris en charge2</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Participant Lync 2010</p></td>
<td><p>Non pris en charge3</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interopérable4</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Intendant Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
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
<td><p>application Lync du Windows Store</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
</tbody>
</table>


1Pour plus d’informations, voir [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2Dans Microsoft Lync Server 2010, la conversation de groupe était disponible avec le serveur de conversation de groupe, application approuvée tierce pour Lync Server 2010. Les clients Lync 2013 ne sont pas compatibles avec Lync Server 2010, conversation de groupe.

3Lync Web App 2013 offre à présent un environnement de réunion complet, incluant le son et la vidéo, et est considéré comme remplaçant Participant Lync 2010. Participant Lync 2010 se connectera à Lync Server 2013 seulement si vous utilisez un navigateur non pris en charge (Internet Explorer 6 ou Internet Explorer 7) et Windows XP.

4Les fonctionnalités de présence et de messagerie instantanée dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, contrairement aux fonctionnalités de conférence. Pendant la migration depuis Office Communications Server 2007 R2, Office Communicator 2007 R2 convient pour l’interopérabilité avec les fonctionnalités de présence et de messagerie instantanée, mais les utilisateurs doivent recourir à Lync Web App 2013 pour participer aux réunions Lync Server 2013.

5 Pour les limitations, voir « Prise en charge de la fonctionnalité de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010 Meetings », plus loin dans cette rubrique.

## Interopérabilité entre les clients

Avec Lync Server 2013, les différentes versions des clients peuvent interagir en toute transparence dans des scénarios d’égal-à-égal et de conférence. Cette section décrit la disponibilité des fonctionnalités lorsque les utilisateurs interagissent avec d’autres utilisateurs exécutant des versions différentes de client et de serveur.

## Prise en charge de la fonctionnalité d’égal-à-égal

Les fonctionnalités d’égal-à-égal sont prises en charge pour les utilisateurs qui sont hébergés sur différentes versions du serveur et qui utilisent différentes versions du client. L’expérience de l’utilisateur final et les fonctionnalités disponibles reflètent les capacités du client de l’utilisateur et de la version du serveur auquel l’utilisateur est connecté. En d’autres termes :

  - Si un utilisateur est connecté à Lync Server 2013 avec un ancien client, l’utilisateur bénéficiera de la même expérience. Pour que les nouvelles fonctionnalités introduites dans Lync Server 2013 soient disponibles, l’utilisateur doit mettre à niveau le client. Les exemples incluent la vue de la galerie vidéo, la vidéo HD, le partage PowerPoint et l'option permettant de désactiver les fonctions audio et vidéo de tous les participants à leur arrivée à la réunion. Les nouvelles fonctions sont présentées dans [Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un utilisateur est connecté à Lync Server 2010 avec un client Lync 2013, les nouvelles fonctionnalités non prises en charge par Lync Server 2010 seront disponibles une fois que l’utilisateur aura procédé à la mise à niveau vers Lync Server 2013.

Le tableau suivant compare les fonctionnalités disponibles dans des sessions d’égal-à-égal dans lesquelles le client est connecté à Lync Server 2013 ou à Lync Server 2010.

> [!NOTE]  
> Lync Web App et Participant Lync 2010 sont des clients de réunion uniquement et ne sont pas inclus dans ce tableau.


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
<td><p>Concepts de base Lync 2013</p></td>
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
<td><p>Intendant Lync 2010</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui1</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Messagerie instantanée publique (AOL, Yahoo!)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Messagerie instantanée publique (MSN, Windows Live Messenger)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut plus être achetée ni renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo!. Pour plus d’informations, voir <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent ne sera pas renouvelé.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de la messagerie instantanée.</p></li></ul>


1 Dans Office Communicator 2007 R2, seul le partage de Bureau est disponible ; le partage de programme ne l’est pas.

## Prise en charge de la fonctionnalité de conférence pour les clients Lync 2013 dans les réunions Lync Server 2010

Quand des utilisateurs se joignent à des réunions Lync Server 2010 avec un client Lync 2013, ils ont accès aux fonctions du client Lync 2013, aux exceptions près suivantes :

  - Dans les options de gestion des **Participants**, qui sont accessibles via l'icône des personnes dans la fenêtre de la réunion, l'option **Aucune messagerie instantanée de réunion** ne fonctionne pas.

  - La vue Galerie ne fonctionne pas dans les conférences vidéo. L'utilisateur voit uniquement le haut-parleur actif et non tous les haut-parleurs. Dans la liste des options **Choisir une disposition**, l'option **Vue Galerie** n'est pas disponible

  - La liste des participants s'affiche par défaut dans les conférences vidéo.

  - Lorsque vous effectuez un clic droit dans la liste des participants, les options de gestion des participants **Verrouiller les actualités vidéo** et **Épingler à la galerie** ne sont pas disponibles.

## Prise en charge de la fonctionnalité de conférence dans les réunions Lync Server 2013

Lync Server 2013 fournit de nouvelles fonctionnalités de conférences qui deviennent accessibles une fois que les utilisateurs sont transférés vers Lync Server 2013 et qu'ils se connectent avec le client Lync 2013. Les exemples incluent la vue de la galerie vidéo, la vidéo HD, le partage PowerPoint et l'option permettant de désactiver les fonctions audio et vidéo de tous les participants à leur arrivée à la réunion. Les nouvelles fonctionnalités de conférence sont présentées dans [Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Dans les réunions Lync Server 2013, certaines fonctionnalités de conférence sont prises en charge pour les utilisateurs qui sont hébergés sur différentes versions du serveur et qui utilisent différents clients et différentes versions de client. Lorsque des clients rejoignent une réunion Lync Server 2013, les utilisateurs ont accès aux fonctionnalités et capacités indiquées dans ce tableau.


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
<td><p>Concepts de base Lync 2013</p></td>
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
<td><p>Office Communicator 2007 R24</p></td>
<td><p>Oui</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


1 Dans Office Communicator 2007 R2, seul le partage de Bureau est disponible ; le partage de programme ne l’est pas.

2Lync Server 2013 utilise un mécanisme mis à jour pour télécharger des fichiers PowerPoint. Les utilisateurs de Lync Web App qui rejoignent une réunion planifiée à l’origine sur Lync Server 2010 peuvent afficher et accéder aux présentations PowerPoint, mais ils ne peuvent pas télécharger des fichiers PowerPoint.

3 Si la réunion a été programmée sur Lync Server 2013 et que les diapositives PowerPoint ont été téléchargées par un client Lync 2013, les utilisateurs de Lync 2010 peuvent seulement visualiser les diapositives. Inversement, si les diapositives PowerPoint ont été téléchargées par un utilisateur Lync 2010, les utilisateurs de Lync Server 2013 pourront visualiser les diapositives et, si Office Web Apps Server est configuré, accéder à de nouvelles fonctionnalités telles qu’une résolution d’affichage supérieure, des animations, des transitions de diapositive et des vidéos incorporées. Pour plus d’informations, voir [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Les fonctionnalités de présence et de messagerie instantanée dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, contrairement aux fonctionnalités de conférence. Pendant la migration depuis Office Communications Server 2007 R2, Office Communicator 2007 R2 convient pour l’interopérabilité avec les fonctionnalités de présence et de messagerie instantanée, mais les utilisateurs doivent recourir à Lync Web App 2013 pour participer aux réunions Lync Server 2013.

## Prise en charge des compléments de planification

La prise en charge par le serveur des différents compléments de planification reflète la compatibilité de la version du serveur et du client. En général, les compléments de planification suivants sont pris en charge sur Lync Server 2013. Cependant, les versions précédentes des compléments ne fournissent pas les nouvelles fonctionnalités de complément de Lync 2013, telle que l’option permettant de désactiver le son et la vidéo pour tous les participants lorsqu’ils rejoignent une réunion.

  - Le **complément de réunion en ligne pour Lync 2013** fournit les mêmes fonctionnalités que le complément de réunion en ligne pour Lync 2010, avec en plus des contrôles de désactivation du son pour les participants, qui permettent aux organisateurs d’une réunion de planifier des conférences pour lesquelles le son et la vidéo sont désactivés par défaut. Les administrateurs peuvent également personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL de prise en charge, une URL d’exclusion de responsabilité ou un texte de pied de page personnalisé.

  - Le **complément de réunion en ligne pour Lync 2010** permet la planification des réunions Lync mais ne permet pas de planifier des conférences Office Live Meeting.

  - Le **complément de conférence pour Office Communicator 2007 R2** permet la planification des conférences Office Live Meeting et des conférences Office Communicator 2007 R2.

> [!NOTE]  
> Les conférences Live Meeting ne peuvent pas être planifiées sur Lync Server 2013.


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
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>complément de réunion en ligne pour Lync 2013 (peut être utilisé avec Office 2013, Outlook 2010 et Outlook 2007)</p></td>
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


## Prise en charge de la participation aux réunions

Tous les clients pris en charge par Lync Server 2013 sont autorisés à rejoindre des réunions Lync 2013. Étant donné que Lync Web App est un composant Web du serveur, si Lync Web App est utilisé pour rejoindre une réunion Lync Server 2013, la dernière version de Lync Web App est toujours utilisée.

Les clients Lync 2013 peuvent rejoindre des réunions hébergées sur Lync 2010 et Office Communications Server 2007 R2 avec des fonctionnalités réduites. Les fonctionnalités de réunion sont limitées par la version du serveur sur lequel la réunion est hébergée.

## Voir aussi

#### Concepts

[Configuration requise de l’application Lync du Windows Store](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)

