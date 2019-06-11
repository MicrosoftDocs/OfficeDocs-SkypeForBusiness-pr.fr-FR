---
title: 'Lync Server 2013: attributs et descriptions de schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Attributs et descriptions de schéma dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Cette section décrit tous les attributs de schéma utilisés par Lync Server 2013. Pour les classes associées à des attributs, voir [attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Pour obtenir la liste des classes et attributs qui sont des nouveautés de Lync Server 2013, voir [modifications de schéma dans Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Les attributs qui sont des paires liées sont spécifiés en tant que liens de renvoi ou liens d’arrière-plan. Un attribut qui fait référence à un autre objet est un lien de transfert; l’attribut de l’autre objet qui fait référence au premier objet est un lien précédent. Les liens de renvoi peuvent être mis à jour de façon à être en lecture seule.

Certains attributs ont une valeur de masque de bits. Pour ces attributs, chaque paramètre est représenté par un bit et la valeur décimale affichée représente la position en bits. Les positions de bits commencent par le bit 0. Par exemple, 1 (binaire) est du bit 0 défini et 10000 (binaire) est le bit 4 défini. Chaque bit représente une propriété. Voici quelques exemples:

  - 10000 (binaire) a une valeur décimale de 16 (c’est-à-dire que le bit 4 est défini).

  - 100 millions (binaire) a une valeur décimale de 256 (c’est-à-dire que le bit 8 est défini).

  - 1100 (binaire) a une valeur décimale de 12 (autrement dit, les bits 2 et 3 sont définis; les propriétés représentées par les deux bits sont activées).

  - 1111000001 (binaire) a une valeur décimale de 961 (autrement dit, les bits 0, 6, 7, 8 et 9 sont définis; les propriétés de chacun de ces bits sont activées).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Attributs de schéma pour Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Description</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Un attribut existant dans les services de domaine Active Directory, désormais associé aux classes <strong>msRTCSIP-pool</strong> et <strong>msRTCSIP-MonitoringServer</strong> . Cet attribut spécifie le nom de domaine complet (FQDN) d’un pool ou d’un serveur de surveillance.</p>
<p>La valeur valide de chaque segment est de 63 caractères. une valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés de Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Cet attribut contient la représentation de chaîne du nom unique (DN) de l’objet d’une autre forêt qui correspond à cet objet. Cet attribut est utilisé pour l’extension du groupe de distribution et la présence automatique. Cet attribut est défini dans le schéma Active Directory par défaut de Windows Server 2003 R2.</p>
<p>Pour éviter d’avoir besoin d’une mise à niveau d’AD DS vers Windows Server 2003 R2, la préparation du schéma Active Directory étend le schéma Windows Server 2003 avec cette définition d’attribut.</p></td>
<td><p>Nouveautés de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Cet attribut à valeurs multiples contient les paramètres de la messagerie vocale. Cet attribut est partagé avec la messagerie unifiée Exchange.</p></td>
<td><p>Nouveautés de Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Cet attribut à plusieurs valeurs contient des identificateurs pour les stratégies de conservation qui s’appliquent à l’utilisateur. Les stratégies de blocage préservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la conservation. Cet attribut est partagé avec Exchange 2013.</p></td>
<td><p>Nouveautés de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Cet attribut stocke les informations du fournisseur de services d’audioconférence pour un utilisateur.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Cet attribut pointe sur l’entrée de service approuvé pour le contact de l’application.</p></td>
<td><p>Nouveautés de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Cet attribut contient une liste des applications hébergées sur le serveur d’applications.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Cet attribut spécifie les options du contact de l’application.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Cet attribut contient la langue principale du contact de l’application.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Cet attribut à plusieurs valeurs contient les langues secondaires du contact de l’application.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Cet attribut contient une liste des serveurs d’application appartenant à ce pool. Le lien transférer correspondant à cet attribut de lien précédent est <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Cet attribut pointe vers le pool auquel appartient ce serveur d’applications. Il s’agit du lien transférer. Le lien inverse correspondant est <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsolète)</p></td>
<td><p>Cet attribut spécifie la valeur par défaut globale dans la limite de la forêt pour l’archivage de toutes les communications utilisateur. Cette opération est appliquée par la couche agent d’archivage. La plage de valeurs de cet attribut est la suivante:</p>
<ul>
<li><p><strong>Vrai</strong>: archiver tous les utilisateurs</p></li>
<li><p><strong>False</strong>: ne pas archiver tous les utilisateurs</p></li>
</ul>
<p>Cet attribut contrôle globalement, au sein de la frontière de la forêt, le mode d’archivage des communications utilisateur au sein d’un réseau interne.</p>
<p><strong>Comportement 2005 de Live Communications Server (désormais obsolète)</strong></p>
<p>La plage de valeurs de cet attribut est la suivante:</p>
<ul>
<li><p>0: archiver le corps du message [bit 0]</p></li>
<li><p>1: ne pas archiver le corps du message [bit 0]</p></li>
</ul>
<p><strong>Comportement 2007 d’Office Communications Server</strong></p>
<p>La plage de valeurs de cet attribut est la suivante:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (obsolète)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Cet attribut est un entier utilisé comme champ de bits pour contrôler si les communications d’un utilisateur unique doivent être archivées. Ce contrôle est appliqué par la couche de l’agent d’archivage. Il est marqué pour la réplication de catalogue global.</p>
<p>L’objectif de cet attribut est spécifique à un utilisateur ou à un contact unique. Les valeurs valides (et positions de bits associées) dans Lync Server sont les suivantes:</p>
<ul>
<li><p>0: do not Archive (aucun jeu de bits)</p></li>
<li><p>1: retrait (position de bit 0)</p></li>
<li><p>2: obsolète (position de bit 1)</p></li>
<li><p>4: archiver des communications internes (position binaire 2)</p></li>
<li><p>8: archiver des communications fédérées (position binaire 3)</p></li>
</ul>
<p>Les valeurs précédemment valides dans Live Communications Server 2005 sont les suivantes:</p>
<ul>
<li><p>0: utilisez la valeur par défaut définie par <strong>msRTCSIP-ArchiveDefault</strong> et <strong>msRTCSIP-ArchiveFederation</strong> dans cet ordre de priorité:</p>
<ul>
<li><p>1: Archive</p></li>
<li><p>2: ne pas archiver</p></li>
<li><p>3: archiver sans le corps du message</p></li>
</ul></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsolète)</p></td>
<td><p>Cet attribut définit la version du service d’archivage. Il s’agit d’un monotonously qui augmente de manière à chaque publication officielle du produit. Les valeurs possibles sont les suivantes:</p>
<ul>
<li><p>Non défini: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 avec SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Cet attribut spécifie le nom de domaine complet (FQDN) du serveur principal du pool. Étant donné qu’il ne peut exister qu’un serveur principal unique par pool, il s’agit d’un attribut à valeur unique.</p>
<p>La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Cet attribut contient l’identificateur du pool qui héberge l’annuaire de conférences.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Cet attribut contient l’identificateur d’un annuaire de conférences.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Cet attribut contient l’identificateur du pool dans lequel le répertoire de conférences est déplacé.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-par défaut</p></td>
<td><p>Cet attribut booléen définit si l’utilisation du téléphone est une utilisation par défaut. Si cet attribut est défini sur <strong>true</strong>, l’utilisation du téléphone est une utilisation par défaut qui ne peut pas être supprimée par l’administrateur. Si cet attribut est défini sur <strong>false</strong>, l’utilisation peut être supprimée.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Cet attribut identifie l’URL Communicator Web Access pour les utilisateurs extérieurs à l’organisation.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Cet attribut identifie l’URL Communicator Web Access pour les utilisateurs qui se trouvent au sein de l’organisation.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient le nom unique (DN) d’un objet de classe de profil d’emplacement qui lui est affecté.</p>
<p>Lien suivant: <strong>ID de lien 11036</strong></p>
<p>Le lien inverse correspondant est <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsolète)</p></td>
<td><p>Cet attribut booléen spécifie si la stratégie est une stratégie par défaut. La stratégie est une stratégie par défaut définie sur <strong>true</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsolète)</p></td>
<td><p>Cet attribut spécifie le nom de domaine complet (FQDN) du serveur de périphérie exécutant le service Edge d’accès, s’il est accessible directement ou à partir de l’équilibrage de charge matérielle d’un pool de serveurs exécutant le service Edge d’accès. Si les serveurs exécutant le service Edge d’accès ne peuvent être utilisés que par le biais d’un ou de plusieurs directeurs, cet attribut spécifie le nom de domaine complet et, éventuellement, le numéro de port du réalisateur ou du système d’équilibrage de la charge matérielle servant un pool de directeurs.</p>
<p>La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsolète)</p></td>
<td><p>Cet attribut représente le numéro de port qui doit être utilisé pour la connexion au serveur exécutant le service Edge d’accès.</p>
<p>La valeur valide est une valeur entière spécifiant le port à utiliser. La valeur par défaut est 5061.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration de l’abonnement de présence par défaut.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’inscription par défaut.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’abonnement aux données itinérantes par défaut.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Cet attribut est utilisé dans une topologie de domaine fractionné et contient un nom de domaine complet (FQDN).</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsolète)</p></td>
<td><p>Cet attribut de chaîne UNICODE à valeur unique contient une description conviviale de ce type de route ou de la règle de normalisation.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-nom_domaine</p></td>
<td><p>Cet attribut représente un domaine configuré pour le Bureau d’enregistrement.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Cet attribut spécifie le nom de domaine complet du serveur exécutant le service Edge d’accès.</p>
<p>La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsolète)</p></td>
<td><p>Cet attribut détermine si un serveur génère une demande de notification d’utilisation optimale, au lieu d’une demande de notification, en réponse à une demande s’ABONNer à partir d’un client. BENOTIFY est une extension d’amélioration des performances du protocole de notification d’abonnement où le serveur génère des demandes BENOTIFY au lieu de demandes de notification normales. Le gain de performance réside dans le fait qu’une demande BENOTIFY ne nécessite pas de réponse de 200 OK du client en fonction de la demande de notification.</p>
<p>Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 ne prend pas en charge les demandes BENOTIFY. Pour interagir avec des applications serveur écrites à l’aide de l’API serveur Live Communications Server 2003 exécutée sur Live Communications Server 2005 et des serveurs tiers, les demandes BENOTIFY peuvent être désactivées <STRONG></STRONG>en définissant la valeur sur false. BENOTIFY ne fait actuellement pas partie du processus de normalisation SIP de l’IETF (Internet Engineering Task Force).


</div></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsolète)</p></td>
<td><p>Cet attribut est un commutateur global utilisé par les administrateurs informatiques pour déterminer si les utilisateurs sont autorisés à communiquer avec des utilisateurs d’autres organisations. Il permet à un administrateur de remplacer l’attribut <strong>FederationEnabled</strong> d’un utilisateur individuel. Cet attribut peut vous aider à protéger le réseau interne contre les attaques via Internet qui peuvent être causées par des vers, des virus ou des attaques ciblées au niveau de l’entreprise.</p>
<p>Les valeurs valides (et positions de bits associées) sont les suivantes:</p>
<ul>
<li><p>1: activé pour la connectivité PIC (Public IM Connectivity)</p></li>
<li><p>2: réservé (position binaire 1)</p></li>
<li><p>4: réservé (position binaire 2)</p></li>
<li><p>8: réservé (position binaire 3)</p></li>
<li><p>16: le contrôle d’appel distant a été activé [téléphonie] (position bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permettre aux utilisateurs d’inviter des utilisateurs anonymes à des réunions (position de bit 6)</p></li>
<li><p>128: UCEnabled (permettre aux utilisateurs pour les communications unifiées) (position binaire 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (activer l’utilisateur pour la connectivité de messagerie instantanée publique) (position de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (position binaire 9)</p></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Cet attribut indique si les services d’entreprise sont chargés sur le serveur donné.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Cet attribut contient le code de numérotation pour l’accès externe.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Cet attribut détermine si un utilisateur unique est activé pour la Fédération. Elle est appliquée par la couche services d’entreprise. Il est marqué pour la réplication de catalogue global.</p>
<p>Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Cet attribut est une liste à plusieurs valeurs des noms de domaine de tous les serveurs Enterprise Edition associés à un pool.</p>
<p>Lien précédent: <strong>ID de lien 11023</strong></p>
<p>Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-passerelles (obsolète)</p></td>
<td><p>Cet attribut de chaîne à valeurs multiples contient une liste des passerelles et des ports (par passerelle).</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsolète)</p></td>
<td><p>Cet attribut stocke les paires nom: valeur. Le nom déjà défini: paire de valeurs correspond au paramètre <strong>autoriser l’interrogation pour la présence</strong> .</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Cet attribut est un identificateur unique d’un groupe qui est utilisé pour regrouper les entrées du carnet d’adresses.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003 (non utilisés).</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003 (non utilisés).</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Cet attribut détermine si un utilisateur unique est activé pour l’accès extérieur de l’utilisateur. Elle est appliquée par la couche services d’entreprise. Il est marqué pour la réplication de catalogue global.</p>
<p>Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ligne</p></td>
<td><p>Cet attribut à valeur unique contient l’ID de l’appareil (URI SIP ou URI TEL du téléphone contrôles) utilisé par Lync pour la téléphonie. Cet attribut est marqué pour la réplication de catalogue global et est indexé. Si un utilisateur est activé pour voix entreprise, cet attribut stocke la version normalisée E. 164 du numéro de téléphone de l’utilisateur.</p></td>
<td><p>Nouveautés de Microsoft Office Live Communications Server 2005 avec SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Cet attribut à valeur unique contient l’URI SIP du serveur de passerelle CSTA-SIP. Cet attribut est marqué pour la réplication de catalogue global, mais n’est pas indexé.</p></td>
<td><p>Nouveautés de Microsoft Office Live Communications Server 2005 avec SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsolète)</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de noms uniques (ND) de normalisation locale associés à ce profil d’emplacement. Le type de cet attribut est un fichier binaire DN. Il existe une relation un-à-plusieurs entre le profil d’emplacement et les règles de normalisation locales. Le classement de la liste du DNs de normalisation local doit être maintenu dans l’ordre indiqué par l’administrateur. La conservation de l’ordre est gérée par la partie binaire du fichier binaire du DN, qui spécifie l’index de l’ordre.</p>
<p>Lien suivant: <strong>ID de lien 11034</strong></p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Cet attribut contient une liste des options de la règle de normalisation.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient un nom convivial pour le profil d’emplacement indiquant l’emplacement que ce profil représente. Dans la mesure où il existe plusieurs profils d’emplacement, l’administrateur a besoin d’une méthode pour distinguer les différents profils.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsolète)</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de noms uniques de profils d’emplacements. Cet attribut spécifie le lien précédent vers un ou plusieurs profils d’emplacement.</p>
<p>Lien précédent: <strong>ID de lien 11035</strong></p>
<p>Cet attribut correspond à la liaison suivante <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Cet attribut contient les options du profil d’emplacement.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Cet attribut à plusieurs valeurs contient une liste des contacts de l’application.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Cet attribut à valeurs multiples comporte une liste de profils d’emplacements.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsolète)</p></td>
<td><p>Cet attribut représente le nombre maximal de demandes de recherche en suspens par serveur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsolète)</p></td>
<td><p>L’attribut représente le nombre maximal d’abonnements par utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’abonnement maximal.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai maximal d’inscriptions.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai maximal d’abonnements aux données itinérantes.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Cet attribut est un attribut de point de contrôle de service sous la classe ordinateur qui spécifie un lien vers une fabrique de contrôle multipoint (MCU) auquel il appartient. Ce point et cet attribut de contrôle de service est créé pour chaque MCU Microsoft. Chaque MCU Microsoft doit trouver le serveur principal du pool auquel il appartient, afin de récupérer les paramètres au niveau du pool.</p>
<p>La valeur de cet attribut est le nom unique (DN) de la fabrique MCU. Il s’agit d’un attribut à valeur unique qui est marqué pour la réplication de catalogue global.</p>
<p>Lien suivant: <strong>ID de lien 11026</strong></p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Il s’agit d’un attribut réservé multichaîne. Les paramètres stockés dans cet attribut sont représentés par des paires name = value. Nom actuellement défini = paires de valeurs:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Il s’agit d’un attribut à valeur unique qui contient le nom unique (DN) d’une fabrique MCU unique associée à un pool.</p>
<p>Lien suivant: <strong>ID de lien 11024</strong></p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Cet attribut est une chaîne à valeur unique qui spécifie le GUID du fournisseur de fabrique MCU. En fonction de la valeur GUID, le processus de fabrique MCU détermine si ce type MCU doit être desservi. Si la valeur GUID est <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, le processus de fabrique MCU (disponible par défaut dans Lync Server) la traitera. Pour toute autre valeur GUID, le processus de fabrique MCU ne traitera pas le type MCU.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Cet attribut est une liste à plusieurs valeurs de noms uniques (DN). Cet attribut contient la liste de tous les serveurs MCU du même type et fournisseur associé à cette fabrique MCU. La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p>
<p>Lien précédent: ID de lien 11027</p>
<p>Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Cet attribut est une chaîne à valeur unique qui spécifie le média que la MCU peut gérer.</p>
<p>Les types valides pris en charge sont les suivants:</p>
<ul>
<li><p>répond</p></li>
<li><p>audio-vidéo</p></li>
<li><p>salons</p></li>
<li><p>Téléphone-CONF</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Cet attribut est une chaîne à valeur unique qui spécifie le nom d’un fournisseur MCU. Tous les Microsoft MCU doivent spécifier cet attribut en tant que <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsolète)</p></td>
<td><p>Cet attribut définit différentes options de réunion qui sont activées globalement pour tous les utilisateurs ou objets de contact. Cet attribut est une valeur de masque de bits de type entier.</p>
<p>Les valeurs valides (et positions de bits associées) sont les suivantes:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants est défini sur aucun (ne pas autoriser les utilisateurs à inviter des utilisateurs anonymes à des réunions) (aucun bit)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants est tout le monde (permettre à tous les utilisateurs d’inviter des utilisateurs anonymes à des réunions) (position de bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants est UsePerUserSetting (permet aux utilisateurs d’inviter des utilisateurs anonymes à des réunions en fonction de leur paramètre par utilisateur) (position de bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (la stratégie de réunion est définie par l’utilisateur) (position binaire 4)</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsolète)</p></td>
<td><p>Cet attribut spécifie le nom unique (DN) de la stratégie affectée à l’administrateur pour cet utilisateur en tant qu’attribut à valeur unique.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’expiration de l’abonnement de présence minimum.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’inscription minimum.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente la fenêtre délai d’abonnement aux données itinérantes minimum.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Cet attribut est utilisé pour stocker le serveur principal SQL Server utilisé par le pool frontal.</p></td>
<td><p>Nouveautés de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Cet attribut contient des options et des indicateurs qui définissent les paramètres de mobilité.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Cet attribut contient le DN d’un objet de stratégie de mobilité.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsolète)</p></td>
<td><p>Cet attribut représente le nombre autorisé d’appareils sur lesquels un utilisateur peut s’inscrire pour les communications SIP et s’abonner à la présence.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Cet attribut spécifie les options qui sont activées pour l’objet utilisateur ou contact. Cet attribut est une valeur de masquage de type binaire de type entier. Chaque option est représentée par un bit. Cet attribut est marqué pour la réplication de catalogue global.</p>
<p>Les valeurs valides (et positions de bits associées) sont les suivantes:</p>
<ul>
<li><p>1: activé pour la connectivité de messagerie instantanée publique (position de bit 0)</p></li>
<li><p>2: réservé (position binaire 1)</p></li>
<li><p>4: réservé (position binaire 2)</p></li>
<li><p>8: réservé (position binaire 3)</p></li>
<li><p>16: le contrôle d’appel distant a été activé [téléphonie] (position bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permettre aux utilisateurs d’inviter des utilisateurs anonymes à des réunions (position de bit 6)</p></li>
<li><p>128: UCEnabled (permettre aux utilisateurs pour les communications unifiées) (position bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (activer l’utilisateur pour la connectivité de messagerie instantanée publique) (position de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (position binaire 9)</p></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Cet attribut est utilisé dans les topologies de ressources et de forêts centrales pour activer l’authentification unique lorsque l’objet ObjectSID d’un utilisateur à partir du compte principal du serveur Windows NT est copié dans cet attribut de l’objet utilisateur ou contact correspondant dans la ressource ou la forêt centrale. Office Communicator Web Access recherche un utilisateur dans AD DS en utilisant cet attribut ou l’ObjectSID de l’utilisateur. Cet attribut est marqué pour la réplication de catalogue global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Cet attribut est le nom de ressource uniforme (URN) du propriétaire d’un contact d’application.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pattern (obsolète)</p></td>
<td><p>Cet attribut de chaîne à une seule valeur contient un modèle utilisé pour faire correspondre les numéros de téléphone au format E. 164. Si le numéro de téléphone correspond à ce modèle, la traduction est appliquée au numéro composé.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsolète)</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de noms uniques d’itinéraires téléphoniques. Cet attribut spécifie le lien précédent vers un ou plusieurs itinéraires téléphoniques.</p>
<p>Lien précédent: <strong>ID de lien 11033</strong></p>
<p>Cet attribut correspond à la liaison suivante <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsolète)</p></td>
<td><p>Cet attribut de chaîne UNICODE à valeur unique spécifie le nom convivial de l’itinéraire téléphonique, de sorte qu’il puisse facilement être référencé par l’administrateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsolète)</p></td>
<td><p>Cet attribut est une chaîne Unicode à valeur unique. Cet attribut de chaîne contient la définition de la stratégie au format XML. La définition de schéma XML est courante dans les différents types de stratégies, seuls les paramètres sont différents pour chaque type de stratégie.</p>
<p>La définition de schéma XML (XSD) est définie comme suit:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsolète)</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsolète)</p></td>
<td><p>Cet attribut de chaîne Unicode à valeur unique contient le type de stratégie. Les types de stratégie valides sont les suivants:</p>
<ul>
<li><p>répond</p></li>
<li><p>téléphonie</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Cet attribut spécifie un lien vers le pool auquel appartient un ordinateur. Cet attribut est défini, que l’ordinateur exécute l’édition standard ou l’édition Enterprise de Lync Server. Cet attribut est marqué pour la réplication de catalogue global.</p>
<p>La valeur valide est le nom de domaine du pool.</p>
<p>Lien suivant: <strong>ID de lien 11022</strong></p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Il s’agit d’un attribut à valeurs multiples qui contient une liste de noms uniques (DN) de pools avec lesquels la fabrique MCU est associée.</p>
<p>Lien précédent: <strong>ID de lien 11025</strong></p>
<p>Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Cet attribut spécifie un nom arbitraire pour un pool affiché par la console de gestion. Ce nom peut être modifié par l’administrateur.</p>
<p>La valeur valide est une chaîne qui représente le nom d’un pool.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Cet attribut est une valeur de chaîne à valeur unique. La valeur de cet attribut, le cas échéant, représente le nom de domaine complet (FQDN) du pool si l’administrateur souhaite créer un pool frontal avec un nom de domaine complet qui n’est pas conforme à la structure de domaine Active Directory (par exemple, un SIP). espace de noms disjoint de l’espace de noms DNS (Domain Name System).</p>
<p>Nous vous recommandons de mapper le nom de domaine complet (FQDN) du pool frontal à la partie nom de domaine en tant que domaine Active Directory dans lequel réside le pool. Par conséquent, quand aucune valeur n’est présente dans cet attribut, le nom de domaine complet du pool frontal est défini par défaut sur la structure de nom de domaine Active Directory, tel qu’il est indiqué par l’attribut <strong>dNSHostName</strong> .</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Liste à plusieurs valeurs des noms de domaine de tous les serveurs Lync Server Enterprise Edition associés à un pool. Cet attribut de type entier détermine si le pool est compatible avec la messagerie instantanée (mi) et la présence et les réunions.</p>
<p>Les types de valeurs valides possibles sont les suivants:</p>
<ul>
<li><p>Non défini: service de messagerie instantanée et de présence (Live Communications Server 2005 et 2003)</p></li>
<li><p>1: service de messagerie instantanée et de présence (Lync Server)</p></li>
<li><p>2: messagerie instantanée, présence et service de réunion (Lync Server)</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Cet attribut spécifie si un pool de serveurs exécute Standard Edition Server ou Server Enterprise Edition Server. Cet attribut est une valeur de masquage de type binaire de type entier. Chaque option est représentée par un bit.</p>
<p>Les valeurs valides (et positions de bits associées) sont les suivantes:</p>
<ul>
<li><p>1: Standard Edition Server, hébergement des utilisateurs (position de bit 0)</p></li>
<li><p>2: serveur Enterprise Edition, hébergement des utilisateurs (position binaire 1)</p></li>
<li><p>4: Standard Edition Server et applications hébergées (position binaire 2)</p></li>
<li><p>8: serveur Enterprise Edition, applications d’hébergement (position de bit 3)</p></li>
</ul>
<p>Dans la mesure où Lync Server ne prend pas en charge les pools hébergeant uniquement des applications, les seules valeurs valides sont les suivantes:</p>
<ul>
<li><p>5: Standard Edition Server, hébergement des utilisateurs et des applications (positions de bit 0 et 2)</p></li>
<li><p>10: serveur Enterprise Edition, héberge les utilisateurs et les applications (emplacements des points 1 et 3)</p></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Cet attribut définit la version du pool. Il s’agit d’un type entier qui est incrémenté avec chaque version de produit majeure.</p>
<p>Les types de valeurs valides possibles sont les suivants:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 avec SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Cet attribut contient des options et des indicateurs permettant de définir les paramètres de présence.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Cet attribut contient le DN d’un objet de stratégie de présence.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Cet attribut autorise un utilisateur ou un contact à la messagerie SIP. Il est ajouté à la classe contact, car dans la topologie centrale de la forêt, les objets de contact, pas les objets utilisateur, sont activés par SIP.</p>
<p>La valeur valide est le nom de domaine principal du serveur Standard Edition Server ou du pool frontal d’Enterprise Edition dans lequel un utilisateur est hébergé.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Cet attribut contient l’adresse SIP d’un utilisateur donné.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Cet attribut contient l’ID d’appareil de l’appareil de lignes privées.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-routable</p></td>
<td><p>Cet attribut est un attribut booléen utilisé pour déterminer si Lync Server est autorisé à router vers ce service en utilisant son adresse GRUU. Si cette valeur est définie sur <strong>true</strong>, Lync Server est autorisé à effectuer le routage vers ce service. Si cette valeur est définie sur <strong>false</strong>, le serveur Lync n’est pas autorisé à router vers ce service.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsolète)</p></td>
<td><p>Cet attribut de chaîne UNICODE à valeur unique définit un attribut qui qualifie l’utilisation pour un itinéraire téléphonique. La sélection d’un itinéraire de téléphone est déterminée en fonction de deux éléments: l’attribut utilisation attribué à l’itinéraire du téléphone et les attributs d’utilisation de stratégie autorisés de l’appelant. Le premier itinéraire téléphonique avec un attribut utilisation qui correspond à l’utilisation autorisée de l’appelant est sélectionné.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsolète)</p></td>
<td><p>Cet attribut de nom unique (DN) à valeurs multiples contient une liste des noms uniques de l’itinéraire.</p>
<p>Lien suivant: <strong>ID de lien 11032</strong></p>
<p>Cet attribut est un lien de transfert vers la liaison de renvoi correspondante de <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Cet attribut contient le DN qui pointe vers le pool sur lequel tout le trafic SIP adressé à ce MCU ou à ce service approuvé doit traverser.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsolète)</p></td>
<td><p>Cet attribut de chaîne UNICODE à valeur unique spécifie le nom convivial de la règle de normalisation, afin qu’il puisse facilement être référencé par un administrateur.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Cet attribut représente la version de schéma actuellement déployée au sein de l’organisation.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsolète)</p></td>
<td><p>Cet attribut limite le nombre de résultats de recherche à retourner à partir d’une recherche dans l’annuaire lorsqu’un utilisateur recherche un contact à l’aide de Communicator. Cet attribut remplace la valeur fournie par le client.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsolète)</p></td>
<td><p>Cet attribut limite le nombre de demandes de recherche renvoyées.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Cet attribut à valeurs multiples est un lien précédent contenant une liste de noms uniques (DN). Ces DN pointent vers un objet pool ou <strong>TrustedService</strong> .</p>
<p>Cet attribut correspond à la liaison suivante <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsolète)</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de noms uniques. Ces noms uniques sont des liens de retour qui font référence à d’autres objets serveur qui peuvent être affectés à un profil d’emplacement par défaut.</p>
<p>Lien précédent: <strong>ID de lien 11037</strong></p>
<p>Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Cet attribut de lien précédent fait référence uniquement aux pools et aux serveurs de médiation.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Cet attribut définit les informations de version du serveur. Ce numéro de version s’applique à tous les rôles de serveur. Il s’agit d’un entier monotonously croissant qui s’incrémente avec chaque publication officielle du produit.</p>
<p>Les valeurs valides possibles sont les suivantes:</p>
<ul>
<li><p>Non défini: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 avec SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Cet attribut à une seule valeur de type entier spécifie le type d’objet sur lequel pointe <strong>MSDS-SourceObjectDN</strong> , comme suit:</p>
<ul>
<li><p>null | 0x00000001: représente un objet utilisateur principal du serveur Windows NT d’une autre forêt</p></li>
<li><p>Les attributs suivants représentent un type de groupe à partir d’une autre forêt pour l’extension du groupe de distribution:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: représente un objet de standard automatique ou d’accès d’abonné de la même forêt ou d’une autre forêt.</p></li>
</ul></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Cet attribut vous permet de déplacer un utilisateur ou un objet contact d’un pool de serveurs Lync vers un autre. Cet attribut est ajouté à la classe contact en raison de l’activation de l’option SIP dans la topologie centrale de la forêt.</p>
<p>La valeur valide est le nom d’utilisateur de l’emplacement du serveur Standard Edition Server ou du pool frontal vers lequel un utilisateur doit être déplacé.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsolète)</p></td>
<td><p>Cet attribut de chaîne à une seule valeur contient un modèle de numéro de téléphone ou une plage pour diriger vers les passerelles spécifiées définies dans <strong>msRTCSIP-passerelles</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Cet attribut stocke les paires nom-valeur pour les stratégies cibles pour les utilisateurs de Lync Server.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-IDClient</p></td>
<td><p>Cet attribut stocke l’identificateur unique d’un client.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-traduction (obsolète)</p></td>
<td><p>Cet attribut est utilisé par la fonctionnalité voix de Lync Server et contient la chaîne de traduction à appliquer sur le numéro composé, si une correspondance est trouvée.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Cet attribut est une valeur de chaîne qui contient le nom de domaine complet de la MCU. Il s’agit d’un attribut à valeur unique. La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Cet attribut est une valeur de chaîne contenant le nom de domaine complet du serveur proxy exécutant. Cet attribut a une valeur unique. La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Cet attribut est un attribut à valeur unique qui représente le nom de domaine complet d’un serveur approuvé.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Cet attribut spécifie le numéro de version d’un serveur dans la liste des serveurs approuvés.</p>
<p>Les valeurs valides possibles sont les suivantes:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nouveautés de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Cet attribut définit les options qui sont activées pour le service approuvé.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de noms uniques (ND) qui font référence à un objet de service approuvé, tel qu’un service d’authentification par relais de média. Un service d’authentification de relais de média (physiquement localisé sur le serveur Edge exécutant le service de conférence A/V) doit être associé à un pool pour prendre en charge les scénarios audio des utilisateurs distants.</p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>CITÉ</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Cet attribut est un entier qui définit le numéro de port utilisé pour la connexion à ce service GRUU.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Cet attribut est une valeur de chaîne qui définit le type de service GRUU qu’il représente.</p>
<p>Les types de services GRUU valides sont les suivants:</p>
<ul>
<li><p>Le serveur de médiation</p></li>
<li><p>Passerelle</p></li>
<li><p>Service d’authentification de relais de média (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Cet attribut est une valeur de chaîne qui contient le nom de domaine complet (FQDN) du serveur IIS exécutant les services Web de Lync Server. Il s’agit d’un attribut à valeur unique. La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsolète)</p></td>
<td><p>Cet attribut définit différentes options de communications unifiées qui sont activées globalement pour tous les objets utilisateur ou contact. Cet attribut est une valeur de masque de bits de type entier. Chaque option est représentée par la présence d’un bit.</p>
<p>La valeur valide possible (et la position de bit associée) sont les suivantes:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (position binaire 2)</p></li>
</ul>
<p>Lorsque ce bit est défini, la stratégie de Cu est définie par l’utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient le nom unique (DN) de la stratégie de Cu attribuée par l’administrateur pour cet utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsolète)</p></td>
<td><p>Cet attribut fournit une liste de tous les domaines d’une forêt qui hébergent des utilisateurs compatibles SIP. La valeur par défaut est une liste vide, ce qui signifie que tous les domaines de la forêt sont compatibles SIP.</p>
<p>Les valeurs valides sont des chaînes multiples qui représentent le nom de domaine de chaque domaine.</p></td>
<td><p>Nouveautés de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Cet attribut détermine si l’utilisateur est actuellement activé pour Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Cet attribut à valeurs multiples contient une liste de paires nom-valeur au format de &quot;nom = valeur. &quot; Cet attribut est marqué pour la réplication de catalogue global.</p></td>
<td><p>Nouveautés de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Cet attribut contient le nom unique (DN) qui pointe vers un objet de profil d’emplacement.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Cet attribut stocke les paires nom-valeur pour les stratégies utilisateur.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Il s’agit d’un attribut à valeurs multiples contenant une liste de noms uniques avec des valeurs binaires (DN_WITH_BINARY) pointant vers des stratégies utilisateur globales de différents types. La partie binaire indique le type de stratégie auquel la partie du DN pointe.</p>
<p>Les valeurs binaires valides sont les suivantes:</p>
<ul>
<li><p>0x00000001: stratégie de réunion</p></li>
<li><p>0x00000002: stratégie d’UC</p></li>
<li><p>0x00000005: politique de présence</p></li>
</ul></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Il s’agit de l’ID du groupe de routage SIP. Les utilisateurs du même groupe seront enregistrés sur le même serveur principal.</p></td>
<td><p>Nouveautés de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Il s’agit d’un attribut à valeurs multiples. Cet attribut est réservé pour une utilisation ultérieure.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Cet attribut à valeur unique pointe vers le pool ou le serveur Standard Edition auquel appartiennent les composants Web.</p>
<p>Lien suivant: <strong>ID de lien 11028</strong></p>
<p>Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Cet attribut est une liste à plusieurs valeurs de noms uniques. Cet attribut contient la liste de tous les serveurs Web associés à ce pool.</p>
<p>Lien précédent: <strong>ID de lien 11029</strong></p>
<p>Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveautés de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Cet attribut Active Directory existant est utilisé par la téléphonie pour spécifier la liste d’adresses IP supplémentaires pour un téléphone.</p></td>
<td><p>Nouveauté du système d’exploitation Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Cet attribut Active Directory existant est utilisé par les composants vocaux de Lync Server, uniquement pour les objets contact, dans le but de router les appels vers les numéros d’accès d’abonné et de standard de messagerie unifiée. L’adresse de transfert d’appel sans condition est stockée dans cet attribut à valeurs multiples. Ce compte est créé pour l’objet spécifique du standard automatique et de l’accès abonné. Les attributs de ce compte ne doivent pas être modifiés par les administrateurs.</p></td>
<td><p>Nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Cet attribut multivaleur Active Directory existant fait partie du schéma Active Directory de base introduit dans Windows 2000. Cet attribut contient les différentes adresses x400, X500 et SMTP de l’adresse de messagerie de l’utilisateur. Dans Live Communications Server 2003 et versions ultérieures, l’URI SIP de l’utilisateur est ajouté à cette liste &quot;à l'&quot; aide de la balise SIP:.</p>
<p>Les applications suivantes recherchent l’URI SIP de l’utilisateur à partir de cet attribut:</p>
<ul>
<li><p>Client de messagerie et de collaboration de Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Cet attribut Active Directory existant contient le numéro de téléphone de l’utilisateur.</p></td>
<td><p>Nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

