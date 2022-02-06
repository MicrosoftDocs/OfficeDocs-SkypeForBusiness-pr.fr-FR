---
title: Configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server.'
---

# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server

**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server.

Cette section décrit la configuration matérielle et logicielle requise pour les conférences web, les conférences audio et vidéo (A/V), les conférences téléphoniques et les conférences par messagerie instantanée. Toutes les fonctionnalités de conférence s’exécutent sur les serveurs frontux ; il existe des exigences supplémentaires pour différents types de conférences, comme illustré dans le diagramme suivant.

Par exemple, si vous souhaitez autoriser les conférences téléphoniques, vous devez déployer un serveur de médiation et une passerelle pour la connexion au réseau téléphonique commuté (PSTN). Si vous souhaitez autoriser la conférence web, vous devez vous assurer que les Skype Entreprise Server peuvent se connecter à Office Web Apps Server. Si vous souhaitez autoriser les utilisateurs externes à participer à des conférences, vous devez déployer un serveur Edge.

**Fonctionnalités et exigences de conférence**

![Composants de conférence.](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Pour plus d’informations sur les considérations sur la topologie, voir [Plan your conferencing topology for Skype Entreprise Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Configuration matérielle et logicielle requise pour les serveurs frontux

Étant donné que la conférence web, la conférence A/V, la conférence d’accès et la conférence par messagerie instantanée sont toutes cingliquées avec le serveur frontal, la configuration matérielle et logicielle requise pour le serveur est la même que pour les serveurs frontux. Pour plus d’informations sur ces exigences, voir Server [requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Environmental requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Conditions requises pour les conférences web

Si vous avez choisi d’activer la conférence web, vous devez planifier les choses suivantes :

- Accès au magasin de fichiers, utilisé pour stocker le contenu de conférence web.

- Intégration à Office Web Apps Server, qui est nécessaire pour partager des fichiers PowerPoint au cours d’une conférence.

### <a name="file-store"></a>magasin de fichiers

Le Skype Entreprise Server de conférence web stocke le contenu partagé pendant les réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Édition Standard ou Êdition Entreprise pool frontal. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, [voir Créer un partage de fichiers dans Skype Entreprise Server](../../deploy/install/create-a-file-share.md). Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Skype Entreprise Server prend en charge l’utilisation de partages de fichiers sur un stockage DAS (Direct Attached Storage) ou un réseau san (storage area network), y compris DFS (Distributed File System), et sur un tableau redondant de disques indépendants (RAID) pour les magasins de fichiers. Une fois que Skype Entreprise Server’Assistant Déploiement a défini l’emplacement du partage de fichiers, Skype Entreprise Server crée une structure de dossiers dans le partage de fichiers similaire à :

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Le service de conférence web stocke ensuite du contenu tel que des diapositives PowerPoint, des tableaux blancs, des sondages et des pièces jointes dans les dossiers CollabContent et CollabMetadata, situés dans le dossier WebServices.

### <a name="office-web-apps-server"></a>Office Web Apps Server

Pour utiliser les fonctionnalités de conférence web, vous devez installer Office Web Apps Server et configurer Skype Entreprise Server pour communiquer avec Office Web Apps Server.

Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Skype Entreprise Server, SQL Server ou toute autre application serveur. (Vous ne devez avoir aucune version de Office installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également avoir un ensemble spécifique de logiciels installés (y compris .NET Framework 4.5 et Windows PowerShell 3.0). Ces exigences, ainsi que les informations sur la configuration des certificats et des Internet Information Services (IIS), sont détaillées dans le site web [Microsoft Office Web Apps Deployment](/webappsserver/deploy-the-infrastructure-office-web-apps-server).

Pour plus d’informations sur la configuration de Skype Entreprise Server pour qu’il fonctionne avec Office Web Apps Server, voir Configurer l’intégration avec [Office Web Apps Server dans Skype Entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Conditions requises pour les conférences audio et vidéo

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de média de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur.

Pour plus d’informations sur la planification de la capacité audio et vidéo pour les conférences, voir [Plan network requirements for Skype Entreprise](../../plan-your-deployment/network-requirements/network-requirements.md).

Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Ceci est important pour les réseaux restreints, tels que les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, voir [Plan for call admission control in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio tels que des casques pour y prendre part. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo tels que des webcams pour les utilisateurs. Pour les périphériques audio et vidéo, le déploiement d’appareils et la formation des utilisateurs sont des étapes importantes à prendre en compte. Pour plus d’informations, [voir Planifier les clients et les appareils](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft recommande d’utiliser des périphériques de communications unifiées (UC) certifiés par Microsoft pour tous les types d’appareils, afin de garantir une expérience utilisateur optimale. Pour plus d’informations sur les appareils certifiés par UC, voir [Téléphones et appareils pour Skype Entreprise](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

## <a name="requirements-for-dial-in-conferencing"></a>Conditions requises pour les conférences téléphoniques

La conférence rendez-vous est une fonctionnalité facultative de la charge de travail Skype Entreprise Server conférence qui inclut une variété de composants. Certains composants sont spécifiques à la conférence téléphonique et d’autres sont Voix Entreprise composants. Cette section décrit les conditions requises pour les composants nécessaires pour les conférences téléphoniques. Pour plus d’informations sur les exigences en matière de serveur de médiation et de passerelle de réseau téléphonique commuté (PSTN), voir Composant du serveur de médiation dans [Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) et Déployer un serveur de médiation dans le Générateur de [topologies dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Composants requis

Vous devez installer les composants de Skype Entreprise Server suivants avant de pouvoir configurer la conférence téléphonique :

- service d’application de communications unifiées (UCAS), désigné par Service d’application

- application Intendant Conférence

- application d’annonce de conférence

- page web Paramètres de conférence rendez-vous

- Au moins un serveur de médiation et au moins une passerelle PSTN

Pour les conférences téléphoniques, le service d’application, application Assistant de conférence et application Annonce de conférence ont les mêmes exigences de système d’exploitation que les serveurs frontux. Pour plus d’informations, [voir Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

application Assistant de conférence et application Annonce de conférence que le Windows format multimédia soit installé sur les serveurs frontaux. Windows’utilisation du format multimédia runtime est nécessaire pour lire les fichiers Windows Multimédia audio (WMA) utilisés pour l’attente musicale, les noms enregistrés et les invites. Si vous installez sur Windows Server 2012 ou Windows Server 2012 R2 (ce que nous vous recommandons), vous devez installer Microsoft Media Foundation pour obtenir Windows format multimédia runtime. Si vous installez sur une version de Windows Server antérieure à Windows 2012, vous devez vous assurer que l’expérience expérience utilisateur Windows est installée pour obtenir le runtime du format Windows Média.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Conditions requises pour les fichiers audio pour les conférences téléphoniques

Skype Entreprise Server ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences téléphoniques. Toutefois, si vous avez un besoin métier fort qui nécessite de modifier les fichiers audio par défaut, consultez l’article de la Base de connaissances Microsoft 961177, Comment personnaliser les invites vocales ou les fichiers de musique pour les conférences [audio rendez-vous](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

application Assistant de conférence et application Annonce de conférence les conditions suivantes pour les fichiers d’attente musicale, de nom enregistré et d’invite audio :

- Format de fichier audio Windows Media (.wma)

- Mono 16 bits

- CBR (vitesse de transmission constante) 2 passes 48 Kbits/s

- Niveau de voix à -24 Db

### <a name="user-requirements-for-dial-in-conferencing"></a>Conditions requises par les utilisateurs pour les conférences téléphoniques

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Enterprise utilisateurs (c’est-à-dire, les utilisateurs qui ont des informations d’identification des services de domaine Active Directory et des comptes Skype Entreprise Server au sein de votre organisation) entrent leur numéro de téléphone (ou poste) et un code confidentiel pour se rendre aux conférences en tant qu’utilisateur authentifié.

## <a name="port-requirements-for-conferencing"></a>Ports requis pour les conférences

Pour utiliser les fonctionnalités de conférence, Skype Entreprise Server certains ports doivent être ouverts. Le tableau suivant répertorie les ports requis pour les conférences. Pour plus d’informations sur tous les ports requis, voir [Port et protocole requis pour les serveurs](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Ports de serveur requis**


|**Rôle serveur**|**Nom du service**|**Port**|**Protocol (Protocole)**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|Serveurs frontaux  <br/> |Skype Entreprise Server service de conférence de messagerie instantanée  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de conférence web  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de compatibilité de conférence web  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour écouter les connexions PSOM (Persistent Shared Object Model) à partir du client Live Meeting et des versions antérieures de Skype Entreprise Server.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de conférence audio/vidéo  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de conférence audio/vidéo  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server Assistant de conférence service (conférences téléphoniques)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server Assistant de conférence service (conférences téléphoniques)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour attendant (conférences téléphoniques).  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de partage d’application  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de partage d’application  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server Annonce de conférence service  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le service Skype Entreprise Server Annonce de conférence (c’est-à-dire, pour les conférences entrantes).  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui arrêtent l’audio : serveurs frontux (pour le service Skype Entreprise Server Assistant de conférence, Skype Entreprise Server Annonce de conférence service et Skype Entreprise Server service de conférence audio/vidéo) et serveur de médiation.  <br/> |
|Office Web Apps Servers  <br/> ||443  <br/> ||Utilisé par Skype Entreprise Server pour se connecter à Office Web Apps Server.  <br/> |

**Ports clients requis**


|**Port**|**Protocol (Protocole)**|**Notes**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Partage d’application.  <br/> |