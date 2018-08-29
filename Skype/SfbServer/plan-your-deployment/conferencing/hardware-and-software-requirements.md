---
title: Configuration matérielle et logicielle requise pour la conférence dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour la conférence dans Skype pour Business Server.'
ms.openlocfilehash: 0029bca57477d52e1886ff476984477bdac75b97
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23247668"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Configuration matérielle et logicielle requise pour la conférence dans Skype pour Business Server

**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour la conférence dans Skype pour Business Server.

Cette section décrit la configuration matérielle et logicielle requise pour les conférences web, audio et vidéo (A / V) les conférences, conférence rendez-vous et conférence de messagerie instantanée (IM). Toutes les fonctionnalités de conférence s’exécutée sur des serveurs frontaux ; Il existe des exigences supplémentaires pour les différents types de conférence, comme illustré dans le diagramme suivant.

Par exemple, si vous souhaitez autoriser dans les conférences rendez-vous, vous devez déployer un serveur de médiation et une passerelle pour se connecter au réseau téléphonique commuté (RTC). Si vous souhaitez autoriser les conférences web, vous devez vous assurer que Skype pour Business Server peut se connecter à un serveur Office Web Apps Server. Si vous voulez autoriser les utilisateurs externes à participer à des conférences, vous devez déployer un serveur Edge.

**Fonctions et conditions requises pour les conférences**

![Composants de conférence](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Pour plus d’informations sur les considérations relatives à la topologie, voir [planifier votre topologie de conférence pour Skype pour Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Configuration matérielle et logicielle requise pour les serveurs frontaux

Étant donné que conférence web, A / V conférences, conférence rendez-vous et conférence par messagerie instantanée sont tous colocalisés avec le serveur frontal, les exigences de configuration matérielle et logicielle du serveur sont les mêmes que pour les serveurs frontaux. Pour plus d’informations sur ces conditions, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et [exigences de Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Configuration requise dans le cadre de la conférence web

Si vous avez choisi d’activer les conférences web, vous devez planifier les points suivants :

- Accès au magasin de fichiers permettant de stocker le contenu des conférences web

- Intégration au serveur Office Web Apps Server nécessaire au partage de fichiers PowerPoint lors d’une conférence

### <a name="file-store"></a>Magasin de fichiers

Le Skype pour le service de conférence web Business Server stocke le contenu partagé au cours des réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition server ou pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, voir [créer un partage de fichiers dans Skype pour Business Server](../../deploy/install/create-a-file-share.md). Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Skype pour Business Server prend en charge les partages de fichiers sur stockage en attachement direct (DAS) ou sur un réseau de stockage (SAN), y compris les fichiers système distribués (DFS) et sur une baie de disques indépendants (RAID) pour les magasins de fichiers redondante. Une fois le Skype pour l’Assistant de déploiement Business Server a défini l’emplacement du partage de fichier, Skype pour Business Server crée une structure de dossiers dans le partage de fichiers similaire à :

- 1-ApplicationServer-1

- CentralMgmt-1-1

- WebServices-1-1

  - CollabContent

  - Collabmetadata qui

  - DataConf

Le service de conférence web stocke ensuite le contenu (diapositives PowerPoint, tableaux blancs, sondages et pièces jointes) dans les dossiers CollabContent et CollabMetadata qui se trouvent dans le dossier WebServices.

### <a name="office-web-apps-server"></a>Office Web Apps Server

Pour pouvoir utiliser les fonctionnalités de conférence web, vous devez installer Office Web Apps Server et configurer Skype pour Business Server communiquer avec Office Web Apps Server.

Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Skype pour Business Server, SQL Server ou toute autre application serveur. (Vous devez pas n’importe quelle version d’Office installée sur cet ordinateur.) N’importe quel ordinateur utilisé pour exécuter Office Web Apps Server doit être un ensemble spécifique de logiciels (y compris le .NET Framework 4.5 et Windows PowerShell 3.0). Ces exigences, ainsi que des informations sur la configuration des certificats et les Services Internet (IIS), sont abordés en détail dans le [site Web de déploiement de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Pour plus d’informations sur la configuration Skype pour Business Server fonctionner avec Office Web Apps Server, voir [configurer l’intégration avec Office Web Apps Server dans Skype pour Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Configuration requise pour la conférence audio et vidéo

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de trafic multimédia de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur.

Pour plus d’informations sur la planification des conférences de la capacité audio et vidéo, voir [planifier la configuration réseau requise pour Skype pour les entreprises](../../plan-your-deployment/network-requirements/network-requirements.md).

Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Cela est important pour les réseaux restreints, comme les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, voir [planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio, comme des casques pour y participer. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo, comme des webcams pour les utilisateurs. Pour les périphériques audio et vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes à prendre en considération. Pour plus d’informations, voir [planifier les clients et périphériques](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft vous recommande d’utiliser des appareils de communications unifiées (UC) certifiés par Microsoft pour garantir une expérience utilisateur optimale. Pour plus d’informations sur les périphériques certifié UC, voir [téléphones et appareils pour Skype pour les entreprises](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Configuration requise pour la conférence rendez-vous

Conférence rendez-vous est une fonctionnalité facultative de la Skype pour la charge de travail Business Server conférence qui inclut de nombreux composants. Certains composants sont spécifiques à la conférence rendez-vous et d’autres composants d’Enterprise Voice. Cette section décrit la configuration requise pour les composants qui sont nécessaires pour les conférences rendez-vous. Pour plus d’informations sur le serveur de médiation et les exigences en matière de passerelle de réseau (PSTN) public commuté, voir [composant serveur de médiation dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) et [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Composants requis

Vous devez installer le Skype suivante pour les composants Business Server avant de pouvoir configurer conférence rendez-vous :

- service d’application de communications unifiées (UCAS), désigné par Service d’application

- application Intendant Conférence

- Application d’annonce de conférence

- Page web Paramètres de conférence rendez-vous

- Au moins un serveur de médiation et une passerelle RTC

Pour la conférence rendez-vous, service d’Application, application intendant Conférence et application d’annonce de conférence ont la même configuration requise de système d’exploitation que les serveurs frontaux. Pour plus d’informations, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Application intendant Conférence et application d’annonce de conférence nécessitent que le module d’exécution du Format Windows Media est installé sur les serveurs frontaux. Le module d’exécution du format Windows Media est requis pour lire les fichiers audio Windows Media (WMA) concernant l’attente musicale, les noms enregistrés et les invites. Si vous installez sur Windows Server 2012 ou Windows Server 2012 R2 (auquel il est recommandé), vous devez installer Microsoft Media Foundation pour obtenir le module d’exécution du Format Windows Media. Si vous effectuez une installation sur une version de Windows Server antérieure à Windows 2012, vous devez vous assurer que l’Expérience Bureau Windows est installée de façon à obtenir le module d’exécution du format Windows Media.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Exigences concernant les fichiers audio pour la conférence rendez-vous

Skype pour Business Server ne gère pas la personnalisation des invites vocales et de musique pour les conférences rendez-vous. Toutefois, si vous avez besoin de forte activité nécessitant vous permet de modifier les fichiers audio par défaut, voir l’article 961177, [comment personnaliser les invites vocales ou fichiers de musique pour les services d’audioconférence rendez-vous](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)de la Base de connaissances Microsoft.

Vous pouvez également utiliser l’utilitaire de gestion de [Microsoft Lync Server Attendant personnalisé voix invites de la téléconférence](https://go.microsoft.com/fwlink/p/?LinkId=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisés lorsqu’un appelant téléphone joint une Skype pour la réunion d’entreprise avec les messages personnalisés l’expérience d’entrée pour fournir une réunion différents. Les invites vocales personnalisées peuvent être installées sur un serveur Entreprise ou Standard.

Application intendant Conférence et application d’annonce de conférence ont les besoins suivants pour une musique d’attente, le nom enregistré et fichiers d’invite audio :

- Format de fichier audio Windows Media (.wma)

- Mono 16 bits

- Vitesse de transmission constante (CBR) 2 passes 48 Kbits/s

- Niveau de voix à -24 Db

### <a name="user-requirements-for-dial-in-conferencing"></a>Exigences imposées aux utilisateurs de la conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Utilisateurs de l’entreprise (autrement dit, les utilisateurs qui disposent d’informations d’identification des Services de domaine Active Directory et Skype pour les comptes Business Server au sein de votre organisation) entrent leur numéro de téléphone (ou extension) et un code confidentiel (PIN) pour vous connecter à des conférences en tant que un utilisateur authentifié.

## <a name="port-requirements-for-conferencing"></a>Configuration de ports requise pour les conférences

Pour pouvoir utiliser les fonctionnalités de conférence, Skype pour Business Server requiert que certains ports sont ouverts. Le tableau ci-dessous répertorie la configuration requise pour les conférences. Pour plus d’informations sur tous les ports requis, consultez [ports et protocoles requis pour les serveurs](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Ports de serveur requis**


|**Rôle serveur**|**Nom du service**|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|serveurs frontaux  <br/> |Skype pour le service de conférence par messagerie instantanée Business Server  <br/> |5062  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de conférence Web Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de compatibilité de conférence Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilisé pour l’écoute des connexions de l’objet modèle PSOM (Persistent Shared) à partir du client Live Meeting et les versions antérieures de Skype pour Business Server.  <br/> |
|serveurs frontaux  <br/> |Skype pour le service de conférence Audio/vidéo Business Server  <br/> |5063  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de conférence Audio/vidéo Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences vidéo.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server intendant (conférence rendez-vous)  <br/> |5064  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service Business Server intendant (conférence rendez-vous)  <br/> |5072  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour Attendant (conférences rendez-vous).  <br/> |
|serveurs frontaux  <br/> |Skype pour le service de partage d’Application Business Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service de partage d’Application Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour le service d’annonce de conférence Business Server  <br/> |5073  <br/> |TCP  <br/> |Utilisé pour les demandes SIP entrantes pour le Skype pour le service d’annonce de conférence Business Server (autrement dit, pour les conférences rendez-vous).  <br/> |
|Tous les serveurs internes  <br/> |Divers  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes. Utilisée par tous les serveurs qui se termine audio : serveurs frontaux (pour Skype pour le service Business Server intendant, Skype pour le service d’annonce de conférence Business Server et Skype pour le service de conférence Audio/vidéo Business Server), et Serveur de médiation.  <br/> |
|Serveurs Office Web Apps Server  <br/> ||443  <br/> ||Utilisé par Skype pour Business Server pour se connecter à Office Web Apps Server.  <br/> |

**Ports client requis**


|**Port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).  <br/> |
|1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports audio (au moins 20 ports requis).  <br/> |
|1024-65535.\*  <br/> |TCP/UDP  <br/> |Plage de ports vidéo (au moins 20 ports requis).  <br/> |
|1024-65535.\*  <br/> |TCP  <br/> |Partage d’application.  <br/> |


