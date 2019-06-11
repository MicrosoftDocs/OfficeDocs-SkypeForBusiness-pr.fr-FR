---
title: 'Lync Server 2013: classes et descriptions de schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Descriptions et classes de schéma dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

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
<th>Cours</th>
<th>Description</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-destinataire</p></td>
<td><p>Destinataire du message de messagerie unifiée (MU) Exchange.</p></td>
<td><p>Cette classe auxiliaire est partagée avec la messagerie unifiée Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Cette classe est un conteneur pour plusieurs contacts d’application et ne contient pas d’attributs lui-même.</p></td>
<td><p>Nouveautés de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Cette classe contient l’entrée du point de contrôle de service d’une instance de services d’application de communications unifiées (UCAS).</p></td>
<td><p>Nouveauté d’Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Cette classe fournit une association d’un pool spécifique au service d’application.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-ApplicationServer contient des attributs représentant des paramètres pour les instances du service d’application.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsolète)</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient tous les paramètres relatifs à l’archivage.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsolète)</p></td>
<td><p>Cette classe représente un serveur d’archivage de la messagerie instantanée unique. Une instance de cette classe est créée lors de l’activation d’un ordinateur comme serveur d’archivage de messagerie instantanée, tel qu’un ordinateur sur lequel est installé le service d’archivage de la messagerie instantanée.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Cette classe est un conteneur pour plusieurs instances de répertoires de conférences et ne contient aucun attribut lui-même.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Cette classe comporte des attributs représentant des paramètres pour un annuaire de conférences spécifique.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Point de contrôle de service générique (SCP) pour spécifier l’ordinateur comme serveur exécutant Lync Server.</p></td>
<td><p>Nouveautés de Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Cette classe auxiliaire contient les paramètres pour une banque Microsoft Lync Web App.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Cette classe comporte des attributs qui définissent les domaines configurés du Bureau d’enregistrement SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Ce conteneur de classe représente un service Edge d’accès unique. Dans la mesure où un service Edge d’accès est déployé dans le réseau de périmètre et que les clients n’autorisent pas l’accès aux services de domaine Active Directory à partir du réseau de périmètre, les instances du service Edge d’accès ne sont pas jointes au réseau Active Directory de l’intranet. C’est pourquoi les proxys d’accès ne sont pas automatiquement inscrits dans AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Cette classe auxiliaire est associée à msRTCSIP-MCU en tant qu’attributs représentant les paramètres des serveurs de conférence.</p></td>
<td><p>Nouveautés de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-MediationServer contient des attributs représentant les paramètres des serveurs de médiation.</p></td>
<td><p>Nouveautés d’Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-Server comporte des attributs représentant les paramètres des serveurs SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Fédération</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient tous les paramètres liés à la Fédération.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Cette classe comporte tous les paramètres qui s’appliquent à tout le déploiement de Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsolète)</p></td>
<td><p>Cette classe représente une seule stratégie de réunion du serveur Office Communications Server.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Objet du paramètre topologique global local.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Conteneur pour contenir les objets de paramètres topologique globaux.</p></td>
<td><p>Nouveautés de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Cette classe est un conteneur qui représente une instance d’une règle de normalisation de l’emplacement.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Cette classe est créée par l’application de surveillance des conférences et contient des attributs permettant de classer les numéros de téléphone de conférence par région.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Cette classe est un conteneur pour plusieurs instances de mappages de contacts d’emplacement et ne contient aucun attribut lui-même.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Cette classe est un conteneur qui représente un profil d’emplacement spécifique.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsolète)</p></td>
<td><p>Cette classe est un conteneur pour plusieurs profils d’emplacement et ne contient aucun attribut lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsolète)</p></td>
<td><p>Cette classe est un conteneur pour plusieurs règles de normalisation locales et ne contient aucun attribut lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Cette classe représente un serveur de conférence unique.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Cette classe contient plusieurs classes msRTCSIP-MCUFactory et ne possède pas d’attributs lui-même.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Cette classe est un conteneur qui représente une fabrique de serveurs de conférence pour un type de support unique. Une instance de cette classe est créée lorsque le premier serveur de conférence pour ce type et ce fournisseur spécifiques est activé.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Cette classe fournit une association entre un pool spécifique et sa fabrique du serveur de conférence.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Cette classe contient l’entrée du point de contrôle de service pour un serveur de médiation.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-réunion (obsolète)</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui représentent des paramètres de réunion configurables.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Conteneur qui stocke les paramètres de mobilité globale.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Cette classe comporte des attributs qui représentent des paramètres pour un serveur de surveillance unique.</p></td>
<td><p>Nouveauté de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsolète)</p></td>
<td><p>Cette classe est un conteneur qui représente une instance d’un itinéraire moins coûteux vers une passerelle ou un ensemble de passerelles. Ces informations sont utilisées par tous les serveurs ou les pools d’entreprise exécutant Standard Edition pour diriger les appels sortants vers le réseau téléphonique public commuté (RTC), le plus rentable.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsolète)</p></td>
<td><p>Cette classe est un conteneur pour plusieurs itinéraires de coûts minimum et ne contient aucun attribut lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-stratégies (obsolète)</p></td>
<td><p>Cette classe contient plusieurs classes de stratégie de serveur Lync et ne possède pas d’attributs lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pool</p></td>
<td><p>Cette classe représente un pool de serveurs Lync unique.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pools</p></td>
<td><p>Cette classe contient plusieurs pools de serveurs Lync et ne possède pas d’attributs lui-même.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Cette classe représente le point de contrôle pointservice du contrôle de service d’un pool. Les utilisateurs hébergés sur un pool disposent de leur attribut msRTCSIP-PrimaryHomeServer sur une instance de cette classe.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-présence</p></td>
<td><p>Conteneur qui stocke les paramètres de présence globaux.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui représentent des paramètres utilisateur conservés par les serveurs de bureaux d’enregistrement SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsolète)</p></td>
<td><p>Cette classe est un conteneur qui représente une instance d’utilisation de l’itinéraire du téléphone. Une classe d’utilisation de l’itinéraire de téléphone comporte un champ d’attribut et un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ Description permet aux administrateurs de décrire l’utilisation de cet attribut dans l’itinéraire du téléphone.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsolète)</p></td>
<td><p>Cette classe contient plusieurs instances de la classe msRTCSIP-RouteUsage et ne possède pas d’attributs lui-même.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-recherche</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui limitent et contrôlent la portée des résultats de recherche.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-serveur</p></td>
<td><p>Cette classe représente un serveur unique exécutant Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-service</p></td>
<td><p>Cette classe contient le conteneur de paramètres globaux et les objets msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Cette classe comporte des attributs qui représentent des paramètres pour un serveur de conférence approuvé.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedMCU et ne possède pas d’attributs lui-même.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Cette classe contient plusieurs classes msRTCSIP-TrustedProxy et ne contient aucun attribut lui-même.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Cette classe est un conteneur qui représente un serveur exécutant Proxy Server. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur proxy sur un ordinateur joint à AD DS.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Cette classe comporte des attributs qui représentent des paramètres pour un serveur de confiance.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Cette classe est un conteneur qui représente un service approuvé qui est routable à l’aide d’une adresse de l’URI de l’agent utilisateur routable (GRUU). Une instance de cette classe est créée lorsqu’un nouveau serveur approuvé par Lync Server est activé. Ce serveur approuvé doit être joint à un domaine Active Directory.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Cette classe est un conteneur pour plusieurs serveurs GRUU et ne contient aucun attribut lui-même.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Cette classe contient des attributs qui représentent les paramètres d’un composant WebPart de confiance.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedWebComponentServer et ne possède pas d’attributs lui-même.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsolète)</p></td>
<td><p>Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs liés aux communications unifiées.</p></td>
<td><p>Obsolète dans Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-webcomposants</p></td>
<td><p>Cette classe contient le point de contrôle du contrôle de service pointservice pour Internet Information Server (IIS). Il identifie un serveur en tant que serveur de composants WebPart.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Cette classe fournit une association d’un pool spécifique aux composants Web que le pool utilisera.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Cette classe auxiliaire à msRTCSIP-WebComponents contient des attributs représentant les paramètres des composants WebPart.</p></td>
<td><p>Nouveautés de Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

