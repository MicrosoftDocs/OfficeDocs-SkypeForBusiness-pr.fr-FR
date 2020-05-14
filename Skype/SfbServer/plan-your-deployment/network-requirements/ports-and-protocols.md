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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Résumé : Examinez les considérations relatives à l’utilisation des ports avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 09b0d187195faa0aa4b5278456991d9223427f9d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220384"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Configuration requise pour les ports et les protocoles pour les serveurs
 
**Résumé :** Examinez les considérations relatives à l’utilisation des ports avant d’implémenter Skype entreprise Server.
  
Skype entreprise Server requiert l’ouverture de ports spécifiques sur les pare-feu externe et interne. En outre, si la sécurité IPsec (Internet Protocol Security) est déployée dans votre organisation, IPsec doit être désactivé sur la plage de ports utilisée pour la fourniture de l’audio, de la vidéo et de la vidéo panoramique. 
  
Bien que cela puisse paraître un peu décourageante, l’important travail de planification de cette opération peut être réalisé à l’aide de l' [outil de planification de Skype entreprise Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Une fois que vous avez rencontré les questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez, vous pouvez afficher le rapport de pare-feu dans le rapport Edge admin et utiliser les informations qui y sont indiquées pour créer des règles yourfirewall. Vous pouvez également apporter des modifications à la plupart des noms et des adresses IP utilisés, pour plus d’informations, consultez [la rubrique Review the Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). N’oubliez pas que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel, et que le rapport de pare-feu sera l’une des feuilles de calcul du fichier. 
  
Vous pouvez également trouver les informations contenues dans ces tableaux sous forme de diagramme en examinant l’affiche relative aux charges de travail de protocole liées à l’article [diagrammes techniques de Skype entreprise Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Si vous implémentez Skype entreprise Online (Microsoft 365 ou Office 365), reportez-vous à la rubrique [URL et plages d’adresses IP microsoft 365 et office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Les environnements hybrides devront faire référence à cette rubrique et planifier également une [connectivité hybride](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Vous pouvez utiliser des pare-feu matériels ou logiciels, nous n’avons pas besoin de modèles ou de versions spécifiques. Quels sont les éléments qui concernent les ports autorisés, de sorte que le pare-feu ne nuit pas au fonctionnement de Skype entreprise Server.
  
## <a name="port-and-protocol-details"></a>Détails des ports et protocoles

Cette section récapitule les ports et les protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un déploiement Skype entreprise Server.
  
> [!NOTE]
> Lorsque Skype entreprise Server démarre, il ouvre les ports requis dans le pare-feu Windows. Le pare-feu Windows doit déjà être en cours d’exécution dans la plupart des applications normales, mais s’il n’est pas utilisé, Skype entreprise Server ne fonctionnera pas. 
  
Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, consultez la rubrique [scénarios de serveur Edge dans Skype entreprise server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne. 
  
**Ports de serveurs requis (par rôle serveur)**

|Rôle serveur|Nom du service|Port|Protocole|Notes|
|:-----|:-----|:-----|:-----|:-----|
|Tous les serveurs  |SQL Browser  |1434  |DATAGRAMME  |SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.  |
|Serveurs frontaux  |Service frontal Skype entreprise Server  |5060  |TCP  |Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|Serveurs frontaux  |Service frontal Skype entreprise Server  |5061  | TCP (TLS) |Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec un serveur de surveillance.  |
| Serveurs frontaux |Service frontal Skype entreprise Server  |444  | HTTPS <br/> TCP  |Utilisé pour les communications HTTPs entre le focus (le composant Skype entreprise Server qui gère l’état des conférences) et les serveurs individuels.  <br/> Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliances et les serveurs frontaux.  |
|Serveurs frontaux  |Service frontal Skype entreprise Server  |135  |DCOM et appel de procédure distante (RPC)  |Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.  |
|Serveurs frontaux  |Service de conférence par messagerie instantanée Skype entreprise Server  |5062  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  |
|Serveurs frontaux  |Service de conférence Web Skype entreprise Server  |8057  |TCP (TLS)  |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  |
|Serveurs frontaux  |Service de compatibilité de conférence Web Skype entreprise Server  |8058  |TCP (TLS)  |Utilisé pour l’écoute des connexions PSOM (persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Skype entreprise Server.  |
|Serveurs frontaux  |Service de conférence audio/vidéo Skype entreprise Server  |5063  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  |
|Serveurs frontaux  |Service de conférence audio/vidéo Skype entreprise Server  |57501-65535  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences vidéo.  |
|Serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |80  |HTTP  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.  |
|Serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |443  |HTTPS  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).  |
|Serveurs frontaux  |Service de compatibilité Web Skype entreprise Server  |8080  |TCP et HTTP  |Utilisé par les composants Web pour l’accès externe.  |
|Serveurs frontaux  |Composant serveur Web  |4443  |HTTPS  |HTTPs (des proxys inverses) et les communications inter-pool frontaux HTTPs pour la connexion au service de découverte automatique.  |
|Serveurs frontaux  |Composant serveur Web  |8060  |TCP (MTLS)  ||
|Serveurs frontaux  |Composant serveur Web  |8061  |TCP (MTLS)  ||
|Serveurs frontaux  |Composant des services de mobilité  |5086  |TCP (MTLS)  |Port SIP utilisé par les processus internes des services de mobilité  |
|Serveurs frontaux  |Composant des services de mobilité  |5087  |TCP (MTLS)  |Port SIP utilisé par les processus internes des services de mobilité  |
|Serveurs frontaux  |Composant des services de mobilité  |443  |HTTPS  ||
|Serveurs frontaux  |Service de surveillance de conférence Skype entreprise Server (Conférence rendez-vous)  |5064  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  |
|Serveurs frontaux  |Service de surveillance de conférence Skype entreprise Server (Conférence rendez-vous)  |5072  |TCP  |Utilisé pour les demandes SIP entrantes pour le service de surveillance (Conférence rendez-vous).  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5081  |TCP  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Service de médiation Skype entreprise Server  |5082  |TCP (TLS)  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux  |Service de partage d’application Skype entreprise Server  |5065  |TCP  |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  |
|Serveurs frontaux  |Service de partage d’application Skype entreprise Server  |49152-65535  |TCP  |Plage de ports multimédias utilisée pour le partage d’application.  |
|Serveurs frontaux  |Service d’annonce de conférence Skype entreprise Server  |5073  |TCP  |Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Skype entreprise Server (c’est-à-dire pour les conférences rendez-vous).  |
|Serveurs frontaux  |Service de parcage d’appel Skype entreprise Server  |5075  |TCP  |Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.  |
|Serveurs frontaux  |Service de test audio Skype entreprise Server  |5076  |TCP  |Utilisé pour les demandes SIP entrantes du service de test audio.  |
|Serveurs frontaux  |Non applicable  |5066  |TCP  |Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.  |
|Serveurs frontaux  |Service Response Group de Skype entreprise Server  |5071  |TCP  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Service Response Group de Skype entreprise Server  |8404  |TCP (MTLS)  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Service de stratégie de bande passante de Skype entreprise Server  |5080  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.  |
|Serveurs frontaux  |Accès au serveur de partage de fichiers Skype entreprise Server  |445   |SMB/TCP  | Permet de récupérer le carnet d’adresses, le contenu de la réunion et d’autres éléments stockés sur le serveur de partage de fichiers.  |
|Serveurs frontaux  |Service de stratégie de bande passante de Skype entreprise Server  |448  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Skype entreprise Server.  |
|Serveurs frontaux où réside le magasin central de gestion  | Service d’agent réplicateur principal Skype entreprise Server |445  |TCP  |Utilisé pour envoyer des données de configuration à partir du magasin central de gestion vers les serveurs exécutant Skype entreprise Server.  |
|Tous les serveurs  |SQL Browser  |1434  |DATAGRAMME  |SQL Browser pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale  |
|Tous les serveurs internes  |Divers  |49152-57500  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui terminent l’audio : les serveurs frontaux (pour le service de surveillance de conférence Skype entreprise Server, le service d’annonce de conférence Skype entreprise Server et le service de conférence audio/vidéo Skype entreprise Server) et le serveur de médiation.  |
|Serveurs Office Web Apps  ||443  ||Utilisé par Skype entreprise Server pour se connecter à Office Web Apps Server.  |
|Directeurs  |Service frontal Skype entreprise Server  |5060  |TCP  |Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|Directeurs  |Service frontal Skype entreprise Server  |444  |HTTPS  <br/> TCP  |Communication entre serveurs frontaux et directeurs. De plus, le certificat client doit être publié (sur les serveurs frontaux) ou validé si le certificat client a déjà été publié.  |
|Directeurs  |Service de compatibilité Web Skype entreprise Server  |80  |TCP  |Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.  |
|Directeurs  |Service de compatibilité Web Skype entreprise Server  |443  |HTTPS  |Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).  |
|Directeurs  |Service frontal Skype entreprise Server  |5061  |TCP  |Utilisé pour les communications internes entre serveurs et pour les connexions client.  |
|serveurs de médiation  |Service de médiation Skype entreprise Server  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.  |
|serveurs de médiation  |Service de médiation Skype entreprise Server  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Service de médiation Skype entreprise Server  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Service de médiation Skype entreprise Server  |5070  |TCP (MTLS)  |Utilisé pour les demandes SIP des serveurs frontaux.  |
|Serveur frontal de conversation permanente  |SIP de conversation permanente  |5041  |TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Conversation permanente Windows Communication Foundation (WCF)  |881  |TCP (TLS) et TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Service de transfert de fichiers de conversation permanente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Bien que Skype entreprise Server n’utilise plus le port TCP 5060, pendant le déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou directeur utilisera pour se connecter au système PBX. Pour plus d’informations, reportez-vous à l’applet de commande **CsTrustedApplicationComputer** dans la documentation de Skype entreprise Server Management Shell.
  
Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.
  
**Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé**

|Programme d’équilibrage de charge|Port|Protocole|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  |5061  |TCP (TLS)  |
|Programme d’équilibrage de charge du serveur frontal  |444  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |135  |DCOM et appel de procédure distante (RPC)  |
|Programme d’équilibrage de charge du serveur frontal  |80  |HTTP  |
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP-récupération de client et de périphérique du certificat racine à partir du serveur frontal-clients et appareils authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |443  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du serveur frontal  |5072  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5073  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5075  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5076  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5071  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5080  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |448  |TCP  |
|Programme d’équilibrage de la charge du serveur de médiation  |5070  |TCP  |
|Programme d’équilibrage de la charge du serveur frontal (si le pool exécute également le serveur de médiation)  |5070  |TCP  |
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
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP-récupération de client et de périphérique du certificat racine à partir du serveur frontal-clients et appareils authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du directeur  |443  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |4443  |HTTPS (du proxy inverse)  |

**Ports client requis**

|Composant|Port|Protocole|Notes|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |SERVICE  |Utilisé par Skype entreprise Server pour rechercher le nom de domaine complet (FQDN) du serveur d’inscriptions (en d’autres points, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).  |
|Clients  |443  |TCP (TLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |443  |TCP (PSOM/TLS)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)  |
|Clients  |5061  |TCP (MTLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |6891-6901  |TCP  |Utilisé pour le transfert de fichiers entre les clients Skype entreprise et les clients précédents.  |
|Clients  |1024-65535\*  |TCP/UDP  |Plage de ports audio (au moins 20 ports requis).  |
|Clients  |1024-65535\*  |TCP/UDP  |Plage de ports vidéo (au moins 20 ports requis).  |
|Clients  |1024-65535\*  |TCP  |Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.  |
|Clients  |1024-65535\*  |TCP  |Partage d’application.  |
|Téléphone de partie commune Aastra 6721ip  <br/> Téléphone de bureau Aastra 6725ip  <br/> Téléphone IP HP 4110 (téléphone de partie commune)  <br/> Téléphone IP HP 4120 (téléphone de bureau)  <br/> Téléphone de partie commune IP Polycom CX500  <br/> Téléphone de bureau IP Polycom CX600  <br/> Téléphone de bureau IP CX700  <br/> Téléphone de conférence IP Polycom CX3000  |67/68  |SERVICE  |Utilisé par les appareils cités pour rechercher le certificat Skype entreprise Server, le nom de domaine complet (FQDN) de mise en service et le nom de domaine complet du serveur d’inscriptions.  |
   
\*Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres clientmediaportrangeenabled, ClientMediaPort et ClientMediaPortRange).
  
> [!NOTE]
> Les programmes d’installation pour les clients Skype entreprise créent automatiquement les exceptions de pare-feu de système d’exploitation requises sur l’ordinateur client. 

> [!NOTE]
> Les ports utilisés pour l’accès des utilisateurs externes sont requis pour tout scénario dans lequel le client doit traverser le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations). 
  
## <a name="ipsec-exceptions"></a>Exceptions IPsec

Pour les réseaux d’entreprise sur lesquels la sécurité du protocole Internet (IPsec) (voir IETF RFC 4301-4309) a été déployée, IPsec doit être désactivé sur la plage de ports utilisée pour la livraison de l’audio, de la vidéo et de la vidéo panoramique. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.
  
Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec. 
  
**Exceptions recommandées pour IPsec**

|Nom de la règle|Adresse IP source|Adresse IP de destination|Protocole|Port source|Port de destination|Besoin d’authentification|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Serveur Edge A/V, ports internes/entrants  |N'importe lequel  |Serveur Edge A/V - interne  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur Edge A/V, ports externes/entrants  |N'importe lequel  |Serveur Edge A/V - externe  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur Edge A/V, ports internes/sortants  |Serveur Edge A/V - interne  |N'importe lequel  |&amp;TCP UDP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur Edge A/V, ports externes/sortants  |Serveur Edge A/V - externe  |N'importe lequel  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur de médiation, ports entrants  |N'importe lequel  |Élaboration  <br/> Serveur (s)  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur de médiation, ports sortants  |Élaboration  <br/> Serveur (s)  |N'importe lequel  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Intendant Conférence entrant  |N'importe lequel  |Serveur frontal exécutant l’Intendant Conférence  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Intendant Conférence sortant  |Serveur frontal exécutant l’Intendant Conférence  |N'importe lequel  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur de conférence A/V, ports entrants  |N'importe lequel  |Serveurs frontaux  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Conférence A/V, ports sortants  |Serveurs frontaux  |N'importe lequel  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Exchange, ports entrants  |N'importe lequel  |Messagerie unifiée Exchange  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveurs de partage d’application, ports entrants  |N'importe lequel  |Serveurs de partage d’application  |TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Serveur de partage d’application, ports sortants  |Serveurs de partage d’application  |N'importe lequel  |TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Exchange, ports sortants  |Messagerie unifiée Exchange  |N'importe lequel  |UDP et TCP  |N'importe lequel  |N'importe lequel  |Ne pas authentifier  |
|Clients  |N'importe lequel  |N'importe lequel  |DATAGRAMME  |Plage de ports multimédias définie  |N'importe lequel  |Ne pas authentifier  |
