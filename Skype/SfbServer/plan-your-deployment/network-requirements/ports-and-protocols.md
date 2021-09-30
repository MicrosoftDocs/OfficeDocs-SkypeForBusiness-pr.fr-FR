---
title: Exigences en matière de ports et de protocoles pour les serveurs
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Résumé : Examinez les considérations d’utilisation des ports avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: 2ed181bd7bbcdce772e7db88a29e60d4f78e9fe2
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012988"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Exigences en matière de ports et de protocoles pour les serveurs
 
**Résumé :** Examinez les considérations d’utilisation des ports avant d’implémenter Skype Entreprise Server.
  
Skype Entreprise Server requiert l’ouverture de ports spécifiques sur les pare-feu externes et internes. En outre, si la sécurité du protocole Internet (IPsec) est déployée dans votre organisation, IPsec doit être désactivé sur la plage de ports utilisée pour la distribution de l’audio, de la vidéo et de la vidéo panoramique. 
  
Bien que cela puisse sembler un peu difficile à faire, le travail de planification peut être effectué à l’aide de l’outil de planification de Skype Entreprise Server 2015. Une fois que vous avez répondu aux questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez, vous pouvez afficher le rapport de pare-feu dans le rapport d’administration Edge et utiliser les informations répertoriées ici pour créer vos règles de pare-feu. Vous pouvez également apporter des ajustements à la plupart des noms et adresses IP utilisés, pour plus d’informations, consultez le rapport de [pare-feu.](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report) Gardez à l’esprit que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel, et le rapport de pare-feu sera l’une des feuilles de calcul dans le fichier. 
  
Vous trouverez les informations dans ces tableaux sous forme de diagramme en reviewant l’affiche Charges de travail de protocole liées à partir de l’article Diagrammes techniques pour Skype Entreprise [Server 2015.](../../technical-diagrams.md)

> [!NOTE]
> - Si vous implémentez Skype Entreprise Online (Microsoft 365 ou Office 365), reportez-vous aux URL et [plages d’adresses IP Microsoft 365 et Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) Les environnements hybrides devront référencer cette rubrique et planifier [la connectivité hybride.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - Vous pouvez avoir un pare-feu matériel ou logiciel. Nous n’avons pas besoin de modèles ou de versions spécifiques. Ce qui importe, c’est les ports qui sont ajoutés à une liste d’adresses permises afin que le pare-feu ne nuise pas au fonctionnement de Skype Entreprise Server.
  
## <a name="port-and-protocol-details"></a>Détails des ports et protocoles

Cette section récapitule les ports et protocoles utilisés par les serveurs, les équilibreurs de charge et les clients dans un déploiement Skype Entreprise Server.
  
> [!NOTE]
> Lorsque Skype Entreprise Server démarre, il ouvre les ports requis dans le Pare-feu Windows. Le Pare-feu Windows doit déjà être en cours d’exécution dans la plupart des applications normales, mais s’il n’est pas utilisé, Skype Entreprise Server fonctionne sans lui. 
  
Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [Edge Server scenarios in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne. 
  
**Ports de serveurs requis (par rôle serveur)**

|Rôle serveur|Nom du service|Port|Protocole|Notes|
|:-----|:-----|:-----|:-----|:-----|
|Tous les serveurs  |SQL Browser  |1434  |UDP  |SQL navigateur pour la copie répliquée locale de la base de données du magasin central de gestion.  |
|Front-End serveurs  |Service d'Front-End Skype Entreprise Server  |5060  |TCP  |Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|Serveurs frontaux  |Service d'Front-End Skype Entreprise Server  |5061  | TCP (TLS) |Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec un serveur de surveillance.  |
| Serveurs frontaux |Service d'Front-End Skype Entreprise Server  |444  | HTTPS <br/> TCP  |Utilisé pour la communication HTTPS entre le focus (composant Skype Entreprise Server qui gère l’état de conférence) et les serveurs individuels.  <br/> Ce port est également utilisé pour la communication TCP entre les Survivable Branch Appliances et les serveurs frontux.  |
|Serveurs frontaux  |Service d'Front-End Skype Entreprise Server  |135  |DCOM et appel de procédure distante (RPC)  |Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.  |
|Serveurs frontaux  |Service de conférence de messagerie instantanée Skype Entreprise Server  |5062  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  |
|Serveurs frontaux  |Service de conférence web Skype Entreprise Server  |8057  |TCP (TLS)  |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  |
|Serveurs frontaux  |Service de compatibilité de conférence web Skype Entreprise Server  |8058  |TCP (TLS)  |Utilisé pour écouter les connexions PSOM (Persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Skype Entreprise Server.  |
|Serveurs frontaux  |Service de conférence audio/vidéo Skype Entreprise Server  |5063  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  |
|Serveurs frontaux  |Service de conférence audio/vidéo Skype Entreprise Server  |57501-65535  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences vidéo.  |
|Serveurs frontaux  |Service de compatibilité web Skype Entreprise Server  |80  |HTTP  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.  |
|Serveurs frontaux  |Service de compatibilité web Skype Entreprise Server  |443  |HTTPS  |Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).  |
|Serveurs frontaux  |Service de compatibilité web Skype Entreprise Server  |8080  |TCP et HTTP  |Utilisé par les composants web pour l’accès externe.  |
|Serveurs frontaux  |Composant serveur Web  |4443  |HTTPS  |Communications HTTPS (à partir d’un proxy inverse) et entre les pool frontaux HTTPS pour la connexion de découverte automatique.  |
|Serveurs frontaux  |Composant serveur Web  |8060  |TCP (MTLS)  ||
|Serveurs frontaux  |Composant serveur Web  |8061  |TCP (MTLS)  ||
|Serveurs frontaux  |Composant Mobility Services  |5086  |TCP (MTLS)  |Port SIP utilisé par les processus internes mobility services  |
|Serveurs frontaux  |Composant Mobility Services  |5087  |TCP (MTLS)  |Port SIP utilisé par les processus internes mobility services  |
|Serveurs frontaux  |Composant Mobility Services  |443  |HTTPS  ||
|Serveurs frontaux  |Skype Entreprise Server Assistant de conférence service (conférences téléphoniques)  |5064  |TCP  |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  |
|Serveurs frontaux  |Skype Entreprise Server Assistant de conférence service (conférences téléphoniques)  |5072  |TCP  |Utilisé pour les demandes SIP entrantes pour attendant (conférences téléphoniques).  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype Entreprise Server Service de médiation  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype Entreprise Server Service de médiation  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype Entreprise Server Service de médiation  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype Entreprise Server Service de médiation  |5081  |TCP  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.  |Skype Entreprise Server Service de médiation  |5082  |TCP (TLS)  |Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.  |
|Serveurs frontaux  |Skype Entreprise Server Service de partage d’application  |5065  |TCP  |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  |
|Serveurs frontaux  |Skype Entreprise Server Service de partage d’application  |49152-65535  |TCP  |Plage de ports multimédias utilisée pour le partage d’application.  |
|Serveurs frontaux  |Skype Entreprise Server Annonce de conférence service  |5073  |TCP  |Utilisé pour les demandes SIP entrantes pour le service Skype Entreprise Server Annonce de conférence (c’est-à-dire, pour les conférences entrantes).  |
|Serveurs frontaux  |Skype Entreprise Server Service de parcier d’appel  |5075  |TCP  |Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.  |
|Serveurs frontaux  |Skype Entreprise Server Service de test audio  |5076  |TCP  |Utilisé pour les demandes SIP entrantes du service de test audio.  |
|Serveurs frontaux  |Non applicable  |5066  |TCP  |Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.  |
|Serveurs frontaux  |Skype Entreprise Server Service Response Group  |5071  |TCP  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Skype Entreprise Server Service Response Group  |8404  |TCP (MTLS)  |Utilisé pour les demandes SIP entrantes de l’application Response Group.  |
|Serveurs frontaux  |Skype Entreprise Server Service de stratégie de bande passante  |5080  |TCP  |Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.  |
|Serveurs frontaux  |Skype Entreprise Server Accès au serveur de partage de fichiers  |445   |SMB/TCP  | Utilisé pour récupérer le carnet d’adresses, le contenu des réunions et d’autres éléments stockés sur le serveur de partage de fichiers.  |
|Serveurs frontaux  |Skype Entreprise Server Service de stratégie de bande passante  |448  |TCP  |Utilisé pour le contrôle d’admission des appels par Skype Entreprise Server service de stratégie de bande passante.  |
|Serveurs frontaux où réside le magasin central de gestion  | Skype Entreprise Server Service agent réplicateur maître |445  |TCP  |Permet de pousser les données de configuration du magasin central de gestion vers les serveurs exécutant Skype Entreprise Server.  |
|Tous les serveurs  |SQL Browser  |1434  |UDP  |SQL Navigateur pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale  |
|Tous les serveurs internes  |Divers  |49152-57500  |TCP/UDP  |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui arrêtent l’audio : les serveurs frontux (pour le service Skype Entreprise Server Assistant de conférence, le service Skype Entreprise Server Annonce de conférence et le service de conférence audio/vidéo Skype Entreprise Server) et le serveur de médiation.  |
|Office Serveurs Web Apps  ||443  ||Utilisé par Skype Entreprise Server pour se connecter à Office Web Apps Server.  |
|Directeurs  |Skype Entreprise Server Front-End service  |5060  |TCP  |Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.  |
|Directeurs  |Skype Entreprise Server Front-End service  |444  |HTTPS  <br/> TCP  |Communication entre serveurs frontaux et directeurs. En outre, le certificat client est publié (sur les serveurs frontux) ou validé s’il a déjà été publié.  |
|Directeurs  |Skype Entreprise Server Service de compatibilité web  |80  |TCP  |Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.  |
|Directeurs  |Skype Entreprise Server Service de compatibilité web  |443  |HTTPS  |Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).  |
|Directeurs  |Skype Entreprise Server Front-End service  |5061  |TCP  |Utilisé pour les communications internes entre serveurs et pour les connexions client.  |
|Serveurs de médiation  |Skype Entreprise Server Service de médiation  |5070  |TCP  |Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.  |
|Serveurs de médiation  |Skype Entreprise Server Service de médiation  |5067  |TCP (TLS)  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Skype Entreprise Server Service de médiation  |5068  |TCP  |Utilisé pour les demandes SIP entrantes de la passerelle PSTN.  |
|Serveurs de médiation  |Skype Entreprise Server Service de médiation  |5070  |TCP (MTLS)  |Utilisé pour les demandes SIP des serveurs frontaux.  |
|Serveur frontal de conversation permanente  |SiP de conversation permanente  |5041  |TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Persistent Chat Windows Communication Foundation (WCF)  |881  |TCP (TLS) et TCP (MTLS)  ||
|Serveur frontal de conversation permanente  |Service de transfert de fichiers de conversation permanente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX. Bien que Skype Entreprise Server n’utilise plus le port TCP 5060, lors du déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de groupe de serveurs de ligne RCC au port TCP que le serveur frontal ou le directeur utilisera pour se connecter au système PBX. Pour plus d’informations, voir l’cmdlet **CsTrustedApplicationComputer** dans la documentation Skype Entreprise Server Management Shell.
  
Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.
  
**Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé**

|Programme d’équilibrage de charge|Port|Protocole|
|:-----|:-----|:-----|
|Programme d’équilibrage de charge du serveur frontal  |5061  |TCP (TLS)  |
|Programme d’équilibrage de charge du serveur frontal  |444  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |135  |DCOM et appel de procédure distante (RPC)  |
|Programme d’équilibrage de charge du serveur frontal  |80  |HTTP  |
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP - Récupération du certificat racine du client et de l’appareil à partir du serveur frontal : clients et appareils authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |443  |HTTPS  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du serveur frontal  |5072  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5073  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5075  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5076  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5071  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |5080  |TCP  |
|Programme d’équilibrage de charge du serveur frontal  |448  |TCP  |
|Équilibreur de charge du serveur de médiation  |5070  |TCP  |
|Équilibreur de charge du serveur frontal (si le pool exécute également le serveur de médiation)  |5070  |TCP  |
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
|Programme d’équilibrage de charge du serveur frontal  |8080  |TCP - Récupération du certificat racine du client et de l’appareil à partir du serveur frontal : clients et appareils authentifiés par NTLM  |
|Programme d’équilibrage de charge du serveur frontal  |4443  |HTTPS (du proxy inverse)  |
|Programme d’équilibrage de charge du directeur  |443  |HTTPS  |
|Programme d’équilibrage de charge du directeur  |4443  |HTTPS (du proxy inverse)  |

**Ports client requis**

|Composant|Port|Protocole|Notes|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Utilisé par Skype Entreprise Server pour rechercher le nom de domaine complet du serveur d’inscriptions (c’est-à-dire, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).  |
|Clients  |443  |TCP (TLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |443  |TCP (PSOM/TLS)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)  |
|Clients  |5061  |TCP (MTLS)  |Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.  |
|Clients  |6891-6901  |TCP  |Utilisé pour le transfert de fichiers entre Skype Entreprise clients et clients précédents.  |
|Clients  |1024-65535 \*  |TCP/UDP  |Plage de ports audio (au moins 20 ports requis).  |
|Clients  |1024-65535 \*  |TCP/UDP  |Plage de ports vidéo (au moins 20 ports requis).  |
|Clients  |1024-65535 \*  |TCP  |Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.  |
|Clients  |1024-65535 \*  |TCP  |Partage d’application.  |
|Téléphone de partie commune Aastra 6721ip  <br/> Téléphone de bureau Aastra 6725ip  <br/> Téléphone IP HP 4110 (téléphone de partie commune)  <br/> Téléphone IP HP 4120 (téléphone de bureau)  <br/> Téléphone de partie commune IP Polycom CX500  <br/> Téléphone de bureau IP Polycom CX600  <br/> Téléphone de bureau IP CX700  <br/> Téléphone de conférence IP Polycom CX3000  |67/68  |DHCP  |Utilisé par les appareils répertoriés pour trouver le certificat Skype Entreprise Server, le FQDN d’approvisionnement et le FQDN du bureau d’enregistrement.  |
   
\* Pour configurer des ports spécifiques pour ces types de médias, utilisez l'; cmdlet CsConferencingConfiguration (paramètres ClientMediaPortRangeEnabled, ClientMediaPort et ClientMediaPortRange).
  
> [!NOTE]
> Les programmes d’installation Skype Entreprise clients créent automatiquement les exceptions de pare-feu du système d’exploitation requises sur l’ordinateur client. 

> [!NOTE]
> Les ports utilisés pour l’accès des utilisateurs externes sont requis pour tout scénario dans lequel le client doit traverser le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations). 
  
## <a name="ipsec-exceptions"></a>Exceptions IPsec

Pour les réseaux d’entreprise où la sécurité du protocole Internet (IPsec) (voir la RFC 4301-4309 de l’IETF) a été déployée, IPsec doit être désactivée sur la plage de ports utilisée pour la distribution de l’audio, de la vidéo et de la vidéo panoramique. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.
  
Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec. 
  
**Exceptions recommandées pour IPsec**

|Nom de la règle|Adresse IP source|Adresse IP de destination|Protocole|Port source|Port de destination|Besoin d’authentification|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Serveur Edge A/V, ports internes/entrants  |N’importe lequel  |Serveur Edge A/V - interne  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur Edge A/V, ports externes/entrants  |N’importe lequel  |Serveur Edge A/V - externe  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur Edge A/V, ports internes/sortants  |Serveur Edge A/V - interne  |N’importe lequel  |UDP &amp; TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur Edge A/V, ports externes/sortants  |Serveur Edge A/V - externe  |N’importe lequel  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur de médiation, ports entrants  |N’importe lequel  |Médiation  <br/> Serveur(s)  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur de médiation, ports sortants  |Médiation  <br/> Serveur(s)  |N’importe lequel  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Intendant Conférence entrant  |N’importe lequel  |Serveur frontal exécutant l’Intendant Conférence  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Intendant Conférence sortant  |Serveur frontal exécutant l’Intendant Conférence  |N’importe lequel  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur de conférence A/V, ports entrants  |N’importe lequel  |Serveurs frontaux  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Conférence A/V, ports sortants  |Serveurs frontaux  |N’importe lequel  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Exchange, ports entrants  |N’importe lequel  |Messagerie unifiée Exchange  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveurs de partage d’application, ports entrants  |N’importe lequel  |Serveurs de partage d’application  |TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Serveur de partage d’application, ports sortants  |Serveurs de partage d’application  |N’importe lequel  |TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Exchange, ports sortants  |Messagerie unifiée Exchange  |N’importe lequel  |UDP et TCP  |N’importe lequel  |N’importe lequel  |Ne pas s’authentifier  |
|Clients  |N’importe lequel  |N’importe lequel  |UDP  |Plage de ports multimédias définie  |N’importe lequel  |Ne pas s’authentifier  |