---
title: Configuration matérielle et logicielle requise pour les conférences dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype entreprise Server.'
ms.openlocfilehash: 0d09e0e85e7059e0a761b2822f963765751623e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815982"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Configuration matérielle et logicielle requise pour les conférences dans Skype entreprise Server

**Résumé :** Consultez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour les conférences dans Skype entreprise Server.

Cette section décrit la configuration matérielle et logicielle requise pour les conférences Web, les conférences audio et vidéo (A/V), les conférences rendez-vous et la messagerie instantanée. Toutes les fonctionnalités de conférence s’exécutent sur des serveurs front-end ; Il existe d’autres exigences pour les différents types de conférences, comme indiqué dans le schéma suivant.

Par exemple, si vous voulez autoriser les conférences rendez-vous, vous devez déployer un serveur de médiation et une passerelle pour la connexion au réseau téléphonique public commuté (RTC). Si vous voulez autoriser les conférences Web, vous devez vous assurer que Skype entreprise Server peut se connecter à un serveur Office Web Apps. Si vous voulez autoriser les utilisateurs externes à participer à des conférences, vous devez déployer un serveur Edge.

**Fonctions et conditions requises pour les conférences**

![Composants de conférence](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Pour plus d’informations sur les aspects topologiques, reportez-vous à [la rubrique planification de votre topologie de conférences pour Skype entreprise Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Configuration matérielle et logicielle requise pour les serveurs frontaux

Étant donné que les conférences Web, les conférences A/V, les conférences rendez-vous et les conférences par messagerie instantanée sont tout colocalisées avec le serveur frontal, les exigences en matière de matériel et de logiciels sont les mêmes que celles des serveurs frontaux. Pour plus d’informations sur la configuration requise, voir [Configuration requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et configuration environnementale requise pour Skype entreprise [Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Configuration requise dans le cadre de la conférence web

Si vous avez choisi d’activer les conférences web, vous devez planifier les points suivants :

- Accès au magasin de fichiers permettant de stocker le contenu des conférences web

- Intégration au serveur Office Web Apps Server nécessaire au partage de fichiers PowerPoint lors d’une conférence

### <a name="file-store"></a>Magasin de fichiers

Le service de conférence Web Skype entreprise Server stocke le contenu partagé pendant les réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition Server ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, reportez-vous à [la rubrique Création d’un partage de fichiers dans Skype entreprise Server](../../deploy/install/create-a-file-share.md). Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Skype entreprise Server prend en charge l’utilisation des partages de fichiers sur le stockage en attachement direct (DAS) ou sur un réseau de stockage (SAN), y compris le système de fichiers DFS et sur une baie redondante de disques indépendants (RAID) pour les magasins de fichiers. Lorsque l’Assistant Déploiement de Skype entreprise Server a défini l’emplacement du partage de fichiers, Skype entreprise Server crée une structure de dossiers dans le partage de fichier de la même façon que :

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Le service de conférence web stocke ensuite le contenu (diapositives PowerPoint, tableaux blancs, sondages et pièces jointes) dans les dossiers CollabContent et CollabMetadata qui se trouvent dans le dossier WebServices.

### <a name="office-web-apps-server"></a>Office Web Apps Server

Pour pouvoir utiliser les fonctionnalités de conférence Web, vous devez installer Office Web Apps Server et configurer Skype entreprise Server pour communiquer avec Office Web Apps Server.

Office Web Apps Server doit être installé sur un ordinateur autonome qui n’utilise pas Skype entreprise Server, SQL Server ou une autre application serveur. (Vous ne devez pas avoir installé une version d’Office sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également disposer d’un ensemble spécifique de logiciels installés (y compris .NET Framework 4,5 et Windows PowerShell 3,0). Ces conditions, ainsi que des informations sur la configuration des certificats et d’Internet Information Services (IIS), sont décrites en détail dans le [site Web de déploiement de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Pour plus d’informations sur la configuration de Skype entreprise Server pour utiliser Office Web Apps Server, voir [configurer l’intégration à Office Web Apps Server dans Skype entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Configuration requise pour la conférence audio et vidéo

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de trafic multimédia de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur.

Pour plus d’informations sur la planification des capacités audio et vidéo pour les conférences, reportez-vous à la rubrique [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Cela est important pour les réseaux restreints, comme les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, reportez-vous à la section [planifier le contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio, comme des casques pour y participer. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo, comme des webcams pour les utilisateurs. Pour les périphériques audio et vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes à prendre en considération. Pour plus d’informations, reportez-vous à la section [planifier pour les clients et les appareils](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft vous recommande d’utiliser des appareils de communications unifiées (UC) certifiés par Microsoft pour garantir une expérience utilisateur optimale. Pour plus d’informations sur les appareils validés par UC, voir [téléphones et périphériques pour Skype entreprise](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Configuration requise pour la conférence rendez-vous

La fonction de conférence rendez-vous est une fonctionnalité facultative de la charge de travail de conférence Skype entreprise Server incluant divers composants. Certains composants sont spécifiques aux conférences rendez-vous, et certains sont des composants voix entreprise. Cette section décrit les exigences relatives aux composants nécessaires à la Conférence rendez-vous. Pour plus d’informations sur la configuration requise pour les passerelles de réseau téléphonique commuté (PSTN) et de réseau téléphonique commuté (RTC), voir [composant serveur de médiation dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) et [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Composants requis

Pour pouvoir configurer les conférences rendez-vous, vous devez installer les composants Skype entreprise Server suivants :

- service d’application de communications unifiées (UCAS), désigné par Service d’application

- application Intendant Conférence

- Application d’annonce de conférence

- Page web Paramètres de conférence rendez-vous

- Au moins un serveur de médiation et une passerelle RTC

Pour les conférences rendez-vous, le service d’application, les applications de surveillance des conférences et les annonces de conférences présentent les mêmes exigences relatives au système d’exploitation que les serveurs frontaux. Pour plus d’informations, reportez-vous à la rubrique [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

L’application assistance de conférence et d’annonce de conférences nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux. Le module d’exécution du format Windows Media est requis pour lire les fichiers audio Windows Media (WMA) concernant l’attente musicale, les noms enregistrés et les invites. Si vous procédez à l’installation sur Windows Server 2012 ou Windows Server 2012 R2 (recommandé), vous devez installer Microsoft Media Foundation pour obtenir le runtime du format Windows Media. Si vous effectuez une installation sur une version de Windows Server antérieure à Windows 2012, vous devez vous assurer que l’Expérience Bureau Windows est installée de façon à obtenir le module d’exécution du format Windows Media.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Exigences concernant les fichiers audio pour la conférence rendez-vous

Skype entreprise Server ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences rendez-vous. Toutefois, si vous avez un besoin professionnel qui nécessite que vous deviez modifier les fichiers audio par défaut, voir l’article 961177 de la base de connaissances Microsoft, [Comment personnaliser les invites vocales ou les fichiers audio pour les conférences](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)rendez-vous.

Vous pouvez également utiliser l’utilitaire de gestion des [invites de voix personnalisées du surveillant des conférences Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant de téléphone rejoint une réunion Skype entreprise avec des invites personnalisées afin de fournir une nouvelle interface de réunion. Les invites vocales personnalisées peuvent être installées sur un serveur Entreprise ou Standard.

L’application du service de conférence et l’application d’annonce présentent les exigences suivantes concernant la musique en attente, le nom enregistré et les fichiers d’invite audio :

- Format de fichier audio Windows Media (.wma)

- Mono 16 bits

- Vitesse de transmission constante (CBR) 2 passes 48 Kbits/s

- Niveau de voix à -24 Db

### <a name="user-requirements-for-dial-in-conferencing"></a>Exigences imposées aux utilisateurs de la conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Utilisateurs d’entreprise (c’est-à-dire, les utilisateurs disposant d’informations d’identification de services de domaine Active Directory et de comptes Skype entreprise Server au sein de votre organisation) entre leur numéro de téléphone (ou leur extension) et un code confidentiel (PIN) pour se connecter aux conférences comme un utilisateur authentifié.

## <a name="port-requirements-for-conferencing"></a>Configuration de ports requise pour les conférences

Pour pouvoir utiliser les fonctionnalités de conférence, Skype entreprise Server nécessite l’ouverture de certains ports. Le tableau ci-dessous répertorie la configuration requise pour les conférences. Pour plus d’informations sur la configuration requise pour les ports, voir la [Configuration requise pour les ports et les protocoles pour les serveurs](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Ports serveur requis**


|**Rôle serveur**|**Nom du service**|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|serveurs frontaux  <br/> |Service de conférence par messagerie instantanée Skype entreprise Server  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|serveurs frontaux  <br/> |Service de conférence Web Skype entreprise Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|serveurs frontaux  <br/> |Service de compatibilité de conférences Web Skype entreprise Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour écouter les connexions PSOM (persistent Shared Object mode) du client Live Meeting et des versions précédentes de Skype entreprise Server.  <br/> |
|serveurs frontaux  <br/> |Service de conférence audio/vidéo Skype entreprise Server  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|serveurs frontaux  <br/> |Service de conférence audio/vidéo Skype entreprise Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|serveurs frontaux  <br/> |Service de surveillance des conférences Skype entreprise Server (conférences rendez-vous)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|serveurs frontaux  <br/> |Service de surveillance des conférences Skype entreprise Server (conférences rendez-vous)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le service d’assistance téléphonique (Conférence rendez-vous).  <br/> |
|serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Service d’annonce de conférences Skype entreprise Server  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le service d’annonce de conférence Skype entreprise Server (c’est-à-dire pour la Conférence rendez-vous).  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisé par tous les serveurs qui terminent le son : serveurs front-end (pour le service de surveillance des conférences Skype entreprise Server, service d’annonce de conférence Skype entreprise Server et service de visioconférence Skype entreprise Server) et serveur de médiation.  <br/> |
|Serveurs Office Web Apps Server  <br/> ||443  <br/> ||Utilisé par Skype entreprise Server pour la connexion à Office Web Apps Server.  <br/> |

**Ports clients requis**


|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Partage d’application.  <br/> |


