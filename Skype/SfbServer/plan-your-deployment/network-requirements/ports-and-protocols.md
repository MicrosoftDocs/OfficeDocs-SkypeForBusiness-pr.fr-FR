---
title: Ports et protocoles requis pour les serveurs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Résumé : Passez en revue les considérations de l’utilisation du port avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: a014df31ad27e5ed89b97fd7ca09979d4cfb5661
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069511"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Ports et protocoles requis pour les serveurs
 
**Résumé :** Passez en revue les considérations de l’utilisation du port avant d’implémenter Skype pour Business Server.
  
Skype pour Business Server nécessite que les pare-feu internes et externes des ports spécifiques soient ouverts. De plus, si la sécurité IPsec (Internet Protocol security) est déployée dans votre organisation, elle doit être désactivée sur la plage de ports utilisée pour l’acheminement des flux audio, vidéo et de vidéo panoramique. 
  
Alors que cela peut sembler un bit complexe dans un premier temps, l’essentiel pour la planification de ce peut être effectuée à l’aide de la [Skype pour l’outil de planification de Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Une fois que vous avez vérifié les questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez vous pouvez afficher le rapport de pare-feu dans le rapport et utiliser les informations pour créer des règles yourfirewall répertoriées. Vous pouvez également ajuster à la plupart des noms et des adresses IP utilisées, pour plus d’informations consultez [examen du rapport de pare-feu](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Gardez en vous pouvez exporter le rapport vers une feuille de calcul Excel, et le rapport de pare-feu sera une des feuilles de calcul dans le fichier. 
  
Vous trouverez également les informations dans ces tables sous forme de diagramme en examinant le poster des charges de protocole lié déconnecte l’article [Technical diagrams pour Skype pour Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Si vous implémentez Skype pour Business Online (O365) faire référence à [Office 365 URL et plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Environnements hybrides vous devrez faire référence à cette rubrique et également [planifier la connectivité hybride](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Vous peut avoir des pare-feu matériels ou logiciels, nous ne nécessitent pas de modèles spécifiques ou des versions. Important est quels ports sont autorisés pour le pare-feu ne nuit au fonctionnement de Skype pour Business Server.
  
## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

Cette section résume les ports et protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un Skype pour le déploiement de serveur d’entreprise.
  
> [!NOTE]
> Démarrage de Skype pour Business Server, il ouvre les ports requis dans le pare-feu Windows. Le pare-feu Windows doit déjà en cours d’exécution dans les applications plus normales, mais si elle n’est pas utilisé Skype pour Business Server fonctionneront sans lui. 
  
Pour plus d’informations sur la configuration du pare-feu pour les composants edge, voir [les scénarios de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne. 
  
**Ports de serveurs requis (par rôle serveur)**

|Rôle serveur|Nom du service|Port|Protocole|Remarques|
|:-----|:-----|:-----|:-----|:-----|
|Tous les serveurs  |SQL Browser  |1434  |UDP  |SQL Browser pour la copie répliquée locale de la base de données du magasin Central de gestion.  |
|serveurs frontaux  |Skype pour le service Business Server frontal  |5060  |TCP  |Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|serveurs frontaux  |Skype pour le service Business Server frontal  |5061  | TCP (TLS) |Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.  |
| Serveurs frontaux |Skype pour le service Business Server frontal  |444  | HTTPS <br/> TCP  |Utilisé pour les communications HTTPS entre le Focus (le Skype pour composant Business Server qui gère l’état des conférences) et les serveurs individuels.  <br/> Ce port est également utilisé pour les communications TCP entre Survivable Branch Appliances et les serveurs frontaux.  |
|serveurs frontaux  |Skype pour le service Business Server frontal  |135  |DCOM et appel de procédure distante (RPC)  |Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.  |
|serveurs frontaux  |Skype pour le service de conférence par messagerie instantanée Business Server  |5062  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  |
|serveurs frontaux  |Skype pour le service de conférence Web Business Server  |8057  |TCP (TLS)  |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  |
|serveurs frontaux  |Skype pour le service de compatibilité de conférence Web Business Server  |8058  |TCP (TLS)  |Utilisé pour l’écoute des connexions de l’objet modèle PSOM (Persistent Shared) à partir du client Live Meeting et les versions antérieures de Skype pour Business Server.  |
|serveurs frontaux  |Skype pour le service de conférence Audio/vidéo Business Server  |5063  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  |
|serveurs frontaux  |Skype pour le service de conférence Audio/vidéo Business Server  |57501-65535  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences vidéo.  |
|serveurs frontaux  |Skype pour le service Business Server Web compatibilité  |80  |HTTP  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.  |
|serveurs frontaux  |Skype pour le service Business Server Web compatibilité  |443  |HTTPS  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  |
|serveurs frontaux  |Skype pour le service Business Server Web compatibilité  |8080  |TCP et HTTP  |Utilisé par les composants web pour l’accès externe.  |
|Serveurs frontaux  |Composant de serveur web  |4443  |HTTPS  |Communications HTTPS (du proxy inverse) et HTTPS inter-pool frontal pour connexion à la découverte automatique.  |
|Serveurs frontaux  |Composant de serveur web  |8060  |TCP (MTLS)  ||
|serveurs frontaux  |Composant de serveur web  |8061  |TCP (MTLS)  ||
|serveurs frontaux  |Composant des services de mobilité  |5086  |TCP (MTLS)  |Port SIP utilisé pour les processus internes des services de mobilité.  |
|serveurs frontaux  |Composant des services de mobilité  |5087  |TCP (MTLS)  |Port SIP utilisé pour les processus internes des services de mobilité.  |
|serveurs frontaux  |Composant des services de mobilité  |443  |HTTPS  ||
|serveurs frontaux  |Skype pour le service Business Server intendant (conférence rendez-vous)  |5064  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  |
|serveurs frontaux  |Skype pour le service Business Server intendant (conférence rendez-vous)  |5072  |TCP  |Utilisé pour les demandes SIP entrantes pour Attendant (conférences rendez-vous).  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype pour le service de médiation de serveur d’entreprise  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype pour le service de médiation de serveur d’entreprise  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype pour le service de médiation de serveur d’entreprise  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype pour le service de médiation de serveur d’entreprise  |5081  |TCP  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype pour le service de médiation de serveur d’entreprise  |5082  |TCP (TLS)  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|serveurs frontaux  |Skype pour le service de partage d’Application Business Server  |5065  |TCP  |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  |
|serveurs frontaux  |Skype pour le service de partage d’Application Business Server  |49152-65535  |TCP  |Plage de ports multimédias utilisée pour le partage d’application.  |
|serveurs frontaux  |Skype pour le service d’annonce de conférence Business Server  |5073  |TCP  |Utilisé pour les demandes SIP entrantes pour le Skype pour le service d’annonce de conférence Business Server (autrement dit, pour les conférences rendez-vous).  |
|serveurs frontaux  |Skype pour le service Business Server Call Park  |5075  |TCP  |Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.  |
|serveurs frontaux  |Skype pour le service de Test Audio du serveur Business  |5076  |TCP  |Utilisé pour les demandes SIP entrantes du service de test audio.  |
|Serveurs frontaux  |Non applicable  |5066  |TCP  |Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.  |
|serveurs frontaux  |Skype pour le service Response Group Business Server  |5071  |TCP  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Skype pour le service Response Group Business Server  |8404  |TCP (MTLS)  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Skype pour le Service de stratégie de bande passante Business Server  |5080  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.  |
|Serveurs frontaux  |Skype pour accéder au serveur de partage de fichiers Business Server  |445   |SMB/TCP  | Utilisé pour récupérer le carnet d’adresses, contenu de la réunion et autres éléments stockés sur le serveur de partage de fichiers.  |
|serveurs frontaux  |Skype pour le Service de stratégie de bande passante Business Server  |448  |TCP  |Utilisé pour le contrôle d’admission des appels d’appel par le Skype pour le Service de stratégie de bande passante Business Server.  |
|Avant les serveurs frontaux où réside le magasin Central de gestion  | Skype pour le service de l’Agent réplicateur maître de serveur d’entreprise |445  |TCP  |Utilisé pour acheminer les données de configuration à partir du magasin Central de gestion vers des serveurs exécutant Skype pour Business Server.  |
|Tous les serveurs  |SQL Browser  |1434  |UDP  |SQL Browser pour la copie répliquée locale de gestion centrale stockent des données dans l’instance SQL Server locale  |
|Tous les serveurs internes  |Divers  |49152-57500  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisée par tous les serveurs qui se termine audio : serveurs frontaux (pour Skype pour le service Business Server intendant, Skype pour le service d’annonce de conférence Business Server et Skype pour le service de conférence Audio/vidéo Business Server), et Serveur de médiation.  |
|Serveurs Office Web Apps Server  ||443  ||Utilisé par Skype pour Business Server pour se connecter à Office Web Apps Server.  |
|directeurs  |Skype pour le service Business Server frontal  |5060  |TCP  |Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|directeurs  |Skype pour le service Business Server frontal  |444  |HTTPS  <br/> TCP  |Communication entre serveurs frontaux et directeurs. En outre, le certificat client publier (sur les serveurs frontaux) ou valider si le certificat client a déjà été publié.  |
|directeurs  |Skype pour le service Business Server Web compatibilité  |80  |TCP  |Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.  |
|Directeurs  |Skype pour le service Business Server Web compatibilité  |443  |HTTPS  |Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  |
|directeurs  |Skype pour le service Business Server frontal  |5061  |TCP  |Utilisé pour les communications internes entre serveurs et pour les connexions client.  |
|serveurs de médiation  |Skype pour le service de médiation de serveur d’entreprise  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.  |
|serveurs de médiation  |Skype pour le service de médiation de serveur d’entreprise  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Skype pour le service de médiation de serveur d’entreprise  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Skype pour le service de médiation de serveur d’entreprise  |5070  |TCP (MTLS)  |Utilisé pour les demandes SIP des serveurs frontaux.  |
|Serveur frontal de conversation permanente  |SIP de conversation permanente  |5041  |TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Windows Communication Foundation (WCF) de conversation permanente  |881  |TCP (TLS) et TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Service de transfert de fichiers de conversation permanente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Bien que Skype pour Business Server n’utilise plus le port TCP 5060, au cours du déploiement de contrôle d’appel distant, vous créez une configuration de serveurs approuvés, qui associe le FQDN du serveur de ligne de contrôle d’appel distant avec le port TCP que le serveur frontal ou directeur utilisera pour se connecter à la Système PBX. Pour plus d’informations, voir l’applet de commande **CsTrustedApplicationComputer** dans le Skype pour la documentation sur Business Server Management Shell.
  
Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.
  
**Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé**

|Programme d’équilibrage de charge|Port|Protocole|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  |5061  |TCP (TLS)  |
|Programme d’équilibrage de charge du serveur frontal  |444  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |135  |DCOM et appel de procédure distante (RPC)  |
|Programme d’équilibrage de charge du serveur frontal  |80  |HTTP  |
|Programme d’équilibrage de charge du serveur frontal  |8080  |Les clients TCP - récupération Client / périphérique du certificat racine depuis le serveur frontal - et périphériques authentifiés par NTLM  |
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
|Programme d’équilibrage de charge du serveur frontal  |8080  |Les clients TCP - récupération Client / périphérique du certificat racine depuis le serveur frontal - et périphériques authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du directeur  |443  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |4443  |HTTPS (du proxy inverse)  |

**Ports client requis**

|Composant|Port|Protocole|Remarques|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Utilisé par Skype pour Business Server pour trouver le nom de domaine complet du serveur d’inscriptions (autrement dit, si le DNS SRV échoue et que les paramètres manuels ne sont pas configurés).  |
|Clients  |443  |TCP (TLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |443  |TCP (PSOM/TLS)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence Web.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  |
|Clients  |5061  |TCP (MTLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |6891-6901  |TCP  |Utilisé pour le transfert de fichiers entre Skype pour les clients d’entreprise et les clients antérieurs.  |
|Clients  |1024-65535.\*  |TCP/UDP  |Plage de ports audio (au moins 20 ports requis).  |
|Clients  |1024-65535.\*  |TCP/UDP  |Plage de ports vidéo (au moins 20 ports requis).  |
|Clients  |1024-65535.\*  |TCP  |Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.  |
|Clients  |1024-65535.\*  |TCP  |Partage d’application.  |
|Téléphone de partie commune Aastra 6721ip  <br/> Téléphone de bureau Aastra 6725ip  <br/> Téléphone IP HP 4110 (téléphone de partie commune)  <br/> Téléphone IP HP 4120 (téléphone de bureau)  <br/> Téléphone de partie commune IP Polycom CX500  <br/> Téléphone de bureau IP Polycom CX600  <br/> Téléphone de bureau IP CX700  <br/> Téléphone de conférence IP Polycom CX3000  |67/68  |DHCP  |Utilisé par les périphériques répertoriés pour trouver le Skype pour le certificat de serveur d’entreprise, le nom de domaine complet mise en service et nom de domaine complet du serveur d’inscriptions.  |
   
\*Pour configurer des ports spécifiques pour ces types de média, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres ClientMediaPortRangeEnabled, ClientMediaPort et ClientMediaPortRange).
  
> [!NOTE]
> Les programmes d’installation pour Skype pour les clients professionnels créent automatiquement les exceptions requises du pare-feu du système d’exploitation sur l’ordinateur client. 

> [!NOTE]
> Les ports utilisés pour l’accès des utilisateurs externes sont requis pour tout scénario dans lequel le client doit traverser les pare-feu de l’organisation (par exemple, les communications externes ou aux réunions hébergées par d’autres organisations). 
  
## <a name="ipsec-exceptions"></a>Exceptions IPsec

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des vidéos panoramiques. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.
  
Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec. 
  
**Exceptions recommandées pour IPsec**

|Nom de la règle|Adresse IP source|Adresse IP de destination|Protocole|Port source|Port de destination|Besoin d’authentification|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Serveur Edge A/V, ports internes/entrants  |Indifférente  |Serveur Edge A/V - interne  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur Edge A/V, ports externes/entrants  |Indifférente  |Serveur Edge A/V - externe  |UDP et TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
|Serveur Edge A/V, ports internes/sortants  |Serveur Edge A/V - interne  |Indifférente  |UDP &amp; TCP  |Indifférente   |Indifférente  |Ne pas authentifier  |
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