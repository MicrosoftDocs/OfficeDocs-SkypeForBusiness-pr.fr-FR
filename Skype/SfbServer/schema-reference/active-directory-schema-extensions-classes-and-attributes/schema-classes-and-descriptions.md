---
title: Classes et descriptions de schéma dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Cette section décrit toutes les classes de schéma utilisées par Skype entreprise Server.
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296594"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes et descriptions de schéma dans Skype entreprise Server
 
Cette section décrit toutes les classes de schéma utilisées par Skype entreprise Server. 
  
## <a name="schema-classes-and-descriptions"></a>Classes et descriptions de schéma

|**Cours**|**Description**|**Commentaires**|
|:-----|:-----|:-----|
|Mail-destinataire  <br/> |Destinataire du message de messagerie unifiée (MU) Exchange.  <br/> |Cette classe auxiliaire est partagée avec la messagerie unifiée Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Cette classe est un conteneur pour plusieurs contacts d’application et ne contient pas d’attributs lui-même.  <br/> |Nouveautés de Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Cette classe contient l’entrée du point de contrôle de service d’une instance de services d’application de communications unifiées (UCAS).  <br/> |Nouveauté d’Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Cette classe fournit une association d’un pool spécifique au service d’application.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Cette classe auxiliaire pour msRTCSIP-ApplicationServer contient des attributs représentant des paramètres pour les instances du service d’application.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsolète)  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient tous les paramètres relatifs à l’archivage.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsolète)  <br/> |Cette classe représente un serveur d’archivage de la messagerie instantanée unique. Une instance de cette classe est créée lors de l’activation d’un ordinateur comme serveur d’archivage de messagerie instantanée, tel qu’un ordinateur sur lequel est installé le service d’archivage de la messagerie instantanée.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Cette classe est un conteneur pour plusieurs instances de répertoires de conférences et ne contient aucun attribut lui-même.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Cette classe comporte des attributs représentant des paramètres pour un annuaire de conférences spécifique.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Point de contrôle de service générique (SCP) pour spécifier l’ordinateur comme serveur exécutant Skype entreprise Server.  <br/> |Nouveautés de Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Cette classe auxiliaire contient les paramètres pour une banque Web App Skype entreprise.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Cette classe comporte des attributs qui définissent les domaines configurés du Bureau d’enregistrement SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Ce conteneur de classe représente un service Edge d’accès unique. Dans la mesure où un service Edge d’accès est déployé dans le réseau de périmètre et que les clients n’autorisent pas l’accès aux services de domaine Active Directory à partir du réseau de périmètre, les instances du service Edge d’accès ne sont pas jointes au réseau Active Directory de l’intranet. C’est pourquoi les proxys d’accès ne sont pas automatiquement inscrits dans AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Cette classe auxiliaire est associée à msRTCSIP-MCU en tant qu’attributs représentant les paramètres des serveurs de conférence.  <br/> |Nouveautés de Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Cette classe auxiliaire pour msRTCSIP-MediationServer contient des attributs représentant les paramètres des serveurs de médiation.  <br/> |Nouveautés d’Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Cette classe auxiliaire pour msRTCSIP-Server comporte des attributs représentant les paramètres des serveurs SIP.  <br/> |-  <br/> |
|msRTCSIP-Fédération  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient tous les paramètres liés à la Fédération.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Cette classe comporte tous les paramètres qui s’appliquent à tout le déploiement de Skype entreprise Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsolète)  <br/> |Cette classe représente une seule stratégie de réunion du serveur Office Communications Server.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Objet du paramètre topologique global local.  <br/> |Nouveautés de Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Conteneur pour contenir les objets de paramètres topologique globaux.  <br/> |Nouveautés de Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Cette classe est un conteneur qui représente une instance d’une règle de normalisation de l’emplacement.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Cette classe est créée par l’application de surveillance des conférences et contient des attributs permettant de classer les numéros de téléphone de conférence par région.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Cette classe est un conteneur pour plusieurs instances de mappages de contacts d’emplacement et ne contient aucun attribut lui-même.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Cette classe est un conteneur qui représente un profil d’emplacement spécifique.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs profils d’emplacement et ne contient aucun attribut lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs règles de normalisation locales et ne contient aucun attribut lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Cette classe représente un serveur de conférence unique.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Cette classe contient plusieurs classes msRTCSIP-MCUFactory et ne possède pas d’attributs lui-même.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Cette classe est un conteneur qui représente une fabrique de serveurs de conférence pour un type de support unique. Une instance de cette classe est créée lorsque le premier serveur de conférence pour ce type et ce fournisseur spécifiques est activé.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Cette classe fournit une association entre un pool spécifique et sa fabrique du serveur de conférence.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Cette classe contient l’entrée du point de contrôle de service pour un serveur de médiation.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-réunion (obsolète)  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui représentent des paramètres de réunion configurables.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Conteneur qui stocke les paramètres de mobilité globale.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Cette classe comporte des attributs qui représentent des paramètres pour un serveur de surveillance unique.  <br/> |Nouveauté de Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsolète)  <br/> |Cette classe est un conteneur qui représente une instance d’un itinéraire moins coûteux vers une passerelle ou un ensemble de passerelles. Ces informations sont utilisées par tous les serveurs ou les pools d’entreprise exécutant Standard Edition pour diriger les appels sortants vers le réseau téléphonique public commuté (RTC), le plus rentable.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs itinéraires de coûts minimum et ne contient aucun attribut lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-stratégies (obsolète)  <br/> |Cette classe contient plusieurs classes de stratégie de serveur Lync et ne possède pas d’attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-pool  <br/> |Ce cours représente une seule grappe de serveurs Skype entreprise.  <br/> |-  <br/> |
|msRTCSIP-pools  <br/> |Ce cours inclut plusieurs pools de serveurs Skype entreprise et ne possède pas d’attributs lui-même.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Cette classe représente le point de contrôle pointservice du contrôle de service d’un pool. Les utilisateurs hébergés sur un pool disposent de leur attribut msRTCSIP-PrimaryHomeServer sur une instance de cette classe.  <br/> |-  <br/> |
|msRTCSIP-présence  <br/> |Conteneur qui stocke les paramètres de présence globaux.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui représentent des paramètres utilisateur conservés par les serveurs de bureaux d’enregistrement SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsolète)  <br/> |Cette classe est un conteneur qui représente une instance d’utilisation de l’itinéraire du téléphone. Une classe d’utilisation de l’itinéraire de téléphone comporte un champ d’attribut et un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ Description permet aux administrateurs de décrire l’utilisation de cet attribut dans l’itinéraire du téléphone.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsolète)  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-RouteUsage et ne possède pas d’attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-recherche  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs qui limitent et contrôlent la portée des résultats de recherche.  <br/> |-  <br/> |
|msRTCSIP-serveur  <br/> |Cette classe représente un serveur unique exécutant Skype entreprise Server.  <br/> |-  <br/> |
|msRTCSIP-service  <br/> |Cette classe contient le conteneur de paramètres globaux et les objets msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Cette classe comporte des attributs qui représentent des paramètres pour un serveur de conférence approuvé.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedMCU et ne possède pas d’attributs lui-même.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Cette classe contient plusieurs classes msRTCSIP-TrustedProxy et ne contient aucun attribut lui-même.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Cette classe est un conteneur qui représente un serveur exécutant Proxy Server. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur proxy sur un ordinateur joint à AD DS.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Cette classe comporte des attributs qui représentent des paramètres pour un serveur de confiance.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Cette classe est un conteneur qui représente un service approuvé qui est routable à l’aide d’une adresse de l’URI de l’agent utilisateur routable (GRUU). Une instance de cette classe est créée lors de l’activation d’un nouveau serveur approuvé par Skype entreprise Server. Ce serveur approuvé doit être joint à un domaine Active Directory.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Cette classe est un conteneur pour plusieurs serveurs GRUU et ne contient aucun attribut lui-même.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Cette classe contient des attributs qui représentent les paramètres d’un composant WebPart de confiance.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Cette classe contient plusieurs instances de la classe msRTCSIP-TrustedWebComponentServer et ne possède pas d’attributs lui-même.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsolète)  <br/> |Cette classe auxiliaire pour msRTCSIP-GlobalContainer contient des attributs liés aux communications unifiées.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-webcomposants  <br/> |Cette classe contient le point de contrôle du contrôle de service pointservice pour Internet Information Server (IIS). Il identifie un serveur en tant que serveur de composants WebPart.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Cette classe fournit une association d’un pool spécifique aux composants Web que le pool utilisera.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Cette classe auxiliaire à msRTCSIP-WebComponents contient des attributs représentant les paramètres des composants WebPart.  <br/> |Nouveautés de Communications Server 2007.  <br/> |
   

