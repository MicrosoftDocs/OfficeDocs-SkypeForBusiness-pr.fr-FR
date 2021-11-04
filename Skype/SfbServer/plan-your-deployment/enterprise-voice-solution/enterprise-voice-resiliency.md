---
title: Planifier la résilience Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Découvrez comment prendre en charge la résistance vocale dans Skype Entreprise Server Voix Entreprise, à la fois sur les sites centraux et les sites de succursale. Les options de site de succursale incluent le déploiement des Survivable Branch Appliances ou des serveurs Survivable Branch Servers.
ms.openlocfilehash: ec0d542318023fdc638926e78ff6ffdeceefba5f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778004"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planifier la résilience Voix Entreprise dans Skype Entreprise Server

Découvrez comment prendre en charge la résistance vocale dans Skype Entreprise Server Voix Entreprise, à la fois sur les sites centraux et les sites de succursale. Les options de site de succursale incluent le déploiement des Survivable Branch Appliances ou des serveurs Survivable Branch Servers.

La résilience vocale fait référence à la capacité des utilisateurs à continuer à passer et recevoir des appels si un site central qui héberge Skype Entreprise Server devient indisponible, qu’il s’agit d’une défaillance de réseau large (WAN) ou d’une autre cause. Si un site central tombe en panne, Voix Entreprise doit basculer vers un site de sauvegarde pour assurer la continuité du service. En cas de panne du réseau étendu, les appels de la succursale doivent être redirigés vers une passerelle PSTN locale. Cette section traite de la planification pour la résistance des communications vocales en cas de panne du site central ou du réseau étendu.

## <a name="central-site-resiliency"></a>Résilience de site central

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. La maintenance des services d’urgence, l’accès au service d’aide et la possibilité d’effectuer des tâches critiques lorsqu’un site central est hors service sont essentiels pour toute solution Voix Entreprise de résilience. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

- Le basculement vocal doit être fourni.

- Les utilisateurs qui s’inscrivent habituellement auprès du pool frontal sur le site central doivent pouvoir s’inscrire auprès d’un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’eux résolu en pool directeur ou pool frontal dans chacun de vos sites centraux. Vous pouvez ajuster la priorité et les pondérations des enregistrements SRV afin que les utilisateurs qui sont servis par ce site central obtiennent le directeur et le pool frontal correspondants en avance sur ceux des autres enregistrements SRV.

- Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

### <a name="architecture-and-topology"></a>Architecture et topologie

La planification de la résistance vocale sur un site central nécessite une compréhension de base du rôle central joué par le Skype Entreprise Server registrar pour activer le changement de voix. Le Skype Entreprise Server serveur d’inscriptions est un service qui permet l’inscription et l’authentification des clients et fournit des services de routage. Il s’exécute sur Édition Standard serveur, serveur frontal, directeur ou Survivable Branch Appliance. Un pool de bureaux d’inscriptions se compose des services de bureau d’inscriptions qui s’exécutent sur le pool frontal et résident sur le même site. Un client Skype Entreprise découvre le pool frontal via le mécanisme de découverte suivant :

1. Enregistrement DNS SRV

2. Service Web de découverte automatique

3. Option DHCP 120

Une fois que Skype Entreprise client se connecte au pool frontal, il est dirigé par l’équilibreur de charge vers l’un des serveurs frontaux du pool. Ce serveur frontal, à son tour, redirige le client vers un serveur d’inscriptions préféré dans le pool.

Chaque utilisateur activé pour Voix Entreprise est affecté à un pool de bureaux d’inscriptions particulier, qui devient le pool de bureaux d’inscriptions principal de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs inscrits auprès d’un Survivable Branch Appliance.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide des paramètres de résilience du Générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1. Un client découvre les Skype Entreprise Server via les enregistrements DNS SRV. Dans Skype Entreprise Server, les enregistrements DNS SRV peuvent être configurés pour renvoyer plusieurs FQDN à la requête DNS SRV. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool directeur dans l’un des emplacements est disponible, le client peut se connecter au premier saut Skype Entreprise Server.

    > [!NOTE]
    > L’utilisation d’un pool directeur est facultative. Un pool frontal peut être utilisé à la place.

2. Le pool directeur informe le client Skype Entreprise du pool de bureaux d’inscriptions principal et du pool de sauvegarde de l’utilisateur.

3. Le Skype Entreprise tente d’abord de se connecter au pool de bureaux d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool de bureaux d’inscriptions principal n’est pas disponible, le client Skype Entreprise tente de se connecter au pool de services d’inscriptions de sauvegarde. Si le pool de bureaux d’inscriptions de sauvegarde est disponible et a déterminé que le pool de bureaux d’inscriptions principal de l’utilisateur est indisponible (en détectant un manque de pulsations pour un intervalle de retentation spécifié), le pool de sauvegarde accepte l’inscription de l’utilisateur. Une fois que le bureau d’enregistrement de sauvegarde a détecté que le bureau d’inscriptions principal est de nouveau disponible, le pool de sauvegarde redirige les clients deover vers leur pool principal.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

- Les sites où résident les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

- Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

- Chaque pool de bureaux d’inscriptions doit être à charge équilibrée à l’aide de l’équilibrage de charge DNS, de l’équilibrage de la charge matérielle ou des deux. Pour plus d’informations sur la planification de votre configuration d’équilibrage de charge, voir La configuration requise pour [l’équilibrage de charge Skype Entreprise](../../plan-your-deployment/network-requirements/load-balancing.md).

- Chaque utilisateur doit être affecté à un pool de bureaux d’inscriptions principal à l’aide de l’Skype Entreprise Server Management Shell **set-CsUser** ou du Panneau de Skype Entreprise Server.

- Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

- Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde au bout de 300 secondes. Vous pouvez modifier cet intervalle à l’aide du générateur Skype Entreprise Server topologie.

- Configurez un itinéraire deover. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

- Si le site central contenait votre serveur de gestion principal et que le site est susceptible de se trouver en panne pendant une période prolongée, vous devrez réinstaller vos outils de gestion sur le site de sauvegarde . Dans le cas contraire, vous ne pourrez pas modifier les paramètres de gestion.

### <a name="dependencies"></a>Dépendances

Skype Entreprise Server l’infrastructure et les composants logiciels suivants assurent la résilience vocale :

|**Composant** <br/> |**Fonctionnel** <br/> |
|:-----|:-----|
|DNS  <br/> |Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client  <br/> |
|Exchange et services Web Exchange (EWS)  <br/> |Stockage des contacts ; données de calendrier  <br/> |
|Messagerie unifiée Exchange et services Web Exchange  <br/> |Journaux des appels, liste des messages vocaux, messagerie vocale  <br/> |
|Options DHCP 120  <br/> |Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour que cela fonctionne, un serveur DHCP doit être configuré ou Skype Entreprise Server DHCP doit être activé.  <br/> |

### <a name="survivable-voice-features"></a>Fonctionnalités vocales de secours

Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :

- Appels PSTN sortants

- Appels PSTN entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde

- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

- Messagerie instantanée entre deux utilisateurs, et partage audio et vidéo entre des utilisateurs situés sur le même site

- Services de transfert d’appel, de sonnerie simultanée des systèmes d’extrémité, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel, ou tous les membres de l’équipe, sont configurés sur le même site.

- Les téléphones et clients existants continuent à fonctionner.

- Enregistrement des détails des appels (CDR)

- Authentification et autorisation

En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :

- Dépôt et récupération de messages vocaux

    Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :

  - Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.

  - Configurez le plan de numérotation de messagerie un Exchange de chaque utilisateur pour qu’il inclue des serveurs de messagerie un Exchange à la fois sur le site central et sur le site de sauvegarde, mais désignez les serveurs de messagerie un Exchange de sauvegarde comme désactivés. Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs de messagerie un Exchange sur le site de sauvegarde comme activés.

    Si aucune des solutions précédentes n’est possible, la Exchange de l’un des deux ne sera pas disponible en cas d’indisponibilité du site central.

- Conférence de tous types

    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, d’autres utilisateurs ne peuvent pas participer à des conférences hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

- standard automatique de conférence

- Routage basé sur la présence et DND

- Mise à jour des paramètres de transfert d’appel

- Service Response Group et parcage d’appel

- Provisionnement des nouveaux téléphones et clients

- Recherche web du carnet d’adresses

## <a name="branch-site-resiliency"></a>Résilience de site de succursale

Si vous souhaitez fournir une résilience de site de succursale, c’est-à-dire, un service Voix Entreprise haute disponibilité, vous avez trois options pour ce faire :

- Survivable Branch Appliance

- serveur Survivable Branch Server

- Un déploiement Skype Entreprise Server complet sur le site de succursale

Ce guide vous aidera à choisir la solution de résistance la plus adaptée à votre organisation et, en fonction de votre choix, la solution de connectivité PSTN à utiliser. Il vous aidera également à préparer le déploiement de la solution choisie en décrivant les conditions préalables et les autres éléments à prendre en compte pour la planification.

### <a name="branch-site-resiliency-features"></a>Fonctionnalités de résilience de site de succursale

Si vous fournissez une résilience de site de succursale, si la connexion WAN d’un site de succursale à un site central échoue ou si le site central est inaccessible, les fonctionnalités vocales suivantes doivent continuer à être disponibles :

- Appels PSTN entrants et sortants

- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

- Messagerie instantanée entre deux utilisateurs

- Le transport d’appel, la sonnerie simultanée des points de terminaison, la délégation d’appel et les services d’appel d’équipe, mais uniquement si le délégant et le délégué (par exemple, un responsable et l’administrateur du responsable), ou tous les membres de l’équipe, sont configurés sur le même site.

- Enregistrements des détails des appels (CDR)

- Conférence rendez-vous par réseau téléphonique commuté (PSTN) avec standard automatique de conférence

- Fonctionnalités de messagerie vocale, si vous configurez les paramètres de réroutage de la messagerie vocale.

- Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes seront disponibles uniquement si votre solution de résilience est un déploiement Skype Entreprise Server à grande échelle sur le site de succursale :

- messagerie instantanée, conférence A/V et web

- routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

- Mise à jour des paramètres de transfert d’appel

- Application Response Group et application de parcage d’appel

- Mise en service de nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents sur le site de succursale.

- Enhanced 9-1-1 (E9-1-1)

    Si E9-1-1 est déployé et que la liaison SIP sur le site central n’est pas disponible car la liaison wan est en panne, le Survivable Branch Appliance route les appels E9-1-1 vers la passerelle de succursale locale. Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent router les appels vers la passerelle locale en cas de panne du réseau wan.

> [!NOTE]
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Les utilisateurs homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.

### <a name="branch-site-resiliency-solutions"></a>Solutions de résilience de site de succursale

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. Plus précisément, si vous perdez la connexion au site central, les utilisateurs du site de succursale continueront à avoir un service Voix Entreprise et la messagerie vocale (si vous configurez les paramètres de réroutage de la messagerie vocale). Cependant, pour les sites comportant moins de 25 utilisateurs une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau suivant peut vous aider à déterminer l’option appropriée.

|**Si vous...**|**Nous vous recommandons d’utiliser un…**|
|:-----|:-----|
|Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’un support d’administration local  <br/> |Survivable Branch Appliance  <br/> Le Survivable Branch Appliance est un serveur lame standard avec un serveur d’inscriptions Skype Entreprise Server et un serveur de médiation s’exécutant sur Windows Server 2008 R2. Le Survivable Branch Appliance contient également une passerelle PSTN (réseau téléphonique commuté). Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA)) assurent une connexion PSTN continue en cas de panne du WAN, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.  <br/> Pour plus d’informations sur les Survivable Branch Appliances, voir « Détails du Survivable Branch Appliance » plus loin dans cette rubrique.  <br/> **Remarque :** Si vous décidez d’utiliser également une trunk SIP avec votre Survivable Branch Appliance, contactez votre fournisseur survivable Branch Appliance pour savoir quel fournisseur de services est le mieux choisi pour votre organisation. <br/> |
|Hébergez entre 1 000 et 2 000 utilisateurs sur votre site de succursale, ne disposez pas d’une connexion WAN résiliente et disposez d’administrateurs Skype Entreprise Server qualifiés.  <br/> |Survivable Branch Server ou deux Survivable Branch Appliances.  <br/> Le serveur Survivable Branch Server est un serveur Windows qui présente la configuration matérielle requise spécifiée et sur Skype Entreprise Server serveur d’inscriptions et de médiation. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.  <br/> Pour plus d’informations sur les serveurs Survivable Branch Server, voir « Survivable Branch Server Details », plus loin dans cette rubrique.  <br/> |
|Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour 5 000 utilisateurs au plus et que des administrateurs Skype Entreprise Server sont disponibles  <br/> |Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.  <br/> Un déploiement d’Skype Entreprise Server à grande échelle fournit une connexion PSTN continue, ainsi qu’une présence et une conférence résilientes en cas de panne du réseau wan.  <br/> |

#### <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résistance de la branche vocale.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

Le Skype Entreprise Server Survivable Branch Appliance inclut les composants suivants :

- un serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs, et le routage des appels ;

- un serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;

- une passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du WAN ;

- SQL Server Express pour le stockage local des données d’utilisateur.

Le Survivable Branch Appliance inclut également des branches PSTN, des ports analogiques et un adaptateur Ethernet.

Si la connexion wan du site de succursale à un site central devient indisponible, les utilisateurs de succursale internes continuent d’être inscrits auprès du survivable Branch Appliance Registrar et d’obtenir un service vocal ininterrompu à l’aide de la connexion Survivable Branch Appliance au réseau PSTN. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison WAN vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion WAN redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Ni le passage au Survivable Branch Appliance, ni la restauration du service ne nécessitent la présence d’un administrateur informatique.

Skype Entreprise Server prend en charge jusqu’à deux Survivable Branch Appliance sur un site de succursale.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Le Survivable Branch Appliance est fabriqué par les fabricants d’équipement d’origine en partenariat avec Microsoft et déployé en leur nom par des détaillants à valeur ajoutée. Ce déploiement ne doit avoir lieu qu’une fois Skype Entreprise Server déployé sur le site central, une connexion WAN au site de succursale est en place et les utilisateurs du site de succursale sont activés pour Voix Entreprise.

Pour plus d’informations sur les phases ci-dessous, voir [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) dans la documentation de déploiement.

|**Étape**|**Étapes**|**Droits d’utilisateur**|
|:-----|:-----|:-----|
|Configurer les services de domaine Active Directory pour le Survivable Branch Appliance  <br/> |**Sur le site central :** <br/>  Créez un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activera le Survivable Branch Appliance sur le site de succursale. <br/>  Créez un compte d’ordinateur (avec le nom de domaine complet applicable) pour le Survivable Branch Appliance dans les services de domaine Active Directory. <br/>  Dans le Générateur de topologie, créez et publiez le Survivable Branch Appliance. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. Le Survivable Branch Appliance doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le Générateur de topologies.  <br/> |
|Installez et activez le Survivable Branch Appliance.  <br/> |**Sur le site de succursale :** <br/>  Connecter le Survivable Branch Appliance vers un port Ethernet et un port PSTN. <br/>  Démarrez le Survivable Branch Appliance. <br/>  Associez le Survivable Branch Appliance au domaine à l’aide du compte d’utilisateur de domaine créé pour le Survivable Branch Appliance sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur. <br/>  Configurez le Survivable Branch Appliance à l’aide de l’interface utilisateur OEM. <br/>  Testez la connectivité PSTN. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Serveur Survivable Branch Server en détail

Dans le Générateur de topologie, créez le site de succursale, ajoutez le serveur Survivable Branch Server à ce site, puis exécutez l’Assistant Déploiement de Skype Entreprise Server sur l’ordinateur sur lequel vous souhaitez installer le rôle.

### <a name="branch-site-resiliency-requirements"></a>Exigences de résilience de site de succursale

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résistance des sites de succursale en faisant de leur pool de serveurs d’inscriptions le Survivable Branch Appliance (SBA) ou le Serveur Survivable Branch Server.

#### <a name="registrar-assignments-for-branch-users"></a>Assignations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale que vous choisissez, vous devez affecter un bureau d’enregistrement principal à chaque utilisateur. Les utilisateurs de site de succursale doivent toujours s’inscrire auprès du serveur d’inscriptions sur le site de succursale, que ce serveur réside dans le Survivable Branch Appliance, le Serveur Survivable Branch Server ou le serveur Skype Entreprise Server Standard ou Êdition Entreprise autonome. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si le Survivable Branch Appliance devient indisponible, c’est ainsi que les clients de site de succursale découvriront automatiquement le bureau d’enregistrement de sauvegarde.

Si un site de succursale ne contient pas de serveur DNS, il existe deux façons de configurer la découverte du Survivable Branch Appliance ou du Serveur Survivable Branch Server :

- Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale pour qu’il pointe vers le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server.

- Configurez le Survivable Branch Appliance ou le Serveur Survivable Branch Server pour répondre aux requêtes DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte pour les utilisateurs d’un site de succursale. Cette stratégie doit inclure un itinéraire principal qui utilise le Survivable Branch Appliance ou la passerelle de serveur de succursale, et un ou plusieurs itinéraires de sauvegarde qui utilisent une liaison avec une passerelle PSTN (réseau téléphonique commuté) sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire de sauvegarde qui utilise une ou plusieurs passerelles de site central est utilisé à la place. Ainsi, quel que soit l’emplacement où un utilisateur est inscrit (sur le bureau d’enregistrement de sites de succursale ou le pool de sauvegarde du site central), la stratégie VoIP de l’utilisateur est toujours en vigueur. Il s’agit d’une considération importante pour les scénarios de failover. Par exemple, si vous devez renommer le Survivable Branch Appliance ou reconfigurer le Survivable Branch Appliance pour vous connecter à un pool de bureaux d’inscriptions de sauvegarde sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central pendant toute la durée. (Pour plus d’informations sur le changement de nom ou la reconfiguration d’un Survivable Branch Appliance, voir l’Annexe B : Gestion d’un [Survivable Branch Appliance](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) dans la documentation de déploiement.) Si ces utilisateurs n’ont pas de stratégies VoIP au niveau de l’utilisateur ou de plans de numérotation au niveau de l’utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site du site central s’appliquent aux utilisateurs par défaut, au lieu des stratégies voIP et des plans de numérotation au niveau du site de succursale. Dans ce scénario, à moins que les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site utilisés par le pool de bureaux d’inscriptions de sauvegarde ne s’appliquent également aux utilisateurs du site de succursale, leurs appels échouent. Par exemple, si les utilisateurs d’un site de succursale situé au Japon sont déplacés vers un site central à Redmond, il est peu probable qu’un plan de numérotation avec des règles de normalisation qui préviennent +1425 à tous les appels à 7 chiffres traduise correctement les appels pour ces utilisateurs.

> [!IMPORTANT]
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique PSTN à la stratégie utilisateur de succursale et d’assigner des itinéraires séparés à chacun d’entre eux. Le premier itinéraire, ou principal, dirigerait les appels vers la passerelle associée au Survivable Branch Appliance (SBA) ou au serveur de succursale ; le deuxième itinéraire, ou itinéraire de sauvegarde, dirigerait les appels vers la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires assignés au premier enregistrement d’utilisation PSTN avant d’essayer le deuxième enregistrement.

Pour vous assurer que les appels entrants aux utilisateurs du site de succursale seront acheminés vers ces utilisateurs lorsque la passerelle de succursale ou le composant Windows du site Survivable Branch Appliance n’est pas disponible (ce qui se produira par exemple, si le Survivable Branch Appliance ou la passerelle de succursale était en panne pour maintenance), créez un itinéraire de transfert sur la passerelle (ou travaillez avec votre fournisseur SDN) pour rediriger les appels entrants vers le pool de sauvegarde du pool de bureaux d’inscriptions du centre. site. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire traduit les numéros conformément aux formats de numéro de téléphone acceptés de la passerelle PSTN ou d’un autre homologue de la liaison. Pour plus d’informations sur la création d’un itinéraire de basculement, voir [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux Survivable Branch Appliances sur un site de succursale, vous pouvez créer un plan de numérotation au niveau du site pour les deux, sauf si un plan de niveau de service distinct pour chacun d’eux est nécessaire.

> [!NOTE]
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs inscrits auprès d’un Survivable Branch Appliance.

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, voir [Create or modify a dial plan in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and Create the [VoIP Routing Policy for Branch Users in](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) the Deployment documentation.

#### <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lors de la préparation des plans de numérotation et des stratégies de voix pour les utilisateurs de sites de succursale, n’oubliez pas d’inclure des règles de normalisation et des règles de traduction qui correspondent aux chaînes et au format de numéro utilisés dans l’attribut de ligne msRTCSIP (ou URI de ligne), afin que les appels Skype Entreprise activés entre les utilisateurs de site de succursale et les utilisateurs du site central soient acheminés correctement, en particulier lorsque les appels doivent être réacheminés sur le réseau téléphonique principal car la liaison wan n’est pas disponible. D’autres éléments particuliers sont à prendre en considération dans le cas des numéros composés qui incluent des numéros de poste et non simplement des numéros de téléphone.

Les règles de normalisation et de traduction qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec uniquement un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Toutefois, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour traduire le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :

|**Nom de la règle**|**Description**|**Modèle de numéro**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Ne traduit pas les numéros à 5 chiffres  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 n’est pas traduit  <br/> |

Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. Lors d’une panne du réseau wan, si un utilisateur de site de succursale appelle un utilisateur du site central uniquement en composant le numéro de poste de l’utilisateur du site central, vous devez avoir une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez avoir une règle de traduction sortante qui ajoute le numéro de téléphone complet de votre organisation à la place. Par exemple :

|**Description**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Traduit les numéros à 5 chiffres en numéro de téléphone et poste d’un utilisateur  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 devient +14255550123;ext=10001  <br/> |
|Traduit les numéros à 5 chiffres vers le numéro de téléphone de votre organisation et le poste d’un utilisateur  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 devient +14255550100;ext=10001  <br/> |

Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de traduction sortante doit également supprimer le numéro de poste. Par exemple :

|**Description**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Supprime le poste des numéros de téléphone présentant un numéro de poste  <br/> |^\+(\d \* ); ext=(\d \* )$  <br/> |+$1  <br/> |+14255550123;ext=10001 devient +14255550123  <br/> |

Qu’une liaison wan soit disponible ou non, si votre organisation n’a pas de numéros DID configurés pour des utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro de poste unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro accessible par l’homologue de trunk ou la passerelle PSTN sur le site de succursale. Vous devez également configurer l’URI de ligne du numéro de téléphone de votre organisation pour inclure son propre poste unique pour les appels à router vers ce numéro.

#### <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survavibilité de la messagerie vocale

Exchange La messagerie unifiée est généralement installée uniquement sur un site central et non sur des sites de succursale. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de ligne pour le numéro de téléphone Exchange um Standard automatique qui fournit la messagerie vocale aux utilisateurs de site de succursale nécessite des considérations spéciales, en plus de la stratégie de voix, du plan de numérotation et des règles de normalisation applicables à ce numéro de messagerie vocale.

Les Survivable Branch Appliances (SBA) et les serveurs Survivable Branch Servers offrent une survivabilité de messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau wan. Plus précisément, si vous utilisez un Survivable Branch Appliance ou un Serveur Survivable Branch Server et que le wan devient indisponible, le SBA ou le serveur Survivable Branch Server réachemine les appels sans réponse via le réseau téléphonique téléphonique public (PSTN) vers la messagerie un Exchange sur le site central. Avec un SBA ou un serveur Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le réseau PSTN lors d’une panne du réseau wan. Enfin, lors d’une panne du réseau wan, le Survivable Branch Appliance ou le Survivable Branch Server place en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie un Exchange lors de la restauration du wan. Pour vous assurer que le réroutage de la messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de nom de service complet du pool de sites centraux et une entrée pour le nom de sujet du serveur Edge au fichier d’hôtes sur le serveur Survivable Branch Server. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

- Un administrateur microsoft Exchange doit configurer la Exchange de Standard automatique de la Standard automatique (AA) pour accepter uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

- L’administrateur Skype Entreprise Server doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone comme numéro de attendant automatique de messagerie unie **Exchange** dans les paramètres de réroutage de la messagerie vocale pour le Survivable Branch Appliance ou le serveur de succursale.

- L’administrateur Skype Entreprise Server doit obtenir le numéro de téléphone d’accès abonné à  la messagerie un Exchange et utiliser ce numéro comme numéro d’accès abonné dans les paramètres de réroutage de la messagerie vocale pour le Survivable Branch Appliance ou le Serveur Survivable Branch Server.

- L’administrateur Skype Entreprise Server doit configurer la messagerie un Exchange afin qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la messagerie vocale lors d’une panne du réseau wan.

- Lorsque la liaison wan est indisponible, les appels aux utilisateurs de site de succursale peuvent être acheminés vers la boîte aux lettres vocale de messagerie unifiée Exchange de l’utilisateur, mais uniquement si la stratégie de voix appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et n’inclut pas de numéro de poste.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

#### <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Le matériel et les logiciels requis sont intégrés au Survivable Branch Appliance. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise se trouvent uniquement dans les sites centraux, les utilisateurs de sites de succursale ne pourront pas se connecter à eux lors d’une panne du réseau wan. Par conséquent, la découverte Skype Entreprise Server qui utilise l’enregistrement de ressource DNS SRV (Service (SRV) échouera. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agit d’un serveur autonome ou d’une version du Survivable Branch Appliance qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez votre fournisseur Survivable Branch Appliance.

> [!NOTE]
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. Le Survivable Branch Appliance authentifier les clients à l’aide d’un certificat spécial qu’il envoie au client en réponse à la demande de certificat du client lorsqu’il se signe.

Skype Entreprise clients peuvent découvrir le Skype Entreprise Server à l’aide de l’option DHCP 120 (option de bureau d’enregistrement SIP). La configuration peut prendre l’une des deux formes suivantes :

- Configurez le serveur DHCP sur le site de succursale pour répondre aux requêtes DHCP 120, qui retournent le nom de domaine général du serveur d’inscriptions sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.

- Activer Skype Entreprise Server DHCP. Lorsque cette option est désactivée, le Skype Entreprise Server de bureau d’enregistrement répond aux requêtes DHCP de l’option 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Enfin, les utilisateurs de site de succursale doivent être configurés Voix Entreprise et configurés avec un point de terminaison de communications unifiées approprié.

#### <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

Les conditions requises pour les serveurs Survivable Branch Server sont les mêmes que pour un serveur frontal. Pour plus d’informations, [voir Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Conditions requises pour Full-Scale Skype Entreprise Server Branch-Site déploiements

Pour plus d’informations, voir [Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) in the Planning documentation.

### <a name="example-configuring-a-failover-route"></a>Exemple : configuration d’un itinéraire deover

 L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.

**Tableau 1. Stratégie utilisateur**

|**Stratégie utilisateur**|**Utilisation téléphonique**|
|:-----|:-----|
|Default Calling Policy  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Redmond Local Policy  <br/> |RedmondLocal  <br/> |
|Dallas Calling Policy  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tableau 2. Itinéraires**


| **Nom de l’itinéraire**             | **Modèle de numéro** | **Utilisation téléphonique**         | **Trunk**                                 | **Passerelle**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond Local Route  <br/> | ^\+1(425           | 206                     | 253)(\d {7} )$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Dallas Local Route  <br/>  | ^\+1(972           | 214                     | 469)(\d {7} )$  <br/>                       | Local  <br/>                                    |
| Universal Route  <br/>     | ^\+? (\d \* ) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Dallas Users Route  <br/>  | ^\+? (\d \* ) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.