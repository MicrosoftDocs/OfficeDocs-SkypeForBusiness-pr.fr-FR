---
title: Attributs et descriptions de schéma dans Lync Server 2013
TOCTitle: Attributs et descriptions de schéma dans Lync Server 2013
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412841(v=OCS.15)
ms:contentKeyID: 49298560
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attributs et descriptions de schéma dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit l’ensemble des attributs de schéma utilisés par Lync Server 2013. Pour connaître les classes associées aux attributs, voir [Attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Pour afficher une liste des classes et des attributs qui sont des nouveautés de Lync Server 2013, voir [Modifications de schéma dans Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Les attributs appartenant à des paires liées sont spécifiés en tant que liens avant ou liens arrière. Un attribut qui fait référence à un autre objet est un lien avant, tandis que l’attribut de l’objet cible qui fait référence au premier objet est un lien arrière. Les liens avant peuvent être mis à jour, contrairement aux liens arrière qui sont en lecture seule.

Certains attributs ont une valeur masque de bits. Pour ces attributs, chaque paramètre est représenté par un bit et la valeur décimale affichée représente la position du bit. Les positions des bits commencent par le bit 0. 1 (binaire) correspond au bit 0 défini et 10000 (binaire) au bit 4 défini. Chaque bit représente une propriété. Voici quelques exemples :

  - 10000 (binaire) a une valeur décimale de 16 (le bit 4 est défini).

  - 100000000 (binaire) a une valeur décimale de 256 (le bit 8 est défini).

  - 1100 (binaire) a une valeur décimale de 12 (les bits 2 et 3 sont définis ; les propriétés représentées par les deux bits sont activées).

  - 1111000001 (binaire) a une valeur décimale de 961 (les bits 0, 6, 7, 8 et 9 sont définis ; les propriétés pour chacun de ces bits sont activées).

### Attributs de schéma pour Lync Server 2013

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
<td><p>Attribut existant dans services de domaine Active Directory, désormais associé aux classes <strong>msRTCSIP-Pool</strong> et <strong>msRTCSIP-MonitoringServer</strong>. Cet attribut spécifie le nom de domaine complet (FQDN) d’un pool ou d’un serveur de surveillance.</p>
<p>Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Cet attribut contient la représentation sous forme de chaîne du nom unique (DN) de l’objet, situé dans une autre forêt, qui correspond à cet objet. Cet attribut est utilisé pour le développement des groupes de distribution et le standard automatique. Il est défini dans le schéma Active Directory par défaut de Windows Server 2003 R2.</p>
<p>Pour éviter la nécessité d’une mise à niveau des services de domaine Active Directory vers Windows Server 2003 R2, la procédure de préparation du schéma Active Directory étend le schéma Windows Server 2003 à l’aide de cette définition d’attribut.</p></td>
<td><p>Nouveauté de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Cet attribut qui gère plusieurs valeurs contient les paramètres de messagerie vocale. Il est partagé avec la messagerie unifiée Exchange.</p></td>
<td><p>Nouveauté de Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur. Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension. Cet attribut est partagé avec Exchange 2013.</p></td>
<td><p>Nouveauté de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Cet attribut stocke les informations sur les fournisseurs de services d’audioconférence pour un utilisateur.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Cet attribut pointe sur l’entrée de service approuvé pour le contact d’application.</p></td>
<td><p>Nouveauté de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Cet attribut contient une liste des applications hébergées sur le serveur d’applications.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Cet attribut spécifie les options pour le contact d’application.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Cet attribut contient la langue principale pour le contact d’application.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient les langues secondaires pour le contact d’application.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Cet attribut contient une liste de serveurs d’applications appartenant à ce pool. Le lien avant correspondant à cet attribut de lien arrière est <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Cet attribut pointe vers le pool auquel appartient ce serveur d’applications. Il s’agit du lien avant. Le lien arrière correspondant est <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsolète)</p></td>
<td><p>Cet attribut spécifie la valeur par défaut globale, dans les limites de la forêt, déterminant si les communications de tous les utilisateurs doivent être archivées ou non. Il est appliqué par la couche de l’agent d’archivage. Les valeurs prises en charge pour cet attribut sont les suivantes :</p>
<ul>
<li><p><strong>TRUE</strong> : archiver tous les utilisateurs</p></li>
<li><p><strong>FALSE</strong> : ne pas archiver tous les utilisateurs</p></li>
</ul>
<p>Cet attribut permet de vérifier globalement, dans les limites de la forêt, le mode d’archivage des communications des utilisateurs d’un réseau interne.</p>
<p><strong>Comportement de Live Communications Server 2005 (obsolète)</strong></p>
<p>Les valeurs prises en charge pour cet attribut sont les suivantes :</p>
<ul>
<li><p>0 : archiver le corps du message [bit 0]</p></li>
<li><p>1 : ne pas archiver le corps du message [bit 0]</p></li>
</ul>
<p><strong>Comportement d’Office Communications Server 2007</strong></p>
<p>Les valeurs prises en charge pour cet attribut sont les suivantes :</p>
<ul>
<li><p>0 : ArchiveFederationDefaultWithoutBody (obsolète)</p></li>
<li><p>1-2 : ArchiveInternalCommunications</p></li>
<li><p>3-4 : ArchiveFederatedCommunications</p></li>
<li><p>5 : RecordPresenceRegistrations</p></li>
<li><p>6 : RecordIMCallDetails</p></li>
<li><p>7 : RecordGroupIMCallDetails</p></li>
<li><p>8 : RecordFileTransferInstances</p></li>
<li><p>9 : RecordAudioCallDetails</p></li>
<li><p>10 : RecordVideoCallDetails</p></li>
<li><p>11 : RecordRemoteAssistanceCallDetails</p></li>
<li><p>12 : RecordApplicationSharingDetails</p></li>
<li><p>13 : RecordMeetingInstantiations</p></li>
<li><p>14 : RecordMeetingJoins</p></li>
<li><p>15 : RecordDataJoins</p></li>
<li><p>16 : RecordAVJoins</p></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Cet attribut est un entier utilisé comme champ bit pour contrôler si les communications d’un utilisateur sont archivées. Ce contrôle est appliqué par la couche de l’agent d’archivage. Il est identifié pour la réplication des catalogues globaux.</p>
<p>Cet attribut est spécifique à un utilisateur ou contact unique. Les valeurs (et les positions des bits associées) prises en charge dans Lync Server sont les suivantes :</p>
<ul>
<li><p>0 : ne pas archiver (aucun bit défini)</p></li>
<li><p>1 : obsolète (position de bit 0)</p></li>
<li><p>2 : obsolète (position de bit 1)</p></li>
<li><p>4 : archiver les communications internes (position de bit 2)</p></li>
<li><p>8 : archiver les communications fédérées (position de bit 3)</p></li>
</ul>
<p>Les valeurs précédemment prises en charge dans Live Communications Server 2005 sont les suivantes :</p>
<ul>
<li><p>0 : utiliser la valeur par défaut définie par <strong>msRTCSIP-ArchiveDefault</strong> et <strong>msRTCSIP-ArchiveFederation</strong> dans cet ordre de priorité :</p>
<ul>
<li><p>1 : archiver</p></li>
<li><p>2 : ne pas archiver</p></li>
<li><p>3 : archiver sans le corps du message</p></li>
</ul></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsolète)</p></td>
<td><p>Cet attribut définit la version du service d’archivage. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit. Les valeurs prises en charge sont les suivantes :</p>
<ul>
<li><p>Non défini : Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 avec SP1</p></li>
<li><p>3 : Office Communications Server 2007</p></li>
<li><p>4 : Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Cet attribut indique le nom de domaine complet du serveur principal du pool. Étant donné qu’il ne peut exister qu’un serveur principal par pool, il s’agit d’un attribut à valeur unique.</p>
<p>Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Cet attribut contient l’identificateur du pool qui héberge l’annuaire de conférences.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Cet attribut contient l’identificateur d’un annuaire de conférences.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Cet attribut contient l’identificateur du pool vers lequel l’annuaire de conférences est déplacé.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Default</p></td>
<td><p>Cet attribut booléen définit si l’utilisation téléphonique est une utilisation par défaut. Si la valeur est <strong>TRUE</strong>, l’utilisation téléphonique est une utilisation par défaut et ne peut pas être supprimée par l’administrateur. Si la valeur est <strong>FALSE</strong>, l’utilisation peut être supprimée.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Cet attribut indique l’URL de Communicator Web Access pour les utilisateurs qui se trouvent à l’extérieur de l’organisation.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Cet attribut indique l’URL de Communicator Web Access pour les utilisateurs qui se trouvent à l’intérieur de l’organisation.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient le nom unique (DN) d’un objet de classe de profil d’emplacement qui lui est affecté.</p>
<p>Lien avant : <strong>ID de lien 11036</strong></p>
<p>Le lien arrière correspondant est <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsolète)</p></td>
<td><p>Cet attribut booléen indique si la stratégie est une stratégie par défaut. C’est le cas lorsque l’attribut a la valeur <strong>TRUE</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsolète)</p></td>
<td><p>Cet attribut indique le nom de domaine complet du serveur Edge exécutant le service Edge d’accès (s’il est accessible directement) ou du programme d’équilibrage de la charge matérielle pour un pool de serveurs exécutant le service Edge d’accès. Si les serveurs exécutant le service Edge d’accès ne sont accessibles que via un ou plusieurs directeurs, cet attribut spécifie le nom de domaine complet et, à titre facultatif, le numéro de port du directeur ou du programme d’équilibrage de la charge matérielle d’un pool directeur.</p>
<p>Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsolète)</p></td>
<td><p>Cet attribut représente le numéro de port qui doit être utilisé pour la connexion au serveur exécutant le service Edge d’accès.</p>
<p>La valeur correcte est un nombre entier spécifiant le port à utiliser. La valeur par défaut est 5061.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration par défaut de l’abonnement aux informations de présence.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration d’inscription par défaut.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration par défaut de l’abonnement aux données d’itinérance.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Cet attribut est utilisé dans une topologie de domaine fractionné et contient un nom de domaine complet (FQDN).</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsolète)</p></td>
<td><p>Cet attribut de type chaîne UNICODE à valeur unique contient une description conviviale de cet itinéraire téléphonique ou de cette règle de normalisation.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Cet attribut représente un domaine configuré pour le serveur d’inscriptions.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Cet attribut indique le nom de domaine complet du serveur exécutant le service Edge d’accès.</p>
<p>Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsolète)</p></td>
<td><p>Cet attribut détermine si un serveur génère une demande BENOTIFY (Best Effort NOTIFY), plutôt qu’une demande NOTIFY, en réponse à la demande SUBSCRIBE envoyée par un client. BENOTIFY est une extension d’amélioration des performances du protocole de transfert de notification de l’inscription dans laquelle le serveur génère des demandes BENOTIFY, plutôt que des demandes NOTIFY normales. Les performances sont améliorées dans la mesure où une demande BENOTIFY ne nécessite pas de réponse 200 OK d’un client, contrairement à la demande NOTIFY.</p>
<p>La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</p>

> [!NOTE]  
> Live Communications Server 2003 ne prend pas en charge les demandes BENOTIFY. Pour interagir avec les applications de serveur écrites à l’aide des API du serveur Live Communications Server 2003 exécutant Live Communications Server 2005 et les serveurs tiers, vous pouvez désactiver les demandes BENOTIFY en définissant la valeur sur <strong>FALSE</strong>. Actuellement, cette fonction ne fait pas partie du processus de standardisation SIP IETF (Internet Engineering Task Force).

</td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsolète)</p></td>
<td><p>Cet attribut est un commutateur global utilisé par les administrateurs informatiques pour déterminer si les utilisateurs sont autorisés ou non à communiquer avec ceux d’autres organisations. Il permet à un administrateur de remplacer l’attribut <strong>FederationEnabled</strong> d’un utilisateur. Cet attribut peut être utile pour protéger le réseau interne contre les attaques en provenance d’Internet pouvant être causées par des vers ou des virus, ou encore contre les attaques ciblées contre la société.</p>
<p>Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</p>
<ul>
<li><p>1 : activé pour la solution PIC (position de bit 0)</p></li>
<li><p>2 : réservé (position de bit 1)</p></li>
<li><p>4 : réservé (position de bit 2)</p></li>
<li><p>8 : réservé (position de bit 3)</p></li>
<li><p>16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</p></li>
<li><p>64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</p></li>
<li><p>128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</p></li>
<li><p>256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</p></li>
<li><p>512 : RemoteCallControlDualMode (position de bit 9)</p></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Cet attribut indique si les services d’entreprise sont chargés sur un serveur donné.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Cet attribut contient l’indicatif pour l’accès externe.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Cet attribut permet de contrôler si un utilisateur unique est activé pour la fédération. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</p>
<p>La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient les noms de domaines de tous les serveurs Enterprise Edition associés à un pool.</p>
<p>Lien arrière : <strong>ID de lien 11023</strong></p>
<p>Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (obsolète)</p></td>
<td><p>Cet attribut de type chaîne gérant plusieurs valeurs contient une liste de passerelles et de ports (par passerelle).</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsolète)</p></td>
<td><p>Cet attribut permet de stocker les paires nom:valeur. La paire nom:valeur déjà définie correspond au paramètre <strong>autoriser l’interrogation de présence</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Cet attribut est un identificateur unique d’un groupe utilisé pour regrouper les entrées de carnet d’adresses.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003 (non utilisé).</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003 (non utilisé).</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Cet attribut permet de contrôler si un utilisateur unique est activé pour l’accès des utilisateurs extérieurs. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</p>
<p>La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Line</p></td>
<td><p>Cet attribut à valeur unique contient l’ID de périphérique (URI SIP ou URI TEL du téléphone contrôlé par l’utilisateur) utilisé par Lync à des fins de téléphonie. Il est identifié pour la réplication des catalogues globaux et est indexé. Si un utilisateur est activé pour Voix Entreprise, cet attribut stocke la version normalisée E.164 du numéro de téléphone de l’utilisateur.</p></td>
<td><p>Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Cet attribut à valeur unique contient l’URI SIP du serveur de passerelle CSTA-SIP. Il est identifié pour la réplication des catalogues globaux mais n’est pas indexé.</p></td>
<td><p>Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsolète)</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des règles de normalisation locales associés à ce profil d’emplacement. Ce type d’attribut est un attribut binaire de nom unique. Il existe une relation un à plusieurs entre le profil d’emplacement et les règles de normalisation locales. L’ordre des noms uniques des règles de normalisation locales doit correspondre à l’ordre défini par l’administrateur. La conservation de cet ordre est assurée par la partie binaire de l’attribut binaire de nom unique, qui définit l’index de classement.</p>
<p>Lien avant : <strong>ID de lien 11034</strong></p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Cet attribut contient une liste d’options pour la règle de normalisation.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient le nom convivial du profil d’emplacement qui indique l’emplacement représenté par le profil. Comme il peut exister plusieurs profils d’emplacement, l’administrateur doit être en mesure de les distinguer.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsolète)</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient la liste des noms uniques de profil d’emplacement. Il indique le lien arrière d’un ou plusieurs profils d’emplacement.</p>
<p>Lien arrière : <strong>ID de lien 11035</strong></p>
<p>Cet attribut correspond au lien avant <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Cet attribut contient les options pour le profil d’emplacement.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de contacts d’application.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de profils d’emplacement.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsolète)</p></td>
<td><p>Cet attribut représente le nombre maximal de demandes de recherches actives par serveur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsolète)</p></td>
<td><p>Cet attribut représente le nombre maximal d’abonnements par utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration maximal d’abonnement.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration maximal d’inscription.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration maximal d’abonnement aux données d’itinérance.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Cet attribut est un attribut de point de contrôle du service sous la classe d’ordinateur qui définit un lien renvoyant à son répartiteur d’unité de contrôle multipoint (MCU) parent. Le point de contrôle du service et l’attribut sont créés pour chaque MCU Microsoft. Chaque MCU Microsoft doit trouver le serveur principal du pool auquel il appartient afin d’en extraire des paramètres de niveau pool.</p>
<p>La valeur de cet attribut est le nom unique (DN) du répartiteur de MCU. Il s’agit d’un attribut à valeur unique identifié pour la réplication des catalogues globaux.</p>
<p>Lien avant : <strong>ID de lien 11026</strong></p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Il s’agit d’un attribut réservé de type chaîne gérant plusieurs valeurs. Les paramètres qui y sont stockés sont représentés par des paires nom=valeur. Les paires nom=valeur actuellement définies sont les suivantes :</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Cet attribut à valeur unique contient le nom unique (DN) d’un répartiteur de MCU unique associé à un pool.</p>
<p>Lien avant : <strong>ID de lien 11024</strong></p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Cet attribut de type chaîne à valeur unique spécifie le GUID du fournisseur du répartiteur de MCU. Selon la valeur du GUID, le répartiteur de MCU détermine s’il doit traiter ce type de MCU. Si la valeur du GUID est <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, le processus du répartiteur de MCU (disponible par défaut dans Lync Server) traite ce type de MCU. Dans le cas contraire, il ne traite pas le type de MCU.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN), à savoir la liste de tous les serveurs MCU de même type et fournisseur associés à ce répartiteur de MCU. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p>
<p>Lien arrière : ID de lien 11027</p>
<p>Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Cet attribut de type chaîne à valeur unique spécifie le support géré par le MCU.</p>
<p>Les types de valeurs gérés sont les suivants :</p>
<ul>
<li><p>réunion ;</p></li>
<li><p>audio-vidéo ;</p></li>
<li><p>conversation ;</p></li>
<li><p>conférence téléphonique.</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Cet attribut de type chaîne à valeur unique représente le nom d’un fournisseur de MCU. Pour tous les MCU Microsoft, cet attribut a la valeur <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsolète)</p></td>
<td><p>Cet attribut définit différentes options de réunion qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier.</p>
<p>Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</p>
<ul>
<li><p>0 : AllowOrganizeMeetingWithAnonymousParticipants a pour valeur Aucun (ne pas autoriser les utilisateurs à inviter des utilisateurs anonymes à des réunions) (aucun bit défini)</p></li>
<li><p>4 : AllowOrganizeMeetingWithAnonymousParticipants a pour valeur Tout le monde (permet à tous les utilisateurs d’inviter des utilisateurs anonymes à des réunions) (position de bit 2)</p></li>
<li><p>8 : AllowOrganizeMeetingWithAnonymousParticipants a la valeur UsePerUserSetting (permet aux utilisateurs d’inviter des utilisateurs anonymes à des réunions en fonction du paramètre par utilisateur) (position de bit 3)</p></li>
<li><p>16 : UserPerUserMeetingPolicy (la stratégie de réunion est définie par utilisateur) (position de bit 4)</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsolète)</p></td>
<td><p>Cet attribut définit le nom unique (DN) de la stratégie que l’administrateur a attribué à cet utilisateur sous la forme d’un attribut à valeur unique.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration minimal d’abonnement aux informations de présence.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration minimal d’inscription.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolète)</p></td>
<td><p>Cet attribut représente le délai d’expiration minimal de l’abonnement aux données d’itinérance.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Cet attribut est utilisé pour stocker le serveur SQL Server principal en miroir utilisé par le pool de serveurs frontaux.</p></td>
<td><p>Nouveauté de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Cet attribut contient des options et des indicateurs qui définissent les paramètres de mobilité.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Cet attribut contient le nom unique pour un objet de stratégie de mobilité.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsolète)</p></td>
<td><p>Cet attribut représente le nombre autorisé de périphériques sur lesquels un utilisateur peut s’inscrire pour les communications SIP et s’abonner aux données de présence.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Cet attribut définit les options qui sont activées pour l’objet utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit. Il est identifié pour la réplication des catalogues globaux.</p>
<p>Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</p>
<ul>
<li><p>1 : activé pour la solution PIC (position de bit 0)</p></li>
<li><p>2 : réservé (position de bit 1)</p></li>
<li><p>4 : réservé (position de bit 2)</p></li>
<li><p>8 : réservé (position de bit 3)</p></li>
<li><p>16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</p></li>
<li><p>64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</p></li>
<li><p>128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</p></li>
<li><p>256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</p></li>
<li><p>512 : RemoteCallControlDualMode (position de bit 9)</p></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Cet attribut est utilisé dans les topologies à forêts de ressources et à forêt centrale pour activer l’authentification unique lorsque l’identificateur ObjectSID du compte principal Windows NT Server d’un utilisateur est copié dans ce même attribut de l’objet utilisateur ou contact correspondant dans la forêt de ressources ou la forêt centrale. Communicator Web Access recherche un utilisateur dans Active Directory à l’aide de cet attribut ou de l’identificateur ObjectSID de l’utilisateur. Il est identifié pour la réplication des catalogues globaux.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Cet attribut est l’URN (Uniform Resource Name) du propriétaire pour un contact d’application.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (obsolète)</p></td>
<td><p>Cet attribut de type chaîne à valeur unique contient un modèle de correspondance permettant de convertir les numéros à composer au format E.164. La conversion est appliquée à tout numéro correspondant au modèle.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsolète)</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’itinéraires téléphoniques. Il indique le lien arrière d’un ou plusieurs itinéraires téléphoniques.</p>
<p>Lien arrière : <strong>ID de lien 11033</strong></p>
<p>Cet attribut correspond au lien avant <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsolète)</p></td>
<td><p>Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de l’itinéraire téléphonique, qui peut ainsi être facilement référencé par l’administrateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsolète)</p></td>
<td><p>Cet attribut de type chaîne UNICODE à valeur unique contient la définition de stratégie au format XML. La définition de schéma XML est commune à différents types de stratégies ; seuls les paramètres varient en fonction du type de stratégie.</p>
<p>La définition de schéma XML (XSD) est définie de la manière suivante :</p>
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
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsolète)</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsolète)</p></td>
<td><p>Cet attribut de type chaîne Unicode à valeur unique contient le type de stratégie. Les types pris en charge sont les suivants :</p>
<ul>
<li><p>réunion ;</p></li>
<li><p>téléphonie.</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Cet attribut spécifie un lien permettant de revenir au pool auquel appartient un ordinateur. Il est défini que l’ordinateur exécute la version Standard Edition ou Enterprise Edition de Lync Server. Il est identifié pour la réplication des catalogues globaux.</p>
<p>La valeur correcte est le nom de domaine du pool.</p>
<p>Lien avant : <strong>ID de lien 11022</strong></p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des pools auxquels le répartiteur de MCU est associé.</p>
<p>Lien arrière : <strong>ID de lien 11025</strong></p>
<p>Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Cet attribut définit le nom arbitraire d’un pool affiché par la console de gestion. Ce nom peut être modifié par l’administrateur.</p>
<p>La valeur correcte est une chaîne représentant le nom d’un pool.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Cet attribut est de type chaîne UNICODE à valeur unique. Lorsqu’elle est définie, la valeur de cet attribut représente le nom de domaine complet du pool si l’administrateur souhaite créer un pool frontal en lui attribuant un nom de domaine complet non conforme à la structure de domaines Active Directory dans lequel il créé le pool frontal (un espace de noms SIP dissocié de l’espace de noms DNS, par exemple).</p>
<p>Nous vous recommandons de mapper le nom de domaine complet du pool frontal sur la partie de nom de domaine du domaine Active Directory dans lequel réside le pool. Par conséquent, quand la valeur de l’attribut n’est pas définie, le nom de domaine complet du pool frontal correspond par défaut à la structure des noms de domaine Active Directory, telle qu’indiquée par l’attribut <strong>dnsHostName</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Cet attribut gérant plusieurs valeurs définit la liste des noms de domaine de tous les serveurs Lync Server Enterprise Edition associés à un pool. Cet attribut de type nombre entier détermine si le pool prend en charge la messagerie instantanée et les données de présence, ainsi que les réunions.</p>
<p>Les types de valeurs pris en charge sont les suivants :</p>
<ul>
<li><p>Non défini : messagerie instantanée et service de présence (Live Communications Server 2005 et 2003)</p></li>
<li><p>1 : messagerie instantanée et service de présence (Lync Server)</p></li>
<li><p>2 : messagerie instantanée et service de réunion (Lync Server)</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Cet attribut indique si un pool de serveurs exécute Standard Edition Server ou Enterprise Edition Server. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</p>
<p>Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</p>
<ul>
<li><p>1 : Standard Edition Server, héberge des utilisateurs (position de bit 0)</p></li>
<li><p>2 : Enterprise Edition Server, héberge des utilisateurs (position de bit 1)</p></li>
<li><p>4 : Standard Edition Server, héberge des applications (position de bit 2)</p></li>
<li><p>8 : Enterprise Edition Server, héberge des applications (position de bit 3)</p></li>
</ul>
<p>Dans la mesure où Lync Server ne prend pas en charge les pools qui hébergent uniquement des applications, les seules valeurs valides sont les suivantes :</p>
<ul>
<li><p>5 : Standard Edition Server, héberge des utilisateurs et des applications (positions de bit 0 et 2)</p></li>
<li><p>10 : Enterprise Edition Server, héberge des utilisateurs et des applications (positions de bit 1 et 3)</p></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Cet attribut définit la version du pool. Sa valeur est un entier incrémenté à chaque version majeure du produit.</p>
<p>Les types de valeurs pris en charge sont les suivants :</p>
<ul>
<li><p>0 : Live Communications Server 2003</p></li>
<li><p>1 : Live Communications Server 2005</p></li>
<li><p>2 : Live Communications Server 2005 avec SP1</p></li>
<li><p>3 : Office Communications Server 2007</p></li>
<li><p>4 : Office Communications Server 2007 R2</p></li>
<li><p>5 : Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Cet attribut contient des options et des indicateurs qui définissent les paramètres de présence.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Cet attribut contient le nom unique pour un objet de stratégie de présence.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Cet attribut permet d’activer un utilisateur ou un contact pour la messagerie SIP. Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</p>
<p>La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal Enterprise Edition hébergeant un utilisateur.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Cet attribut contient l’adresse SIP d’un utilisateur donné.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Cet attribut contient l’ID de périphérique du périphérique de ligne privée.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Routable</p></td>
<td><p>Cet attribut de type booléen permet de déterminer si Lync Server est autorisé à accéder à ce service par le biais de son adresse GRUU. Si la valeur correspond à <strong>TRUE</strong>, Lync Server est autorisé à accéder à ce service. Si la valeur correspond à <strong>FALSE</strong>, Lync Server n’est pas autorisé à accéder à ce service.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsolète)</p></td>
<td><p>Cet attribut de type chaîne UNICODE à valeur unique définit un attribut qualifiant l’utilisation d’un itinéraire téléphonique. La sélection d’un itinéraire téléphonique est déterminée en fonction de deux éléments : l’attribut d’utilisation affecté à l’itinéraire téléphonique et les attributs d’utilisation de la stratégie autorisée de l’appelant. Le premier itinéraire dont l’attribut d’utilisation correspond à l’utilisation autorisée de l’appelant est sélectionné.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsolète)</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’utilisation d’itinéraire téléphonique.</p>
<p>Lien avant : <strong>ID de lien 11032</strong></p>
<p>Cet attribut est un lien avant correspondant au lien arrière <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Cet attribut contient le nom unique pointant vers le pool par lequel doit transiter tout le trafic SIP destiné à ce MCU ou à ce service approuvé.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsolète)</p></td>
<td><p>Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de la règle de normalisation, qui peut ainsi être facilement référencée par l’administrateur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Cet attribut représente la version du schéma actuellement déployée dans l’organisation.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsolète)</p></td>
<td><p>Cet attribut limite le nombre de résultats renvoyés par une recherche d’annuaire lorsqu’un utilisateur recherche un contact à l’aide de Communicator. Il remplace la valeur fournie par le client.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsolète)</p></td>
<td><p>Cet attribut limite le nombre de demandes de recherche renvoyées.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Cet attribut gérant plusieurs valeurs est un lien arrière qui contient une liste de noms uniques (DN). Ceux-ci pointent vers un pool ou un objet <strong>TrustedService</strong>.</p>
<p>Cet attribut correspond au lien avant <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsolète)</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de noms uniques. Ceux-ci sont des liens secondaires qui référencent d’autres objets Serveur auxquels il est possible d’attribuer un profil d’emplacement par défaut.</p>
<p>Lien arrière : <strong>ID de lien 11037</strong></p>
<p>Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Cet attribut de lien arrière référence uniquement des pools et des serveurs de médiation.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Cet attribut définit la version du serveur. Ce numéro de version s’applique à tous les rôles serveurs. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit.</p>
<p>Les valeurs prises en charge sont les suivantes :</p>
<ul>
<li><p>Non défini : Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 avec SP1</p></li>
<li><p>3 : Office Communications Server 2007</p></li>
<li><p>4 : Office Communications Server 2007 R2</p></li>
<li><p>5 : Lync Server 2010</p></li>
<li><p>6 : Lync Server 2013</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Cet attribut à valeur unique de type entier définit le type d’objet vers lequel pointe <strong>msDS-SourceObjectDN</strong>, comme suit :</p>
<ul>
<li><p>null | 0x00000001 : représente un objet utilisateur principal Windows NT Server issu d’une autre forêt.</p></li>
<li><p>Les attributs suivants représentent un type de groupe issu d’une autre forêt pour le développement des groupes de distribution :</p>
<ul>
<li><p>0x00000002 : ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004 : ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004 : ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008 : ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000 : ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000 : représente un objet standard automatique ou accès abonné de la même forêt ou d’une autre forêt.</p></li>
</ul></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Cet attribut permet de transférer un utilisateur ou un objet contact d’un pool Lync Server à un autre. Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</p>
<p>La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal de destination vers lequel l’utilisateur doit être déplacé.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsolète)</p></td>
<td><p>Cet attribut de type chaîne à valeur unique contient un modèle ou une plage de numéros de téléphone à acheminer vers les passerelles spécifiées, définies dans <strong>msRTCSIP-Gateways</strong>.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Cet attribut permet de stocker les paires nom-valeur des stratégies cibles pour les utilisateurs Lync Server.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Cet attribut stocke l’identificateur unique d’un locataire.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsolète)</p></td>
<td><p>Cet attribut est utilisé par le système vocal de Lync Server et contient la chaîne de conversion à appliquer au numéro composé, si une correspondance est trouvée.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Cet attribut de type chaîne contient le nom de domaine complet du MCU. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Cet attribut de type chaîne contient le nom de domaine complet du serveur exécutant le serveur proxy. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Cet attribut à valeur unique représente le nom de domaine complet d’un serveur approuvé.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Cet attribut définit le numéro de version d’un serveur de la liste de serveurs approuvés.</p>
<p>Les valeurs prises en charge sont les suivantes :</p>
<ul>
<li><p>NULL : Live Communications Server 2003</p></li>
<li><p>2 : Live Communications Server 2005</p></li>
<li><p>3 : Office Communications Server 2007</p></li>
<li><p>4 : Office Communications Server 2007 R2</p></li>
<li><p>5 : Lync Server 2010</p></li>
<li><p>6 : Lync Server 2013</p></li>
</ul></td>
<td><p>Nouveauté de Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Cet attribut définit les options activées pour le service approuvé.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN) référençant un objet service approuvé, tel qu’un service d’authentification Media Relay. Un service de ce type (colocalisé physiquement sur le serveur Edge exécutant le service de conférence A/V) doit être associé à un pool pour assurer la prise en charge des scénarios audio des utilisateurs distants.</p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>Communications unifiées</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Cet attribut est un entier qui définit le numéro de port permettant la connexion à ce service GRUU.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Cet attribut de type chaîne définit le type de service GRUU qu’il représente.</p>
<p>Les types de services GRUU pris en charge sont les suivants :</p>
<ul>
<li><p>MediationServer ;</p></li>
<li><p>Passerelle</p></li>
<li><p>MRAS (Media Relay Authentication Service, service d’authentification Media Relay) ;</p></li>
<li><p>QoSM ;</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Cet attribut de type chaîne contient le nom de domaine complet de l’IIS exécutant les services web Lync Server. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsolète)</p></td>
<td><p>Cet attribut définit différentes options relatives aux communications unifiées qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</p>
<p>Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</p>
<ul>
<li><p>4 : UsePerUserUCPolicy (position de bit 2)</p></li>
</ul>
<p>Lorsque ce bit est activé, la stratégie de communications unifiées est définie par utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsolète)</p></td>
<td><p>Cet attribut à valeur unique contient le nom unique (DN) de la stratégie de communications unifiées que l’administrateur a attribué à cet utilisateur.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsolète)</p></td>
<td><p>Cet attribut recense tous les domaines d’une forêt hébergeant des utilisateurs SIP. La liste est vide par défaut, ce qui indique que tous les domaines de la forêt sont activés pour SIP.</p>
<p>Les valeurs prises en charge sont plusieurs chaînes représentant les noms de domaine spécifiques.</p></td>
<td><p>Nouveauté de Live Communications Server 2005.</p>
<p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Cet attribut détermine si l’utilisateur est actuellement activé pour Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de paires au format « nom=valeur ». Il est identifié pour la réplication des catalogues globaux.</p></td>
<td><p>Nouveauté de Live Communications Server 2005 avec SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Cet attribut contient le nom unique (DN) pointant sur un objet de profil d’emplacement.</p></td>
<td><p>Nouveauté de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Cet attribut permet de stocker les paires nom-valeur des stratégies utilisateur.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de noms uniques avec une partie binaire (DN_WITH_BINARY) pointant vers des stratégies utilisateur globales de différents types. La partie binaire indique le type de stratégie vers laquelle pointe la partie DN.</p>
<p>Les valeurs binaires correctes sont les suivantes :</p>
<ul>
<li><p>0x00000001 : stratégie de réunion</p></li>
<li><p>0x00000002 : stratégie de communications unifiées</p></li>
<li><p>0x00000005 : stratégie de présence</p></li>
</ul></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Cette valeur est l’ID de groupe de routage SIP. Les utilisateurs du même groupe s’inscrivent sur le même serveur frontal.</p></td>
<td><p>Nouveauté de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Cet attribut gère plusieurs valeurs. Cet attribut est réservé à un usage ultérieur.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Cet attribut à valeur unique pointe vers le pool ou le serveur Standard Edition auquel appartiennent les composants web.</p>
<p>Lien avant : <strong>ID de lien 11028</strong></p>
<p>Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-WebComponentsServer</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient une liste de noms uniques répertoriant tous les serveurs web associés à ce pool.</p>
<p>Lien arrière : <strong>ID de lien 11029</strong></p>
<p>Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Nouveauté de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsolète)</p></td>
<td><p>-</p></td>
<td><p>Nouveauté de Live Communications Server 2003.</p>
<p>Obsolète dans Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Cet attribut Active Directory existant est utilisé par la téléphonie pour spécifier la liste des autres adresses TCP/IP d’un téléphone.</p></td>
<td><p>Il s’agit d’une nouveauté du système d’exploitation Windows Server 2008</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Cet attribut Active Directory existant est utilisé par les composants du système vocal de Lync Server pour acheminer les appels vers les numéros de standard automatique ou d’accès abonné de messagerie unifiée. Il est réservé aux objets contact. L’adresse de transfert d’appel inconditionnel est enregistrée dans cet attribut gérant plusieurs valeurs. Ce compte est créé spécifiquement pour le standard automatique et l’accès abonné. Ses attributs ne doivent pas être modifiés par des administrateurs.</p></td>
<td><p>Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Cet attribut Active Directory existant qui gère plusieurs valeurs fait partie du schéma Active Directory de base introduit dans Windows 2000. Il contient les adresses électroniques X400, X500 et SMTP de la messagerie de l’utilisateur. Dans Live Communications Server 2003 et les versions ultérieures, l’URI SIP de l’utilisateur est ajouté à la liste, à l’aide de la balise « sip: ».</p>
<p>Les applications suivantes utilisent cet attribut pour examiner l’URI SIP de l’utilisateur :</p>
<ul>
<li><p>Client de messagerie et de collaboration Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Cet attribut Active Directory existant contient le numéro de téléphone de l’utilisateur.</p></td>
<td><p>Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</p></td>
</tr>
</tbody>
</table>

