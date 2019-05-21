---
title: Configuration requise pour les ports et les protocoles pour les serveurs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Résumé: Examinez les considérations d’utilisation des ports avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 613067d90da4fb06811ca1497c83237019b3c021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297021"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Configuration requise pour les ports et les protocoles pour les serveurs
 
**Résumé:** Passez en revue les considérations d’utilisation de port avant d’implémenter Skype entreprise Server.
  
Skype entreprise Server nécessite l’ouverture des ports spécifiques des pare-feux externes et internes. De plus, si la sécurité IPsec (Internet Protocol security) est déployée dans votre organisation, elle doit être désactivée sur la plage de ports utilisée pour l’acheminement des flux audio, vidéo et de vidéo panoramique. 
  
Même si l’utilisation de l' [outil de planification de Skype entreprise Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725)peut sembler une véritable gageure, vous pouvez le faire en premier pour la planification. Lorsque vous avez parcouru les questions de l’Assistant sur les fonctionnalités que vous envisagez d’utiliser, pour chaque site que vous définissez, vous pouvez consulter le rapport de pare-feu dans le rapport d’administration latérale et utiliser les informations qui y sont indiquées pour créer des règles yourfirewall. Pour plus d’informations, consultez [la section examen du rapport de pare-feu](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)pour plus d’informations sur les noms et les adresses IP utilisés. Gardez à l’esprit que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel, et le rapport de pare-feu sera l’une des feuilles de calcul du fichier. 
  
Vous pouvez également rechercher les informations dans ces tableaux sous forme de diagramme en passant en revue l’poster de charge de travail du protocole lié aux schémas techniques de l’article [2015 de Skype entreprise Server](../../technical-diagrams.md) .
> [!NOTE]
> - Si vous implémentez Skype entreprise Online (O365), voir [URL et plages d’adresses IP Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Dans les environnements hybrides, vous devez faire référence à ce sujet et [planifier une connectivité hybride](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Vous pouvez disposer de pare-feu matériel ou logiciel; nous n’avons pas besoin de modèles ou de versions spécifiques. En ce qui concerne les ports autorisés, le pare-feu n’affectera pas le fonctionnement de Skype entreprise Server.
  
## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

Cette section résume les ports et les protocoles utilisés par les serveurs, les équilibreurs de charge et les clients dans le déploiement de Skype entreprise Server.
  
> [!NOTE]
> Lorsque Skype entreprise Server démarre, il ouvre les ports requis dans le pare-feu Windows. Le pare-feu Windows doit déjà être exécuté dans la plupart des applications normales, mais si ce n’est pas le cas, Skype entreprise Server fonctionne sans lui. 
  
Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [scénarios de serveur Edge dans Skype entreprise Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne. 
  
**Ports de serveurs requis (par rôle serveur)**

|Rôle serveur|Nom du service|Port|Protocole|Remarques|
|:-----|:-----|:-----|:-----|:-----|
|Tous les serveurs  |SQL Browser  |1434  |UDP  |Navigateur SQL pour la copie locale répliquée de la base de données centrale de la Banque d’administration.  |
|serveurs frontaux  |Service frontal Skype entreprise Server  |5060  |TCP  |Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|serveurs frontaux  |Service frontal Skype entreprise Server  |5061  | TCP (TLS) |Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.  |
| Serveurs frontaux |Service frontal Skype entreprise Server  |444  | HTTPS <br/> TCP  |Utilisé pour la communication HTTPs entre le focus (composant Skype entreprise Server qui gère l’état de la Conférence) et les serveurs individuels.  <br/> Ce port est également utilisé pour la communication TCP entre les appareils succursales Survivables et les serveurs frontaux.  |
|serveurs frontaux  |Service frontal Skype entreprise Server  |135  |DCOM et appel de procédure distante (RPC)  |Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.  |
|serveurs frontaux  |Service de conférence par messagerie instantanée Skype entreprise Server  |5062  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  |
|serveurs frontaux  |Service de conférence Web Skype entreprise Server  |8057  |TCP (TLS)  |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  |
|serveurs frontaux  |Service de compatibilité de conférences Web Skype entreprise Server  |8058  |TCP (TLS)  |Utilisé pour écouter les connexions PSOM (persistent Shared Object mode) du client Live Meeting et des versions précédentes de Skype entreprise Server.  |
|serveurs frontaux  |Service de conférence audio/vidéo Skype entreprise Server  |5063  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  |
|serveurs frontaux  |Service de conférence audio/vidéo Skype entreprise Server  |57501-65535  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences vidéo.  |
|serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |80  |HTTP  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.  |
|serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |443  |HTTPS  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  |
|serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |8080  |TCP et HTTP  |Utilisé par les composants web pour l’accès externe.  |
|Serveurs frontaux  |Composant de serveur web  |4443  |HTTPS  |Communications HTTPS (du proxy inverse) et HTTPS inter-pool frontal pour connexion à la découverte automatique.  |
|Serveurs frontaux  |Composant de serveur web  |8060  |TCP (MTLS)  ||
|serveurs frontaux  |Composant de serveur web  |8061  |TCP (MTLS)  ||
|serveurs frontaux  |Composant des services de mobilité  |5086  |TCP (MTLS)  |Port SIP utilisé pour les processus internes des services de mobilité.  |
|serveurs frontaux  |Composant des services de mobilité  |5087  |TCP (MTLS)  |Port SIP utilisé pour les processus internes des services de mobilité.  |
|serveurs frontaux  |Composant des services de mobilité  |443  |HTTPS  ||
|serveurs frontaux  |Service de surveillance des conférences Skype entreprise Server (conférences rendez-vous)  |5064  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  |
|serveurs frontaux  |Service de surveillance des conférences Skype entreprise Server (conférences rendez-vous)  |5072  |TCP  |Utilisé pour les demandes SIP entrantes pour le service d’assistance téléphonique (Conférence rendez-vous).  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5081  |TCP  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5082  |TCP (TLS)  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|serveurs frontaux  |Service de partage d’application Skype entreprise Server  |5065  |TCP  |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  |
|serveurs frontaux  |Service de partage d’application Skype entreprise Server  |49152-65535  |TCP  |Plage de ports multimédias utilisée pour le partage d’application.  |
|serveurs frontaux  |Service d’annonce de conférences Skype entreprise Server  |5073  |TCP  |Utilisé pour les demandes SIP entrantes pour le service d’annonce de conférence Skype entreprise Server (c’est-à-dire pour la Conférence rendez-vous).  |
|serveurs frontaux  |Service de parc d’appels Skype entreprise Server  |5075  |TCP  |Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.  |
|serveurs frontaux  |Service de test audio de Skype entreprise Server  |5076  |TCP  |Utilisé pour les demandes SIP entrantes du service de test audio.  |
|Serveurs frontaux  |Non applicable  |5066  |TCP  |Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.  |
|serveurs frontaux  |Service Response Group de Skype entreprise Server  |5071  |TCP  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Service Response Group de Skype entreprise Server  |8404  |TCP (MTLS)  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Service de stratégie de bande passante Skype entreprise Server  |5080  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.  |
|Serveurs frontaux  |Accès au serveur du partage de fichiers Skype entreprise Server  |445   |SMB/TCP  | Permet de récupérer le carnet d’adresses, le contenu de la réunion et d’autres éléments stockés sur le serveur de partage de fichiers.  |
|serveurs frontaux  |Service de stratégie de bande passante Skype entreprise Server  |448  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Skype entreprise Server.  |
|Serveurs frontaux dans lesquels réside le magasin de gestion central  | Service principal de l’agent réplicateur de Skype entreprise Server |445  |TCP  |Utilisé pour transmettre les données de configuration du magasin central de gestion aux serveurs exécutant Skype entreprise Server.  |
|Tous les serveurs  |SQL Browser  |1434  |UDP  |Navigateur SQL pour la copie locale répliquée des données du magasin de gestion central dans l’instance SQL Server locale  |
|Tous les serveurs internes  |Divers  |49152-57500  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui terminent les appels audio: serveurs frontaux (pour le service de surveillance des conférences Skype entreprise Server, service d’annonce de conférences Skype entreprise Server et service de conférence audio/vidéo Skype entreprise Server), et Serveur de médiation.  |
|Serveurs Office Web Apps Server  ||443  ||Utilisé par Skype entreprise Server pour la connexion à Office Web Apps Server.  |
|directeurs  |Service frontal Skype entreprise Server  |5060  |TCP  |Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|directeurs  |Service frontal Skype entreprise Server  |444  |HTTPS  <br/> TCP  |Communication entre serveurs frontaux et directeurs. Par ailleurs, le certificat client est publié (pour les serveurs frontaux) ou validé si le certificat client a déjà été publié.  |
|directeurs  |Service de compatibilité Web Skype entreprise Server  |80  |TCP  |Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.  |
|Directeurs  |Service de compatibilité Web Skype entreprise Server  |443  |HTTPS  |Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  |
|directeurs  |Service frontal Skype entreprise Server  |5061  |TCP  |Utilisé pour les communications internes entre serveurs et pour les connexions client.  |
|serveurs de médiation  |Service de médiation Skype entreprise Server  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.  |
|serveurs de médiation  |Service de médiation Skype entreprise Server  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Service de médiation Skype entreprise Server  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Service de médiation Skype entreprise Server  |5070  |TCP (MTLS)  |Utilisé pour les demandes SIP des serveurs frontaux.  |
|Serveur frontal de conversation permanente  |SIP de conversation permanente  |5041  |TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Windows Communication Foundation (WCF) de conversation permanente  |881  |TCP (TLS) et TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Service de transfert de fichiers de conversation permanente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Même si Skype entreprise Server n’utilise plus le port TCP 5060, lors du déploiement d’un contrôle d’appel distant, vous créez une configuration de serveur approuvé qui associe le nom de domaine complet du serveur de ligne RCC au port TCP qu’utilise le serveur principal ou le directeur pour se connecter à Système PBX. Pour plus d’informations, reportez-vous à la cmdlet **CsTrustedApplicationComputer** dans la documentation de Skype entreprise Server Management Shell.
  
Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.
  
**Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé**

|Programme d’équilibrage de charge|Port|Protocole|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  |5061  |TCP (TLS)  |
|Programme d’équilibrage de charge du serveur frontal  |444  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |135  |DCOM et appel de procédure distante (RPC)  |
|Programme d’équilibrage de charge du serveur frontal  |80  |HTTP  |
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP-client et récupération de périphériques du certificat racine du serveur frontal-clients et périphériques authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |443  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du serveur frontal  |5072  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5073  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5075  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5076  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5071  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5080  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |448  |TCP  |
|Programme d’équilibrage de charge du serveur de médiation  |5070  |TCP  |
|Programme d’équilibrage de charge du serveur frontal (si le pool exécute également le serveur de médiation)  |5070  |TCP  |
|Programme d’équilibrage de charge du directeur  |443  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |444  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |5061  |TCP  |
|Programme d’équilibrage de charge du directeur  |4443  |HTTPS (du proxy inverse)  |
   
Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.
  
**Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé**

|Programme d’équilibrage de charge|Port|Protocole|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  |80  |HTTP  |
|Programme d’équilibrage de charge du serveur frontal  |443  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP-client et récupération de périphériques du certificat racine du serveur frontal-clients et périphériques authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du directeur  |443  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |4443  |HTTPS (du proxy inverse)  |

**Ports client requis**

|Composant|Port|Protocole|Remarques|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Utilisé par Skype entreprise Server pour trouver le nom de domaine complet (FQDN) du Bureau d’enregistrement (autrement dit, en cas d’échec de la configuration manuelle de DNS SRV et de paramètres manuels).  |
|Clients  |443  |TCP (TLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |443  |TCP (PSOM/TLS)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence Web.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  |
|Clients  |5061  |TCP (MTLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |6891-6901  |TCP  |Utilisé pour le transfert de fichiers entre clients Skype entreprise et clients précédents.  |
|Clients  |1024-65535\*  |TCP/UDP  |Plage de ports audio (au moins 20 ports requis).  |
|Clients  |1024-65535\*  |TCP/UDP  |Plage de ports vidéo (au moins 20 ports requis).  |
|Clients  |1024-65535\*  |TCP  |Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.  |
|Clients  |1024-65535\*  |TCP  |Partage d’application.  |
|Téléphone de partie commune Aastra 6721ip  <br/> Téléphone de bureau Aastra 6725ip  <br/> Téléphone IP HP 4110 (téléphone de partie commune)  <br/> Téléphone IP HP 4120 (téléphone de bureau)  <br/> Téléphone de partie commune IP Polycom CX500  <br/> Téléphone de bureau IP Polycom CX600  <br/> Téléphone de bureau IP CX700  <br/> Téléphone de conférence IP Polycom CX3000  |67/68  |DHCP  |Utilisé par les périphériques indiqués pour trouver le certificat Skype entreprise Server, le FQDN de mise en service et le nom de domaine complet du Bureau d’enregistrement.  |
   
\*Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de applet de CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort et les paramètres ClientMediaPortRange).
  
> [!NOTE]
> Les programmes d’installation pour les clients Skype entreprise créent automatiquement les exceptions de pare-feu système d’exploitation requises sur l’ordinateur client. 

> [!NOTE]
> Les ports utilisés pour l’accès utilisateur externe sont requis pour tout scénario dans lequel le client doit traverser le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations). 
  
## <a name="ipsec-exceptions"></a>Exceptions IPsec

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des vidéos panoramiques. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.
  
Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec. 
  
**Exceptions recommandées pour IPsec**

|Nom de la règle|Adresse IP source|Adresse IP de destination|Protocole|Port source|Port de destination|Besoin d’authentification|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Serveur Edge A/V, ports internes/entrants  |Indifférente  |Serveur Edge A/V - interne  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur Edge A/V, ports externes/entrants  |Indifférente  |Serveur Edge A/V - externe  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur Edge A/V, ports internes/sortants  |Serveur Edge A/V - interne  |Indifférente  |TCP &amp; UDP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur Edge A/V, ports externes/sortants  |Serveur Edge A/V - externe  |Indifférente  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur de médiation, ports entrants  |Indifférente  |Serveur(s)  <br/> de médiation  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur de médiation, ports sortants  |Serveur(s)  <br/> de médiation  |Indifférente  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Intendant Conférence entrant  |Indifférente  |Serveur frontal exécutant l’Intendant Conférence  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Intendant Conférence sortant  |Serveur frontal exécutant l’Intendant Conférence  |Indifférente  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur de conférence A/V, ports entrants  |Indifférente  |serveurs frontaux  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Conférence A/V, ports sortants  |Serveurs frontaux  |Indifférente  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Exchange, ports entrants  |Indifférente  |Messagerie unifiée Exchange  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveurs de partage d’application, ports entrants  |Indifférente  |Serveurs de partage d’application  |TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur de partage d’application, ports sortants  |Serveurs de partage d’application  |Indifférente  |TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Exchange, ports sortants  |Messagerie unifiée Exchange  |Indifférente  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Clients  |Indifférente   |Indifférente  |UDP  |Plage de ports multimédias définie  |Indifférente  |Ne pas authentifier  |
