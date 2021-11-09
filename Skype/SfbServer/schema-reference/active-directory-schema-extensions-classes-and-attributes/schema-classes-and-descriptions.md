---
title: Classes de schéma et descriptions dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Cette section décrit toutes les classes de schéma utilisées par Skype Entreprise Server .
ms.openlocfilehash: fbd3e3293cef72ba6592b86932639bd499464858
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829768"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes de schéma et descriptions dans Skype Entreprise Server
 
Cette section décrit toutes les classes de schéma utilisées par Skype Entreprise Server . 
  
## <a name="schema-classes-and-descriptions"></a>Classes et descriptions de schéma

|**Classe**|**Description**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange Destinataire du courrier de messagerie unifiée.  <br/> |Cette classe auxiliaire est partagée avec la Exchange um.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Cette classe est un conteneur de contacts d’application et ne possède pas d’attributs propres.  <br/> |Nouveauté de Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Cette classe contient l’entrée correspondant au point de contrôle de service d’une instance des services d’applications de communications unifiées (UCAS).  <br/> |Nouveauté de Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Cette classe fournit une association d’un pool spécifique à son service d’application.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-ApplicationServer contient des attributs représentant des paramètres pour les instances du service d’application.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres concernant l’archivage.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsolète)  <br/> |Cette classe représente un serveur d’archivage de messagerie instantanée unique. Une instance de cette classe est créée lorsqu’un ordinateur est activé en tant que serveur d’archivage de messagerie instantanée, par exemple un ordinateur sur lequel est installé le service d’archivage de messagerie instantanée.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Cette classe est un conteneur d’instances d’annuaires des conférences et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Cette classe contient des attributs représentant des paramètres réservés à un annuaire des conférences spécifique.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Point de contrôle de service générique (SCP) pour spécifier l’ordinateur en tant que serveur exécutant Skype Entreprise Server.  <br/> |Nouveauté de Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Cette classe auxiliaire contient les paramètres d’une Application Web Skype Entreprise bancaire.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Cette classe contient des attributs qui définissent les domaines configurés du registre SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Ce conteneur de classe représente un service Edge d’accès unique. Étant donné qu’un service Edge d’accès est déployé dans le réseau de périmètre et que les clients n’autorisent généralement pas l’accès aux services de domaine Active Directory à partir du réseau de périmètre, les instances du service Edge d’accès ne sont pas jointes au réseau Active Directory de l’intranet. Par conséquent, les proxies Access ne sont pas automatiquement enregistrés dans AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Cette classe auxiliaire de msRTCSIP-MCU contient des attributs représentant des paramètres réservés aux serveurs de conférence.  <br/> |Nouveauté de Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-MediationServer contient des attributs représentant des paramètres réservés aux serveurs de médiation.  <br/> |Nouveauté de Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-Server contient des attributs représentant des paramètres réservés aux serveurs SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres concernant la fédération.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Cette classe contient tous les paramètres qui s’appliquent tout au long d’Skype Entreprise Server déploiement.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsolète)  <br/> |Cette classe représente une stratégie de réunion Office Communications Server.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Objet local de paramètre de la topologie globale.  <br/> |Nouveauté de Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Conteneur qui contient les objets de paramètre de la topologie globale.  <br/> |Nouveauté de Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Cette classe est un conteneur représentant une instance d’une règle de normalisation d’emplacement.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Cette classe est créée par le application Assistant de conférence et contient des attributs utilisés pour classer les numéros de téléphone de conférence par région.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Cette classe est un conteneur d’instances de mappages de contact d’emplacement et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Cette classe est un conteneur représentant un profil d’emplacement spécifique.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsolète)  <br/> |Cette classe est un conteneur de profils d’emplacement et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsolète)  <br/> |Cette classe est un conteneur de règles de normalisation locales et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Cette classe représente un serveur de conférence unique.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Cette classe héberge des classes msRTCSIP-MCUFactory et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Cette classe est un conteneur représentant un répartiteur de serveurs de conférence pour un type de support unique. Une instance de cette classe est créée lorsque le premier serveur de conférence de ce type et fournisseur est activé.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Cette classe fournit une association entre un pool spécifique et son répartiteur de serveurs de conférence.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Cette classe contient l’entrée correspondant au point de contrôle de service d’un serveur de médiation.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer possède des attributs représentant des paramètres de réunion configurables.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Conteneur qui stocke les paramètres globaux de mobilité.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Cette classe contient des attributs qui représentent les paramètres d’un serveur de surveillance unique.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsolète)  <br/> |Cette classe est un conteneur représentant une instance de l’itinéraire à moindre coût vers une passerelle ou un ensemble de passerelles. Ces informations sont utilisées par tous les pools ou serveurs d’entreprise ou les serveurs exécutant Standard Edition pour acheminer les appels sortants vers le réseau téléphonique commuté (RTC) de la manière la plus rentable qui soit.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsolète)  <br/> |Cette classe est un conteneur d’itinéraires à moindre coût et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsolète)  <br/> |Cette classe contient plusieurs classes de stratégie Lync Server et n’a pas d’attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Cette classe représente un pool Skype Entreprise Server unique.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Cette classe contient plusieurs pools Skype Entreprise Server et n’a pas d’attributs lui-même.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Cette classe représente le point de contrôle de service d’un pool. Les utilisateurs hébergés dans un pool font pointer leur attribut msRTCSIP-PrimaryHomeServer sur une instance de cette classe.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Conteneur qui stocke les paramètres globaux de présence.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient les attributs représentant les paramètres utilisateur gérés par les serveurs du registre SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsolète)  <br/> |Cette classe est un conteneur représentant une instance d’une utilisation d’itinéraire téléphonique. Une classe d’utilisation d’itinéraire téléphonique se compose d’un champ d’attribut et d’un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ de description permet aux administrateurs de décrire l’utilisation de cet attribut dans l’itinéraire téléphonique.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsolète)  <br/> |Cette classe contient des instances de la classe msRTCSIP-RouteUsage et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer possède des attributs qui limitent et contrôlent l’étendue des résultats de la recherche.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Cette classe représente un serveur unique exécutant Skype Entreprise Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Cette classe contient le conteneur des paramètres globaux et les objets msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Cette classe contient des attributs représentant les paramètres d’un serveur de conférence approuvé.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Cette classe contient des instances de la classe msRTCSIP-TrustedMCU et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Cette classe contient plusieurs classes msRTCSIP-TrustedProxy et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Cette classe est un conteneur représentant un serveur exécutant un serveur proxy. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur proxy sur un ordinateur associé à AD DS.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Cette classe contient des attributs représentant les paramètres d’un serveur approuvé.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Cette classe est un conteneur représentant un service approuvé routable à l’aide d’une adresse d’URI d’agent utilisateur de routage global (GRUU). Une instance de cette classe est créée lorsqu’un nouveau serveur approuvé par Skype Entreprise Server est activé. Ce serveur approuvé doit être associé à un domaine Active Directory.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Cette classe est un conteneur de serveurs GRUU et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Cette classe contient des attributs représentant les paramètres d’un composant web approuvé.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Cette classe contient des instances de la classe msRTCSIP-TrustedWebComponentServer et ne possède pas d’attributs propres.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient des attributs relatifs aux communications unifiées.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Cette classe contient le point de contrôle de service pour Internet Information Server (IIS), qui identifie un serveur en tant que serveur de composants web.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Cette classe fournit une association entre un pool spécifique et les composants web qu’il utilise.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Cette classe auxiliaire de msRTCSIP-WebComponents contient des attributs représentant des paramètres réservés aux composants web.  <br/> |Nouveauté de Communications Server 2007.  <br/> |
   

