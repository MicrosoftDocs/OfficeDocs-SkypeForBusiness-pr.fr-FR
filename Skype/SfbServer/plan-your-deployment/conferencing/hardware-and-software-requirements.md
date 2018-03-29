---
title: Configuration logicielle et matérielle requise pour les conférences dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les exigences matérielles et logicielles pour la conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: dcabd3b0216eebfa3873b44b0d19d32522d6564f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour les conférences dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les exigences matérielles et logicielles pour la conférence dans Skype pour Business Server 2015.
  
Cette section décrit les exigences matérielles et logicielles pour les conférences web, audio et vidéo (A / V) conférence dans l’accès à la conférence, conférence et la messagerie instantanée (MI). Toutes les fonctions de conférence de s’exécutées sur des serveurs frontaux ; Il existe des exigences supplémentaires pour les différents types de conférence, comme illustré dans le diagramme suivant.
  
Par exemple, si vous souhaitez autoriser dans l’accès à la conférence, vous devrez déployer un serveur de médiation et la passerelle pour la connexion à un réseau téléphonique public commuté (RTPC). Si vous souhaitez autoriser des conférences sur le web, vous devrez vous assurer que Skype pour Business Server peut se connecter à un serveur d’applications Web Office. Si vous voulez autoriser les utilisateurs externes à participer à des conférences, vous devez déployer un serveur Edge. 
  
**Exigences et capacités de conférence**

![Composants de conférence](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)
  
 Pour plus d’informations sur les considérations relatives à la topologie, voir [planifier votre topologie de conférence pour Skype pour Business Server 2015](conferencing-topology.md).
  
## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Configuration matérielle et logicielle requise pour les serveurs frontaux

Car les conférences web, A / V conférence, conférences à distance et les conférences par messagerie instantanée sont tous colocalisés avec le serveur frontal, la configuration matérielle et logicielle de serveur est les mêmes que pour les serveurs frontaux. Pour plus d’informations sur la configuration requise, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et des [besoins environnementaux dans Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="requirements-for-web-conferencing"></a>Configuration requise dans le cadre de la conférence web

Si vous avez choisi d’activer les conférences web, vous devez planifier les points suivants :
  
- Accès au magasin de fichiers permettant de stocker le contenu des conférences web
    
- Intégration au serveur Office Web Apps Server nécessaire au partage de fichiers PowerPoint lors d’une conférence
    
### <a name="file-store"></a>Magasin de fichiers

Le Skype pour le service de conférence web Business Server stocke du contenu partagé au cours de réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou un pool d’entreprise Edition Front-End. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, voir [créer un partage de fichiers dans Skype pour Business Server 2015](../../deploy/install/create-a-file-share.md). Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.
  
Skype pour Business Server prend en charge les partages de fichiers sur un stockage en attachement direct (DAS) ou un réseau de zone de stockage (SAN), y compris de fichiers système (DFS) et un ensemble redondant de disques indépendants (RAID) pour les magasins de fichiers. Une fois le Skype pour l’Assistant de déploiement de serveur Business a défini l’emplacement du partage de fichier, Skype pour Business Server crée une structure de dossier dans le partage de fichiers similaire à : 
  
- 1-ApplicationServer-1
    
- 1-CentralMgmt-1
    
- 1-WebServices-1
    
  - CollabContent
    
  - CollabMetadata
    
  - DataConf
    
Le service de conférence web stocke ensuite le contenu (diapositives PowerPoint, tableaux blancs, sondages et pièces jointes) dans les dossiers CollabContent et CollabMetadata qui se trouvent dans le dossier WebServices.
  
### <a name="office-web-apps-server"></a>Office Web Apps Server

Pour utiliser les fonctionnalités de conférence web, vous devez installer les Office Web Apps Server et configurer Skype pour communiquer avec le serveur d’applications Web Office Business Server. 
  
Office Web Apps Server doit être installé sur un ordinateur qui n’exécute pas Skype pour Business Server, de SQL Server ou toute autre application serveur autonome. (Pas avoir n’importe quelle version d’Office installée sur cet ordinateur.) N’importe quel ordinateur utilisé pour exécuter Office Web Apps Server doit également avoir un ensemble spécifique de logiciel installé (y compris.NET Framework 4.5 et Windows PowerShell 3.0). Ces exigences, ainsi que des informations sur la configuration des certificats et Internet Information Services (IIS), sont décrits en détail dans le [site Web de déploiement de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Pour plus d’informations sur la façon de configurer Skype pour Business Server fonctionne avec Office Web Apps serveur, voir [configurer une intégration avec Office Web Apps Server dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md).
  
## <a name="requirements-for-audio-and-video-conferencing"></a>Configuration requise pour la conférence audio et vidéo

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de trafic multimédia de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur. 
  
Pour plus d’informations sur la planification des conférences des capacités audio et vidéo, reportez-vous à la section [planifier la configuration réseau requise pour Skype pour entreprise 2015](../../plan-your-deployment/network-requirements/network-requirements.md).
  
Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Cela est important pour les réseaux restreints, comme les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, consultez le [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio, comme des casques pour y participer. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo, comme des webcams pour les utilisateurs. Pour les périphériques audio et vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes à prendre en considération. Pour plus d’informations, consultez [planification pour les clients et les périphériques](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft vous recommande d’utiliser des appareils de communications unifiées (UC) certifiés par Microsoft pour garantir une expérience utilisateur optimale. Pour plus d’informations sur les périphériques certifiés de communications unifiées, voir [téléphones et périphériques pour Skype pour les entreprises](https://go.microsoft.com/fwlink/?LinkId=619916).
  
## <a name="requirements-for-dial-in-conferencing"></a>Configuration requise pour la conférence rendez-vous

Conférences à distance est une fonctionnalité optionnelle de la Skype pour Business Server conférence la charge de travail qui inclut un certain nombre de composants. Certains composants sont spécifiques aux conférences en accès à distance et d’autres composants de Voix Entreprise. Cette section décrit la configuration requise pour les composants qui sont nécessaires pour les conférences à distance. Pour plus d’informations sur serveur de médiation et les exigences de passerelle de réseau téléphonique public commuté, reportez-vous à la section [composant de serveur de médiation dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) et [de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).
  
### <a name="required-components"></a>Composants requis

Vous devez installer le Skype suivante pour les composants serveur de l’entreprise avant de pouvoir configurer les conférences à distance : 
  
- service d’application de communications unifiées (UCAS), désigné par Service d’application
    
- application Intendant Conférence
    
- Application d’annonce de conférence
    
- Page web Paramètres de conférence rendez-vous
    
- Au moins un serveur de médiation et une passerelle RTC
    
Pour les conférences à distance, le service d’Application, application de la surveillance du conférence et application d’annonce de conférence aient les mêmes besoins de système d’exploitation comme serveurs frontaux. Pour plus d’informations, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Application de surveillance du conférence et application d’annonce de conférence exigent l’installation de Windows Media Format Runtime sur les serveurs frontaux. Le module d’exécution du format Windows Media est requis pour lire les fichiers audio Windows Media (WMA) concernant l’attente musicale, les noms enregistrés et les invites. Si vous installez sur Windows Server 2012 ou de Windows Server 2012 R2 (ce qui est recommandé), vous devrez installer Microsoft Media Foundation pour obtenir Windows Media Format Runtime. Si vous effectuez une installation sur une version de Windows Server antérieure à Windows 2012, vous devez vous assurer que l’Expérience Bureau Windows est installée de façon à obtenir le module d’exécution du format Windows Media.
  
### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Exigences concernant les fichiers audio pour la conférence rendez-vous

Skype pour Business Server ne gère pas la personnalisation des invites vocales et de musique pour les conférences à distance. Toutefois, si vous avez un besoin fort qui vous oblige à modifier les fichiers audio par défaut, consultez l’article 961177, [Comment faire pour personnaliser les invites vocales ou les fichiers de musique pour la conférence audio à distance](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)de la Base de connaissances Microsoft.
  
Vous pouvez également utiliser l’utilitaire de gestion de [Microsoft Lync Server surveillance personnalisée voix invites de la téléconférence](https://go.microsoft.com/fwlink/p/?LinkId=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisés lorsqu’un appelant téléphone rejoint un Skype pour une réunion d’affaires avec les messages personnalisés pour fournir une autre réunion entrée rencontrer. Les invites vocales personnalisées peuvent être installées sur un serveur Entreprise ou Standard.
  
Application de surveillance du conférence et application d’annonce de conférence ont les besoins suivants pour la musique de blocage, le nom enregistré et fichiers d’invite audio :
  
- Format de fichier audio Windows Media (.wma)
    
- Mono 16 bits
    
- Vitesse de transmission constante (CBR) 2 passes 48 Kbits/s
    
- Niveau de voix à -24 Db
    
### <a name="user-requirements-for-dial-in-conferencing"></a>Exigences imposées aux utilisateurs de la conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Utilisateurs de l’entreprise (c'est-à-dire, les utilisateurs disposant des informations d’identification des Services de domaine Active Directory et Skype pour les comptes de serveur d’entreprise au sein de votre organisation) entrent leur numéro de téléphone (ou extension) et un numéro d’identification personnel (PIN) pour vous connecter à des conférences en tant que un utilisateur authentifié.
  
## <a name="port-requirements-for-conferencing"></a>Configuration de ports requise pour les conférences

Pour utiliser les fonctionnalités de conférence, Skype pour Business Server requiert que certains ports sont ouverts. Le tableau ci-dessous répertorie la configuration requise pour les conférences. Pour plus d’informations sur tous les ports requis, consultez [conditions de Port et de protocole pour les serveurs](../../plan-your-deployment/network-requirements/ports-and-protocols.md).
  
**Ports de serveur requis**


|**Rôle de serveur**|**Nom du service**|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|serveurs frontaux  <br/> |Skype pour le service Business Server IM conférence  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server Web conférence  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service compatibilité avec le Business Server Web Conferencing  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour écouter les connexions de permanent partagée objet modèle (PSOM) à partir du client Live Meeting et les versions précédentes de Skype pour Business Server.  <br/> |
|serveurs frontaux  <br/> |Skype pour le service Business Server Audio/vidéo conférence  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server Audio/vidéo conférence  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de surveillance de Conferencing Server Business (accès à distance de la conférence)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de surveillance de Conferencing Server Business (accès à distance de la conférence)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les requêtes SIP entrantes de surveillance (conférence de numérotation).  <br/> |
|serveurs frontaux  <br/> |Skype pour service de partage de l’Application serveur de Business  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour service de partage de l’Application serveur de Business  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour service d’annonce de conférence Business Server  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les requêtes SIP entrantes pour le Skype pour service d’annonce de conférence Business Server (autrement dit, pour les conférences à distance).  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui se termine audio : serveurs frontaux (pour Skype pour le service de surveillance de Conferencing Server Business, Skype pour service d’annonce de conférence Business Server et Skype pour le service Business Server Audio/vidéo conférence), et Serveur de médiation.  <br/> |
|Serveurs Office Web Apps Server  <br/> ||443  <br/> ||Utilisé par Skype pour Business Server 2015 pour se connecter à un serveur d’applications Web Office.  <br/> |
   
**Ports du client requis**


|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  <br/> |
|1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|1024-65535.\*  <br/> |TCP  <br/> |Partage d’application.  <br/> |
   

