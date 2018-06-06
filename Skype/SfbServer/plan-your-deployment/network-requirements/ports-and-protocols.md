---
title: Ports et protocoles requis pour les serveurs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Résumé : Passez en revue les considérations de l’utilisation du port avant d’implémenter Skype pour Business Server 2015.'
ms.openlocfilehash: 9f47cf2f04db02765f9693b1128fe1f9440b59e6
ms.sourcegitcommit: a612ebe25e06c2cb090f776325712caf3cf3b943
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/06/2018
ms.locfileid: "19630153"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Ports et protocoles requis pour les serveurs
 
**Résumé :** Passez en revue les considérations de l’utilisation du port avant d’implémenter Skype pour Business Server 2015.
  
Skype pour Business Server nécessite que les pare-feu internes et externes des ports spécifiques soient ouverts. De plus, si la sécurité IPsec (Internet Protocol security) est déployée dans votre organisation, elle doit être désactivée sur la plage de ports utilisée pour l’acheminement des flux audio, vidéo et de vidéo panoramique. 
  
Alors que cela peut sembler un bit complexe dans un premier temps, l’essentiel pour la planification de ce peut être effectuée à l’aide de la [Skype pour l’outil de planification de Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Une fois que vous avez vérifié les questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez vous pouvez afficher le rapport de pare-feu dans le rapport et utiliser les informations pour créer des règles yourfirewall répertoriées. Vous pouvez également ajuster à la plupart des noms et des adresses IP utilisées, pour plus d’informations consultez [examen du rapport de pare-feu](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Gardez en vous pouvez exporter le rapport vers une feuille de calcul Excel, et le rapport de pare-feu sera une des feuilles de calcul dans le fichier. 
  
Vous trouverez également les informations dans ces tables sous forme de diagramme en examinant le poster des charges de protocole lié déconnecte l’article [Technical diagrams pour Skype pour Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Skype pour les utilisateurs professionnels Online doit faire référence à [Office 365 URL et plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). 
> - Vous peut avoir des pare-feu matériels ou logiciels, nous ne nécessitent pas de modèles spécifiques ou des versions. Important est quels ports sont autorisés pour le pare-feu ne nuit au fonctionnement de Skype pour Business Server.
  
## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

Cette section résume les ports et protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un Skype pour le déploiement de serveur d’entreprise.
  
> [!NOTE]
> Démarrage de Skype pour Business Server, il ouvre les ports requis dans le pare-feu Windows. Le pare-feu Windows doit déjà en cours d’exécution dans les applications plus normales, mais si elle n’est pas utilisé Skype pour Business Server fonctionneront sans lui. 
  
Pour plus d’informations sur la configuration du pare-feu pour les composants edge, voir [les scénarios de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne. 
  
**Ports de serveurs requis (par rôle de serveur)**

|**Rôle de serveur**|**Nom de service**|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|Tous les serveurs  <br/> |SQL Browser  <br/> |1434  <br/> |UDP  <br/> |SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server frontal  <br/> |5060  <br/> |TCP  <br/> |Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server frontal  <br/> |5061  <br/> | TCP (TLS) <br/> |Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.  <br/> |
| Serveurs frontaux <br/> |Skype pour le service Business Server frontal  <br/> |444  <br/> | HTTPS <br/> TCP  <br/> |Utilisé pour les communications HTTPS entre le Focus (le Skype pour composant Business Server qui gère l’état des conférences) et les serveurs individuels.  <br/> Ce port est également utilisé pour les communications TCP entre Survivable Branch Appliances et les serveurs frontaux.  <br/> |
|serveurs frontaux  <br/> |Skype pour le service Business Server frontal  <br/> |135  <br/> |DCOM et appel de procédure distante (RPC)  <br/> |Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de conférence par messagerie instantanée Business Server  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de conférence Web Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de compatibilité de conférence Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions de l’objet modèle PSOM (Persistent Shared) à partir du client Live Meeting et les versions antérieures de Skype pour Business Server.  <br/> |
|serveurs frontaux  <br/> |Skype pour le service de conférence Audio/vidéo Business Server  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de conférence Audio/vidéo Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server Web compatibilité  <br/> |80  <br/> |HTTP  <br/> |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server Web compatibilité  <br/> |443  <br/> |HTTPS  <br/> |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server Web compatibilité  <br/> |8080  <br/> |TCP et HTTP  <br/> |Utilisé par les composants web pour l’accès externe.  <br/> |
|Serveurs frontaux  <br/> |Composant de serveur web  <br/> |4443  <br/> |HTTPS  <br/> |Communications HTTPS (du proxy inverse) et HTTPS inter-pool frontal pour connexion à la découverte automatique.  <br/> |
|Serveurs frontaux  <br/> |Composant de serveur web  <br/> |8060  <br/> |TCP (MTLS)  <br/> ||
|Serveurs frontaux  <br/> |Composant de serveur web  <br/> |8061  <br/> |TCP (MTLS)  <br/> ||
|Serveurs frontaux  <br/> |Composant des services de mobilité  <br/> |5086  <br/> |TCP (MTLS)  <br/> |Port SIP utilisé pour les processus internes des services de mobilité.  <br/> |
|Serveurs frontaux  <br/> |Composant des services de mobilité  <br/> |5087  <br/> |TCP (MTLS)  <br/> |Port SIP utilisé pour les processus internes des services de mobilité.  <br/> |
|Serveurs frontaux  <br/> |Composant des services de mobilité  <br/> |443  <br/> |HTTPS  <br/> ||
|Serveurs frontaux  <br/> |Skype pour le service Business Server intendant (conférence rendez-vous)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server intendant (conférence rendez-vous)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour Attendant (conférences rendez-vous).  <br/> |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5070  <br/> |TCP  <br/> |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.  <br/> |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5067  <br/> |TCP (TLS)  <br/> |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  <br/> |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5068  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  <br/> |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5081  <br/> |TCP  <br/> |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  <br/> |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5082  <br/> |TCP (TLS)  <br/> |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de partage d’Application Business Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de partage d’Application Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service d’annonce de conférence Business Server  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le Skype pour le service d’annonce de conférence Business Server (autrement dit, pour les conférences rendez-vous).  <br/> |
|serveurs frontaux  <br/> |Skype pour le service Business Server Call Park  <br/> |5075  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de Test Audio du serveur Business  <br/> |5076  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes du service de test audio.  <br/> |
|Serveurs frontaux  <br/> |Non applicable  <br/> |5066  <br/> |TCP  <br/> |Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Response Group Business Server  <br/> |5071  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes de l’application Response Group.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Response Group Business Server  <br/> |8404  <br/> |TCP (MTLS)  <br/> |Utilisé pour les demandes SIP entrantes de l’application Response Group.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le Service de stratégie de bande passante Business Server  <br/> |5080  <br/> |TCP  <br/> |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le Service de stratégie de bande passante Business Server  <br/> |448  <br/> |TCP  <br/> |Utilisé pour le contrôle d’admission des appels d’appel par le Skype pour le Service de stratégie de bande passante Business Server.  <br/> |
|Avant les serveurs frontaux où réside le magasin Central de gestion  <br/> | Skype pour le service de l’Agent réplicateur maître de serveur d’entreprise <br/> |445  <br/> |TCP  <br/> |Utilisé pour acheminer les données de configuration à partir du magasin Central de gestion vers des serveurs exécutant Skype pour Business Server.  <br/> |
|Tous les serveurs  <br/> |SQL Browser  <br/> |1434  <br/> |UDP  <br/> |SQL Browser pour la copie répliquée locale de gestion centrale stockent des données dans l’instance SQL Server locale  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisée par tous les serveurs qui se termine audio : serveurs frontaux (pour Skype pour le service Business Server intendant, Skype pour le service d’annonce de conférence Business Server et Skype pour le service de conférence Audio/vidéo Business Server), et Serveur de médiation.  <br/> |
|Serveurs Office Web Apps Server  <br/> ||443  <br/> ||Utilisé par Skype pour Business Server 2015 pour se connecter à Office Web Apps Server.  <br/> |
|directeurs  <br/> |Skype pour le service Business Server frontal  <br/> |5060  <br/> |TCP  <br/> |Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  <br/> |
|Directeurs  <br/> |Skype pour le service Business Server frontal  <br/> |444  <br/> |HTTPS  <br/> TCP  <br/> |Communication entre serveurs frontaux et directeurs. En outre, le certificat client publier (sur les serveurs frontaux) ou valider si le certificat client a déjà été publié.  <br/> |
|directeurs  <br/> |Skype pour le service Business Server Web compatibilité  <br/> |80  <br/> |TCP  <br/> |Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.  <br/> |
|Directeurs  <br/> |Skype pour le service Business Server Web compatibilité  <br/> |443  <br/> |HTTPS  <br/> |Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).  <br/> |
|Directeurs  <br/> |Skype pour le service Business Server frontal  <br/> |5061  <br/> |TCP  <br/> |Utilisé pour les communications internes entre serveurs et pour les connexions client.  <br/> |
|Serveurs de médiation  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5070  <br/> |TCP  <br/> |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.  <br/> |
|Serveurs de médiation  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5067  <br/> |TCP (TLS)  <br/> |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  <br/> |
|Serveurs de médiation  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5068  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  <br/> |
|Serveurs de médiation  <br/> |Skype pour le service de médiation de serveur d’entreprise  <br/> |5070  <br/> |TCP (MTLS)  <br/> |Utilisé pour les demandes SIP des serveurs frontaux.  <br/> |
|Serveur frontal de conversation permanente  <br/> |SIP de conversation permanente  <br/> |5041  <br/> |TCP (MTLS)  <br/> ||
|Serveur frontal de conversation permanente  <br/> |Windows Communication Foundation (WCF) de conversation permanente  <br/> |881  <br/> |TCP (TLS) et TCP (MTLS)  <br/> ||
|Serveur frontal de conversation permanente  <br/> |Service de transfert de fichiers de conversation permanente  <br/> |443  <br/> |TCP (TLS)  <br/> ||
   
> [!NOTE]
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Bien que Skype pour Business Server n’utilise plus le port TCP 5060, au cours du déploiement de contrôle d’appel distant, vous créez une configuration de serveurs approuvés, qui associe le FQDN du serveur de ligne de contrôle d’appel distant avec le port TCP que le serveur frontal ou directeur utilisera pour se connecter à la Système PBX. Pour plus d’informations, voir l’applet de commande **CsTrustedApplicationComputer** dans le Skype pour la documentation sur Business Server Management Shell.
  
Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.
  
**Ports du programme d’équilibrage de charge matérielle si vous utilisez uniquement d’équilibrage de charge**

|**Équilibrage de charge**|**Port**|**Protocole**|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  <br/> |5061  <br/> |TCP (TLS)  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |444  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |135  <br/> |DCOM et appel de procédure distante (RPC)  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |80  <br/> |HTTP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |8080  <br/> |Les clients TCP - récupération Client / périphérique du certificat racine depuis le serveur frontal - et périphériques authentifiés par NTLM  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |443  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |4443  <br/> |HTTPS (du proxy inverse)  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5072  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5073  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5075  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5076  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5071  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |5080  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |448  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur de médiation  <br/> |5070  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du serveur frontal (si le pool exécute également le serveur de médiation)  <br/> |5070  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |443  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |444  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |5061  <br/> |TCP  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |4443  <br/> |HTTPS (du proxy inverse)  <br/> |
   
Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.
  
**Ports du programme d’équilibrage de charge matérielle si l’équilibrage de charge DNS**

|**Équilibrage de charge**|**Port**|**Protocole**|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  <br/> |80  <br/> |HTTP  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |443  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |8080  <br/> |Les clients TCP - récupération Client / périphérique du certificat racine depuis le serveur frontal - et périphériques authentifiés par NTLM  <br/> |
|Programme d’équilibrage de charge du serveur frontal  <br/> |4443  <br/> |HTTPS (du proxy inverse)  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |443  <br/> |HTTPS  <br/> |
|Programme d’équilibrage de charge du directeur  <br/> |4443  <br/> |HTTPS (du proxy inverse)  <br/> |
   
**Ports Client requis**

|**Composant**|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |67/68  <br/> |DHCP  <br/> |Utilisé par Skype pour Business Server pour trouver le nom de domaine complet du serveur d’inscriptions (autrement dit, si le DNS SRV échoue et que les paramètres manuels ne sont pas configurés).  <br/> |
|Clients  <br/> |443  <br/> |TCP (TLS)  <br/> |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Clients  <br/> |443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence Web.  <br/> |
|Clients  <br/> |443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  <br/> |
|Clients  <br/> |3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  <br/> |
|Clients  <br/> |5061  <br/> |TCP (MTLS)  <br/> |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  <br/> |
|Clients  <br/> |6891-6901  <br/> |TCP  <br/> |Utilisé pour le transfert de fichiers entre Skype pour les clients d’entreprise et les clients antérieurs.  <br/> |
|Clients  <br/> |1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|Clients  <br/> |1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|Clients  <br/> |1024-65535.\*  <br/> |TCP  <br/> |Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.  <br/> |
|Clients  <br/> |1024-65535.\*  <br/> |TCP  <br/> |Partage d’application.  <br/> |
|Téléphone de partie commune Aastra 6721ip  <br/> Téléphone de bureau Aastra 6725ip  <br/> Téléphone IP HP 4110 (téléphone de partie commune)  <br/> Téléphone IP HP 4120 (téléphone de bureau)  <br/> Téléphone de partie commune IP Polycom CX500  <br/> Téléphone de bureau IP Polycom CX600  <br/> Téléphone de bureau IP CX700  <br/> Téléphone de conférence IP Polycom CX3000  <br/> |67/68  <br/> |DHCP  <br/> |Utilisé par les périphériques répertoriés pour trouver le Skype pour le certificat de serveur d’entreprise, le nom de domaine complet mise en service et nom de domaine complet du serveur d’inscriptions.  <br/> |
   
\*Pour configurer des ports spécifiques pour ces types de média, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres ClientMediaPortRangeEnabled, ClientMediaPort et ClientMediaPortRange).
  
> [!NOTE]
> Les programmes d’installation pour Skype pour les clients professionnels créent automatiquement les exceptions requises du pare-feu du système d’exploitation sur l’ordinateur client. 
  
> [!NOTE]
> Les ports utilisés pour l’accès des utilisateurs externes sont requis pour tout scénario dans lequel le client doit traverser les pare-feu de l’organisation (par exemple, les communications externes ou aux réunions hébergées par d’autres organisations). 
  
## <a name="ipsec-exceptions"></a>Exceptions IPsec

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des vidéos panoramiques. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.
  
Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec. 
  
**Exceptions recommandées pour IPsec**

|**Nom de la règle**|**Adresse IP source**|**Destination IP**|**Protocole**|**Port source**|**Port de destination**|**Besoin d’authentification**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Serveur Edge A/V, ports internes/entrants  <br/> |Indifférente  <br/> |Serveur Edge A/V - interne  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur Edge A/V, ports externes/entrants  <br/> |Indifférente  <br/> |Serveur Edge A/V - externe  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur Edge A/V, ports internes/sortants  <br/> |Serveur Edge A/V - interne  <br/> |Indifférente  <br/> |UDP &amp; TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur Edge A/V, ports externes/sortants  <br/> |Serveur Edge A/V - externe  <br/> |Indifférente  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur de médiation, ports entrants  <br/> |Indifférente  <br/> |Serveur(s)  <br/> de médiation  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur de médiation, ports sortants  <br/> |Serveur(s)  <br/> de médiation  <br/> |Indifférente  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Intendant Conférence entrant  <br/> |Indifférente  <br/> |Serveur frontal exécutant l’Intendant Conférence  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Intendant Conférence sortant  <br/> |Serveur frontal exécutant l’Intendant Conférence  <br/> |Indifférente  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur de conférence A/V, ports entrants  <br/> |Indifférente  <br/> |Serveurs frontaux  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Conférence A/V, ports sortants  <br/> |Serveurs frontaux  <br/> |Indifférente  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Exchange, ports entrants  <br/> |Indifférente  <br/> |Messagerie unifiée Exchange  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveurs de partage d’application, ports entrants  <br/> |Indifférente  <br/> |Serveurs de partage d’application  <br/> |TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Serveur de partage d’application, ports sortants  <br/> |Serveurs de partage d’application  <br/> |Indifférente  <br/> |TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Exchange, ports sortants  <br/> |Messagerie unifiée Exchange  <br/> |Indifférente  <br/> |UDP et TCP  <br/> |Indifférente  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
|Clients  <br/> |Indifférente  <br/> |Indifférente  <br/> |UDP  <br/> |Plage de ports multimédias définie  <br/> |Indifférente  <br/> |Ne pas authentifier  <br/> |
   

