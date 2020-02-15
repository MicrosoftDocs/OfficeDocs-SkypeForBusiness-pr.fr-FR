---
title: 'Lync Server 2013 : classes de schéma et descriptions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3063e0dd6288f4b9248c93de57a6182a7ab20a8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Classes de schéma et descriptions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Cette section décrit toutes les classes de schéma utilisées par Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Classes et descriptions de schéma


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Description</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Destinataire de messagerie de messagerie unifiée Exchange.</p></td>
<td><p>Cette classe auxiliaire est partagée avec la messagerie unifiée Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Cette classe est un conteneur de contacts d’application et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Cette classe contient l’entrée correspondant au point de contrôle de service d’une instance des services d’applications de communications unifiées (UCAS).</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Cette classe fournit une association entre un pool spécifique et son service d’application.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-ApplicationServer contient des attributs représentant des paramètres pour les instances du service d’application.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsolète)</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres concernant l’archivage.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsolète)</p></td>
<td><p>Cette classe représente un serveur d’archivage de messagerie instantanée unique. Une instance de cette classe est créée lorsqu’un ordinateur est activé en tant que serveur d’archivage de messagerie instantanée, par exemple un ordinateur sur lequel est installé le service d’archivage de messagerie instantanée.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Cette classe est un conteneur d’instances d’annuaires des conférences et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Cette classe contient des attributs représentant des paramètres réservés à un annuaire des conférences spécifique.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Point de contrôle de service générique (SCP) pour spécifier l’ordinateur en tant que serveur exécutant Lync Server.</p></td>
<td><p>Nouveauté de Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Cette classe auxiliaire contient les paramètres d’une banque Microsoft Lync Web App.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Cette classe contient des attributs qui définissent les domaines configurés du registre SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Ce conteneur de classe représente un service Edge d’accès unique. Étant donné qu’un service Edge d’accès est déployé dans le réseau de périmètre et que les clients n’autorisent généralement pas l’accès aux services de domaine Active Directory à partir du réseau de périmètre, les instances du service Edge d’accès ne sont pas jointes au réseau Active Directory de l’intranet. Par conséquent, les proxys d’accès ne sont pas automatiquement inscrits dans AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-MCU contient des attributs représentant des paramètres réservés aux serveurs de conférence.</p></td>
<td><p>Nouveauté de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-MediationServer contient des attributs représentant des paramètres réservés aux serveurs de médiation.</p></td>
<td><p>Nouveauté d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-Server contient des attributs représentant des paramètres réservés aux serveurs SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres concernant la fédération.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Cette classe contient tous les paramètres qui s’appliquent tout au long d’un déploiement Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsolète)</p></td>
<td><p>Cette classe représente une stratégie de réunion Office Communications Server unique.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Objet local de paramètre de la topologie globale.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Conteneur qui contient les objets de paramètre de la topologie globale.</p></td>
<td><p>Nouveauté de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Cette classe est un conteneur représentant une instance d’une règle de normalisation d’emplacement.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Cette classe est créée par l’application du service Surveillance de conférence et contient les attributs utilisés pour classer les numéros de téléphone de conférence par région.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Cette classe est un conteneur d’instances de mappages de contact d’emplacement et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Cette classe est un conteneur représentant un profil d’emplacement spécifique.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsolète)</p></td>
<td><p>Cette classe est un conteneur de profils d’emplacement et ne possède pas d’attributs propres.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsolète)</p></td>
<td><p>Cette classe est un conteneur de règles de normalisation locales et ne possède pas d’attributs propres.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Cette classe représente un serveur de conférence unique.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Cette classe héberge des classes msRTCSIP-MCUFactory et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Cette classe est un conteneur représentant un répartiteur de serveurs de conférence pour un type de support unique. Une instance de cette classe est créée lorsque le premier serveur de conférence de ce type et fournisseur est activé.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Cette classe fournit une association entre un pool spécifique et son répartiteur de serveurs de conférence.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Cette classe contient l’entrée correspondant au point de contrôle de service d’un serveur de médiation.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (obsolète)</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer possède des attributs représentant des paramètres de réunion configurables.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Conteneur qui stocke les paramètres globaux de mobilité.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Cette classe contient des attributs représentant les paramètres d’un seul serveur de surveillance.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsolète)</p></td>
<td><p>Cette classe est un conteneur représentant une instance de l’itinéraire à moindre coût vers une passerelle ou un ensemble de passerelles. Ces informations sont utilisées par tous les pools ou serveurs d’entreprise ou les serveurs exécutant Standard Edition pour acheminer les appels sortants vers le réseau téléphonique commuté (RTC) de la manière la plus rentable qui soit.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsolète)</p></td>
<td><p>Cette classe est un conteneur d’itinéraires à moindre coût et ne possède pas d’attributs propres.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (obsolète)</p></td>
<td><p>Cette classe contient plusieurs classes de stratégie Lync Server et ne possède pas d’attributs lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pool</p></td>
<td><p>Cette classe représente un pool Lync Server unique.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pools</p></td>
<td><p>Cette classe contient plusieurs pools Lync Server et ne possède pas d’attributs lui-même.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Cette classe représente le point de contrôle de service d’un pool. Les utilisateurs hébergés dans un pool font pointer leur attribut msRTCSIP-PrimaryHomeServer sur une instance de cette classe.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-presence</p></td>
<td><p>Conteneur qui stocke les paramètres globaux de présence.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer contient les attributs représentant les paramètres utilisateur gérés par les serveurs du registre SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsolète)</p></td>
<td><p>Cette classe est un conteneur représentant une instance d’une utilisation d’itinéraire téléphonique. Une classe d’utilisation d’itinéraire téléphonique se compose d’un champ d’attribut et d’un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ de description permet aux administrateurs de décrire l’utilisation de cet attribut dans l’itinéraire téléphonique.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsolète)</p></td>
<td><p>Cette classe contient des instances de la classe msRTCSIP-RouteUsage et ne possède pas d’attributs propres.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer possède des attributs qui limitent et contrôlent l’étendue des résultats de la recherche.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Cette classe représente un serveur unique exécutant Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-service</p></td>
<td><p>Cette classe contient le conteneur des paramètres globaux et les objets msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Cette classe contient des attributs représentant les paramètres d’un serveur de conférence approuvé.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Cette classe contient des instances de la classe msRTCSIP-TrustedMCU et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Cette classe contient plusieurs classes msRTCSIP-TrustedProxy et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Cette classe est un conteneur représentant un serveur exécutant un serveur proxy. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur proxy sur un ordinateur associé à AD DS.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Cette classe contient des attributs représentant les paramètres d’un serveur approuvé.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Cette classe est un conteneur représentant un service approuvé routable à l’aide d’une adresse d’URI d’agent utilisateur de routage global (GRUU). Une instance de cette classe est créée lorsqu’un nouveau serveur approuvé par Lync Server est activé. Ce serveur approuvé doit être associé à un domaine Active Directory.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Cette classe est un conteneur de serveurs GRUU et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Cette classe contient des attributs représentant les paramètres d’un composant web approuvé.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Cette classe contient des instances de la classe msRTCSIP-TrustedWebComponentServer et ne possède pas d’attributs propres.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsolète)</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-GlobalContainer contient des attributs relatifs aux communications unifiées.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>Cette classe contient le point de contrôle de service pour Internet Information Server (IIS), qui identifie un serveur en tant que serveur de composants web.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Cette classe fournit une association entre un pool spécifique et les composants web qu’il utilise.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Cette classe auxiliaire de msRTCSIP-WebComponents contient des attributs représentant des paramètres réservés aux composants web.</p></td>
<td><p>Nouveauté de Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

