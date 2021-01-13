---
title: Configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Résumé : Consultez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server.'
ms.openlocfilehash: 59ad84cd0f4445709b236baecafeeab240e6ea65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814014"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server

**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype Entreprise Server.

Cette section décrit la configuration matérielle et logicielle requise pour les conférences web, les conférences audio et vidéo (A/V), les conférences d’appels et les conférences par messagerie instantanée. Toutes les fonctionnalités de conférence s’exécutent sur les serveurs frontux ; il existe des exigences supplémentaires pour différents types de conférences, comme illustré dans le diagramme suivant.

Par exemple, si vous souhaitez autoriser les conférences téléphoniques, vous devez déployer un serveur de médiation et une passerelle pour la connexion au réseau téléphonique commuté (PSTN). Si vous souhaitez autoriser la conférence web, vous devez vous assurer que Skype Entreprise Server peut se connecter à un serveur Office Web Apps Server. Si vous souhaitez autoriser les utilisateurs externes à participer à des conférences, vous devez déployer un serveur Edge.

**Fonctionnalités et exigences de conférence**

![Composants de conférence](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Pour plus d’informations sur les considérations de topologie, voir [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Configuration matérielle et logicielle requise pour les serveurs frontux

Étant donné que les conférences web, les conférences A/V, les conférences téléphoniques et les conférences par messagerie instantanée sont toutes cingliquées avec le serveur frontal, la configuration matérielle et logicielle requise pour le serveur est la même que pour les serveurs frontux. Pour plus d’informations sur ces exigences, voir [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and Environmental requirements for Skype for Business Server [2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Conditions requises pour les conférences web

Si vous avez choisi d’activer la conférence web, vous devez planifier les choses suivantes :

- Accès au magasin de fichiers, utilisé pour stocker le contenu de conférence web.

- Intégration à Office Web Apps Server, qui est nécessaire pour partager des fichiers PowerPoint au cours d’une conférence.

### <a name="file-store"></a>magasin de fichiers

Le service de conférence web Skype Entreprise Server stocke le contenu partagé pendant les réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, [voir Créer un partage de fichiers dans Skype Entreprise Server.](../../deploy/install/create-a-file-share.md) Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Skype Entreprise Server prend en charge l’utilisation de partages de fichiers sur un stockage DAS (Direct Attached Storage) ou un réseau san (storage area network), y compris DFS (Distributed File System), et sur un tableau redondant de disques indépendants (RAID) pour les magasins de fichiers. Une fois que l’Assistant Déploiement de Skype Entreprise Server a défini l’emplacement du partage de fichiers, Skype Entreprise Server crée une structure de dossiers dans le partage de fichiers semblable à :

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Le service de conférence web stocke ensuite du contenu tel que des diapositives PowerPoint, des tableaux blancs, des sondages et des pièces jointes dans les dossiers CollabContent et CollabMetadata, situés dans le dossier WebServices.

### <a name="office-web-apps-server"></a>Office Web Apps Server

Pour utiliser les fonctionnalités de conférence web, vous devez installer Office Web Apps Server et configurer Skype Entreprise Server pour communiquer avec Office Web Apps Server.

Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Skype Entreprise Server, SQL Server ou toute autre application serveur. (Aucune version d’Office ne doit être installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également avoir un ensemble spécifique de logiciels installés (y compris .NET Framework 4.5 et Windows PowerShell 3.0). Ces exigences, ainsi que les informations sur la configuration des certificats et des services Internet (IIS), sont détaillées dans le site web [Microsoft Office Web Apps Deployment](https://go.microsoft.com/fwlink/p/?linkid=257525).

Pour plus d’informations sur la configuration de Skype Entreprise Server pour qu’il fonctionne avec Office Web Apps Server, voir Configurer l’intégration avec [Office Web Apps Server dans Skype Entreprise Server.](../../deploy/deploy-conferencing/office-web-app-server.md)

## <a name="requirements-for-audio-and-video-conferencing"></a>Conditions requises pour les conférences audio et vidéo

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de média de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur.

Pour plus d’informations sur la planification de la capacité audio et vidéo pour les conférences, voir [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Ceci est important pour les réseaux restreints, tels que les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, voir [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio tels que des casques pour y prendre part. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo tels que des webcams pour les utilisateurs. Pour les périphériques audio et vidéo, le déploiement d’appareils et la formation des utilisateurs sont des étapes importantes à prendre en compte. Pour plus d’informations, voir [Planifier les clients et les appareils.](../../plan-your-deployment/clients-and-devices/clients-and-devices.md) Microsoft recommande d’utiliser des périphériques de communications unifiées (UC) certifiés par Microsoft pour tous les types d’appareils, afin de garantir une expérience utilisateur optimale. Pour plus d’informations sur les appareils certifiés par UC, voir [Téléphones et appareils pour Skype Entreprise.](https://go.microsoft.com/fwlink/?LinkId=619916)

## <a name="requirements-for-dial-in-conferencing"></a>Conditions requises pour les conférences téléphoniques

La conférence rendez-vous est une fonctionnalité facultative de la charge de travail de conférence Skype Entreprise Server qui inclut de nombreux composants. Certains composants sont spécifiques à la conférence téléphonique et d’autres Voix Entreprise composants. Cette section décrit les conditions requises pour les composants nécessaires pour les conférences téléphoniques. Pour plus d’informations sur les conditions requises pour le serveur de médiation et la passerelle PSTN, voir Composant serveur de médiation dans Skype Entreprise [Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) et Déploiement d’un serveur de médiation dans le Générateur de topologies dans Skype [Entreprise Server.](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)

### <a name="required-components"></a>Composants requis

Vous devez installer les composants Skype Entreprise Server suivants avant de pouvoir configurer la conférence téléphonique :

- service d’application de communications unifiées (UCAS), désigné par Service d’application

- application Intendant Conférence

- application d’annonce de conférence

- page web Paramètres de conférence rendez-vous

- Au moins un serveur de médiation et au moins une passerelle PSTN

Pour les conférences téléphoniques, le service d’application, l’application d’attendant de conférence et l’application Annonce de conférence ont la même exigence de système d’exploitation que les serveurs frontux. Pour plus d’informations, [voir Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

L’application Attendant de conférence et l’application Annonce de conférence nécessitent que le runtime du format Windows Media soit installé sur les serveurs frontaux. Windows Media Format Runtime est nécessaire pour lire les fichiers audio Windows Media (WMA) utilisés pour l’attente musicale, les noms enregistrés et les invites. Si vous installez sur Windows Server 2012 ou Windows Server 2012 R2 (ce que nous vous recommandons), vous devez installer Microsoft Media Foundation pour obtenir le runtime du format Windows Media. Si vous installez sur une version de Windows Server antérieure à Windows 2012, vous devez vous assurer que l’Expérience utilisateur Windows est installée pour obtenir le runtime du format Windows Media.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Conditions requises pour les fichiers audio pour les conférences téléphoniques

Skype Entreprise Server ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences téléphoniques. Toutefois, si vous avez un besoin métier fort qui nécessite de modifier les fichiers audio par défaut, consultez l’article 961177 de la Base de connaissances Microsoft sur la personnalisation des [invites vocales](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)ou des fichiers de musique pour l’audioconférence rendez-vous.

Vous pouvez également utiliser l’utilitaire de gestion des invites vocales personnalisées de l’Attendant de conférence [Microsoft Lync Server,](https://go.microsoft.com/fwlink/p/?LinkId=396880) qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant rejoint une réunion Skype Entreprise par des invites personnalisées pour fournir une expérience d’entrée de réunion différente. Les invites vocales personnalisées peuvent être installées sur un serveur Enterprise ou Standard Edition.

L’application Attendant de conférence et l’application Annonce de conférence ont les conditions suivantes pour les fichiers d’attente musicale, de nom enregistré et d’invite audio :

- Format de fichier audio Windows Media (.wma)

- Mono 16 bits

- CBR (vitesse de transmission constante) 2 passes 48 Kbits/s

- Niveau de voix à -24 Db

### <a name="user-requirements-for-dial-in-conferencing"></a>Conditions requises par les utilisateurs pour les conférences téléphoniques

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Les utilisateurs d’entreprise (c’est-à-dire les utilisateurs qui ont des informations d’identification des services de domaine Active Directory et des comptes Skype Entreprise Server au sein de votre organisation) entrent leur numéro de téléphone (ou poste) et un code confidentiel pour se rendre aux conférences en tant qu’utilisateur authentifié.

## <a name="port-requirements-for-conferencing"></a>Ports requis pour les conférences

Pour utiliser les fonctionnalités de conférence, Skype Entreprise Server requiert l’ouverture de certains ports. Le tableau suivant répertorie les ports requis pour les conférences. Pour plus d’informations sur toutes les conditions requises pour les ports, voir [Port et protocole requis pour les serveurs.](../../plan-your-deployment/network-requirements/ports-and-protocols.md)

**Ports serveur requis**


|**Rôle serveur**|**Nom du service**|**Port**|**Protocole**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|Serveurs frontaux  <br/> |Service de conférence de messagerie instantanée Skype Entreprise Server  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|Serveurs frontaux  <br/> |Service de conférence web Skype Entreprise Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|Serveurs frontaux  <br/> |Service de compatibilité de conférence web Skype Entreprise Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour écouter les connexions PSOM (Persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Skype Entreprise Server.  <br/> |
|Serveurs frontaux  <br/> |Service de conférence audio/vidéo Skype Entreprise Server  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|Serveurs frontaux  <br/> |Service de conférence audio/vidéo Skype Entreprise Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|Serveurs frontaux  <br/> |Service Skype Entreprise Server Conferencing Attendant (conférences téléphoniques)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|Serveurs frontaux  <br/> |Service Skype Entreprise Server Conferencing Attendant (conférences téléphoniques)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour attendant (conférences téléphoniques).  <br/> |
|Serveurs frontaux  <br/> |Service de partage d’application Skype Entreprise Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Service de partage d’application Skype Entreprise Server  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Service d’annonce de conférence Skype Entreprise Server  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le service d’annonce de conférence Skype Entreprise Server (c’est-à-dire, pour les conférences entrantes).  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui arrêtent l’audio : les serveurs frontux (pour le service Skype Entreprise Server Conferencing Attendant, le service d’annonce de conférence Skype Entreprise Server et le service de conférence audio/vidéo Skype Entreprise Server) et le serveur de médiation.  <br/> |
|Serveurs Office Web Apps  <br/> ||443  <br/> ||Utilisé par Skype Entreprise Server pour se connecter à Office Web Apps Server.  <br/> |

**Ports clients requis**


|**Port**|**Protocole**|**Notes**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Partage d’application.  <br/> |


