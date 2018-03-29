---
title: Classes de schéma et de descriptions dans Skype pour Business Server
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
ms.openlocfilehash: 20d85e879bb9bfb040150423d47836b6e6803c37
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes de schéma et de descriptions dans Skype pour Business Server
 
Cette section décrit toutes les classes de schéma utilisées par Skype pour Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Les descriptions et les Classes de schéma

|**Classe**|**Description**|**Commentaires**|
|:-----|:-----|:-----|
|Destinataire du message  <br/> |Destinataire de courrier électronique Exchange la messagerie unifiée (MU).  <br/> |Cette classe auxiliaire est partagée avec la messagerie unifiée d’Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Cette classe est un conteneur pour plusieurs contacts de l’application et ne contient-elle pas tous les attributs lui-même.  <br/> |Nouveautés de Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Cette classe contient l’entrée pour le point de contrôle de service d’une instance de Services unifiée des applications de communication (UCAS).  <br/> |Nouveau dans Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Cette classe fournit une association à partir d’un pool spécifique à son service de l’Application.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Cette classe auxiliaire msRTCSIP-ApplicationServer conserve des attributs qui représente les paramètres pour les instances du service de l’Application.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsolète)  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve tous les paramètres liés à l’archivage.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsolète)  <br/> |Cette classe représente un instant unique serveur d’archivage de la messagerie. Une instance de cette classe est créée lorsqu’un ordinateur est activé en tant qu’un archivage de serveur de messagerie instantanée, tel qu’un ordinateur avec le service d’archivage de la messagerie instantanée est installé.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Cette classe est un conteneur pour les instances multiples des répertoires de conférence et ne contient-elle pas tous les attributs lui-même.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Cette classe contient les attributs qui représente les paramètres d’un répertoire de conférence spécifique.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Point de contrôle de service générique (SCP) pour spécifier l’ordinateur comme un serveur exécutant Skype pour Business Server.  <br/> |Nouveau dans Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Cette classe auxiliaire contient les paramètres pour un Skype pour Business Web application bancaire.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-domaine  <br/> |Cette classe contient les attributs qui définissent les domaines configurés d’inscriptions SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Ce conteneur de classe représente un service Edge d’accès. Dans la mesure où un service Edge d’accès est déployé dans le réseau de périmètre et les clients ne permettent généralement pas d’accès des Services de domaine Active Directory à partir du réseau de périmètre, les instances de service Edge d’accès ne sont pas liés à réseau de Active Directory de l’intranet. Par conséquent, les proxys d’accès ne sont pas automatiquement enregistrés dans les services AD DS. L’administrateur doit configurer manuellement l’existence de chaque instance du service Edge d’accès dans les services AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Cette classe auxiliaire msRTCSIP-MCU conserve des attributs qui représente les paramètres pour les serveurs de conférence.  <br/> |Nouveau dans Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Cette classe auxiliaire msRTCSIP-MediationServer conserve des attributs qui représente les paramètres pour les serveurs de médiation.  <br/> |Nouveau dans Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Cette classe auxiliaire msRTCSIP-serveur conserve des attributs qui représente les paramètres de serveurs SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve tous les paramètres liés à la fédération.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Cette classe contient tous les paramètres qui s’appliquent tout au long d’un Skype pour le déploiement du serveur de l’entreprise.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsolète)  <br/> |Cette classe représente une seule stratégie de réunion d’Office Communications Server.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |L’objet de paramètre local topologie globale.  <br/> |Nouveau dans Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Conteneur pour stocker des objets de paramètre de topologie globale.  <br/> |Nouveau dans Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Cette classe est un conteneur qui représente une instance d’une règle d’emplacement de normalisation.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Cette classe est créée par l’application de la surveillance du conférence et conserve des attributs qui permettent de classer les numéros de téléphone de conférence par région.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Cette classe est un conteneur pour plusieurs instances de l’emplacement de mappage des contacts et ne contient-elle pas tous les attributs lui-même.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Cette classe est un conteneur qui représente un profil d’emplacement spécifique.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs profils d’emplacement et ne contient-elle pas tous les attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs règles de normalisation local et ne contient-elle pas tous les attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Cette classe représente un seul serveur de conférence.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Cette classe conserve plusieurs classes de msRTCSIP-MCUFactory et n’a pas les attributs lui-même.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Cette classe est un conteneur qui représente une fabrique de serveur de conférence pour un seul type de support. Une instance de cette classe est créée lorsque le premier serveur de conférence pour ce type particulier et le fournisseur est activé.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Cette classe fournit une association à partir d’un pool spécifique à son usine de serveur de conférence.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Cette classe contient l’entrée pour le point de contrôle de service pour un serveur de médiation.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-réunion (obsolète)  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve des attributs qui représente les paramètres de réunion configurable.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-mobilité  <br/> |Conteneur qui stocke les paramètres de mobilité globale.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Cette classe conserve les attributs qui représentent les paramètres pour un seul serveur d’analyse.  <br/> |Nouveau dans Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsolète)  <br/> |Cette classe est un conteneur qui représente une instance d’un itinéraire de moindre coût à une passerelle ou d’un ensemble de passerelles. Ces informations sont utilisées par tous les pools d’entreprise ou des serveurs Standard Edition pour router les appels sortants vers le réseau téléphonique public commuté (RTPC) de la manière la plus rentable.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsolète)  <br/> |Cette classe est un conteneur pour plusieurs itinéraires moindre coût et ne contient-elle pas tous les attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-stratégies (obsolètes)  <br/> |Cette classe conserve des classes de stratégie plusieurs Lync Server et n’a pas d’attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Cette classe représente un seul Skype pour un pool de serveurs d’entreprise.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Cette classe conserve plusieurs Skype pour les pools de serveurs d’entreprise et n’a pas d’attributs lui-même.  <br/> |-  <br/> |
|msRTCSIP-Poolservice arrêtée  <br/> |Cette classe représente le point de contrôle de service contrôle pointservice d’un pool. Les utilisateurs hébergés sur un pool ont leur msRTCSIP-PrimaryHomeServer point d’attribut à une instance de cette classe.  <br/> |-  <br/> |
|msRTCSIP-présence  <br/> |Conteneur qui stocke les paramètres de présence mondiale.  <br/> |-  <br/> |
|msRTCSIP-inscription  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve des attributs qui représente les paramètres utilisateur gérées par les serveurs SIP de Registrar.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsolète)  <br/> |Cette classe est un conteneur qui représente une instance de l’utilisation d’une gamme de téléphone. Une classe de l’utilisation d’itinéraire téléphonique se compose d’un champ d’attribut et un champ de description. Le champ d’attribut définit un type d’utilisation. Le champ de description permet aux administrateurs décrire l’utilisation de cet attribut dans l’itinéraire téléphonique.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsolète)  <br/> |Cette classe conserve plusieurs instances de la classe msRTCSIP-RouteUsage et n’a pas d’attributs lui-même.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-recherche  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve des attributs pour limitent et contrôlent l’étendue des résultats de recherche.  <br/> |-  <br/> |
|msRTCSIP-serveur  <br/> |Cette classe représente un serveur unique exécutant Skype pour Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Cette classe contient le conteneur de paramètres globaux et les objets de msRTCSIP-domaine.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Cette classe conserve les attributs qui représentent les paramètres pour un serveur de conférence approuvé.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Cette classe conserve plusieurs instances de la classe msRTCSIP-TrustedMCU et n’a pas d’attributs lui-même.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Cette classe conserve plusieurs classes de msRTCSIP-TrustedProxy et ne contient-elle pas tous les attributs lui-même.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Cette classe est un conteneur qui représente un serveur Proxy Server. Une instance de cette classe est créée lors de l’activation d’un nouveau serveur Proxy sur un ordinateur associé à AD DS.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Cette classe conserve les attributs qui représentent les paramètres pour un serveur de confiance.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Cette classe est un conteneur qui représente un service approuvé qui est routable à l’aide d’une adresse GRUU Globally Routable User Agent URI (). Une instance de cette classe est créée lorsqu’un nouveau serveur est approuvé par Skype pour Business Server est activé. Ce serveur doit être joint à un domaine Active Directory de confiance.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Cette classe est un conteneur pour plusieurs serveurs GRUU et ne contient-elle pas tous les attributs lui-même.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Cette classe contient les attributs qui représentent les paramètres d’un composant web de confiance.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Cette classe conserve plusieurs instances de la classe msRTCSIP-TrustedWebComponentServer et n’a pas d’attributs lui-même.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsolète)  <br/> |Cette classe auxiliaire msRTCSIP-GlobalContainer conserve des attributs relatifs aux communications unifiées.  <br/> |Obsolète dans Lync Server 2010.  <br/> |
|msRTCSIP-des composants Web  <br/> |Cette classe contient le point de contrôle de service contrôle pointservice pour Internet Information Server (IIS). Il identifie un serveur comme un serveur de composants web.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Cette classe fournit une association à partir d’un pool spécifique aux composants web qui utilise le pool.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Cette classe auxiliaire msRTCSIP-composants Web conserve des attributs qui représente les paramètres pour les composants web.  <br/> |Nouveau dans Communications Server 2007.  <br/> |
   

