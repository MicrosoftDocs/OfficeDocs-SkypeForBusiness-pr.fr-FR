---
title: Classes de schéma et les descriptions de Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Cette section décrit toutes les classes de schéma utilisées par Skype pour Business Server.
ms.openlocfilehash: 0bb34a93ec23df67d19026e82e29769e0aeb9ab2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926559"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes de schéma et les descriptions de Skype pour Business Server
 
Cette section décrit toutes les classes de schéma utilisées par Skype pour Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Descriptions et Classes de schéma

|**Classe**|**Description**|**Commentaires**|
|:-----|:-----|:-----|
|Destinataire du message  <br/> |Destinataire de courrier électronique de la messagerie unifiée Exchange (MU).  <br/> |Cette classe auxiliaire est partagée avec la messagerie unifiée Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Cette classe est un conteneur de contacts d’application et ne possède pas d’attributs propres.  <br/> |Nouveauté dans Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Cette classe conserve l’entrée pour le point de contrôle de service pour une instance de Communications unifiées Application Services (UCAS).  <br/> |Nouveau dans Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Cette classe fournit une association entre un pool spécifique et son service d’Application.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-ApplicationServer conserve des attributs représentant des paramètres pour les instances du service d’Application.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres concernant l’archivage.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsolète)  <br/> |Cette classe représente un seul serveur d’archivage de pic. Une instance de cette classe est créée lorsqu’un ordinateur est activé comme un archivage serveur de messagerie instantanée, tel qu’un ordinateur avec le service d’archivage de la messagerie instantanée est installé.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Cette classe est un conteneur pour plusieurs instances d’annuaires des conférences et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Cette classe contient des attributs représentant des paramètres pour un annuaire des conférences spécifique.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Point de contrôle de service générique (SCP) pour spécifier l’ordinateur en tant que serveur exécutant Skype pour Business Server.  <br/> |Nouveauté de Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Cette classe auxiliaire contient les paramètres pour un Skype pour Business Web application banque.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Cette classe conserve des attributs qui définissent les domaines configurés du Registre SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Ce conteneur de classe représente un seul service Edge d’accès. Étant donné que le service Edge d’accès est déployé dans le réseau de périmètre et les clients généralement ne permettent pas d’accès aux Services de domaine Active Directory à partir du réseau de périmètre, les instances du service Edge d’accès ne sont pas liés au réseau d’Active Directory de l’intranet. Par conséquent, les proxys d’accès ne sont pas automatiquement inscrits dans AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Cette classe auxiliaire de msRTCSIP-MCU conserve des attributs représentant des paramètres pour les serveurs de conférence.  <br/> |Nouveauté dans Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-MediationServer conserve des attributs représentant des paramètres pour les serveurs de médiation.  <br/> |Nouveau dans Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Cette classe auxiliaire de msRTCSIP-Server conserve des attributs représentant des paramètres pour les serveurs SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer contient tous les paramètres liés à la fédération.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Cette classe conserve tous les paramètres qui s’appliquent tout au long d’un Skype pour le déploiement de serveur d’entreprise.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsolète)  <br/> |Cette classe représente une seule stratégie de réunion Office Communications Server.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |L’objet de paramètre local de la topologie globale.  <br/> |Nouveauté de Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Conteneur qui contient les objets de paramètres de la topologie globale.  <br/> |Nouveauté de Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Cette classe est un conteneur représentant une instance d’une règle de normalisation d’emplacement.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Cette classe est créée par l’application intendant Conférence et conserve des attributs servis à classer les numéros de téléphone de conférence par région.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Cette classe est un conteneur pour plusieurs instances de l’emplacement de mappages de contact et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Cette classe est un conteneur représentant un profil d’emplacement spécifique.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs profils d’emplacement et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsolète)  <br/> |Cette classe est un conteneur de règles de normalisation locales et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Cette classe représente un seul serveur de conférence.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Cette classe contient plusieurs classes msRTCSIP-MCUFactory et ne possède pas les attributs propres.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Cette classe est un conteneur représentant un répartiteur de serveurs de conférence pour un seul type de taille moyens. Une instance de cette classe est créée lorsque le premier serveur de conférence pour ce type et le fournisseur est activé.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Cette classe fournit une association entre un pool spécifique et son répartiteur de serveurs de conférence.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Cette classe conserve l’entrée pour le point de contrôle de service d’un serveur de médiation.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer conserve des attributs représentant les paramètres de réunion configurables.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-mobilité  <br/> |Conteneur qui stocke les paramètres globaux de mobilité.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Cette classe conserve des attributs qui représentent les paramètres pour un seul serveur de surveillance.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsolète)  <br/> |Cette classe est un conteneur représentant une instance d’un itinéraire à moindre coût vers une passerelle ou un ensemble de passerelles. Cette information est utilisée par tous les pools d’entreprise ou serveurs Standard Edition pour acheminer les appels sortants vers le réseau téléphonique commuté (RTC) de la manière la plus rentable.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsolète)  <br/> |Cette classe est un conteneur d’itinéraires à moindre coût et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsolète)  <br/> |Cette classe contient des classes de stratégie de plusieurs Lync Server et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Cette classe représente un seul Skype pour le pool de serveurs d’entreprise.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Cette classe contient plusieurs Skype pour les pools de serveurs d’entreprise et ne possède pas d’attributs propres.  <br/> |-  <br/> |
|msRTCSIP-Poolservice arrêtée  <br/> |Cette classe représente le point de contrôle de service contrôle pointservice d’un pool. Les utilisateurs hébergés sur un pool ont leur msRTCSIP-PrimaryHomeServer attribut point à une instance de cette classe.  <br/> |-  <br/> |
|msRTCSIP-présence  <br/> |Conteneur qui stocke les paramètres globaux de présence.  <br/> |-  <br/> |
|msRTCSIP-serveurs d’inscriptions  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer conserve des attributs représentant les paramètres utilisateur gérés par les serveurs SIP du serveur d’inscriptions.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsolète)  <br/> |Cette classe est un conteneur représentant une instance d’une utilisation d’itinéraire téléphonique. Une classe de l’utilisation d’itinéraire téléphonique se compose d’un champ d’attribut et un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ description permet aux administrateurs de décrire l’utilisation de cet attribut dans l’itinéraire téléphonique.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsolète)  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-RouteUsage et ne possède pas d’attributs propres.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-recherche  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer conserve des attributs qui limitent et contrôlent l’étendue des résultats de recherche.  <br/> |-  <br/> |
|msRTCSIP-serveur  <br/> |Cette classe représente un serveur unique exécutant Skype pour Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Cette classe conserve le conteneur des paramètres globaux et les objets msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Cette classe conserve des attributs représentant les paramètres d’un serveur de conférence approuvé.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedMCU et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Cette classe conserve plusieurs classes msRTCSIP-TrustedProxy et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Cette classe est un conteneur représentant un serveur exécutant le serveur Proxy. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur Proxy sur un ordinateur lié au domaine Active Directory.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Cette classe conserve des attributs représentant les paramètres d’un serveur approuvé.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Cette classe est un conteneur représentant un service approuvé routable à l’aide d’une adresse GRUU Globally Routable User Agent URI (). Une instance de cette classe est créée lorsqu’un nouveau serveur est approuvé par Skype pour Business Server est activé. Ce serveur doit être joint à un domaine Active Directory de confiance.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Cette classe est un conteneur de serveurs GRUU et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Cette classe conserve des attributs représentant les paramètres d’un composant web approuvé.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedWebComponentServer et ne possède pas d’attributs propres.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsolète)  <br/> |Cette classe auxiliaire de msRTCSIP-GlobalContainer conserve des attributs relatifs aux communications unifiées.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Cette classe contient le point de contrôle de service contrôle pointservice pour Internet Information Server (IIS). Il identifie un serveur comme un serveur de composants web.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Cette classe fournit une association entre un pool spécifique et les composants web qui utilise le pool.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Cette classe auxiliaire de msRTCSIP-WebComponents conserve des attributs représentant des paramètres pour les composants web.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
   

