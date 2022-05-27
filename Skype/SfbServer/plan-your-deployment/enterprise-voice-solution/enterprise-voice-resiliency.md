---
title: Planifier la résilience Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: Découvrez comment prendre en charge la résilience vocale dans Skype Entreprise Server Voix Entreprise, à la fois sur les sites centraux et les sites de succursale. Les options de site de branche incluent le déploiement d’appliances survivable Branch ou de serveurs de branches survivables.
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675476"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planifier la résilience Voix Entreprise dans Skype Entreprise Server

Découvrez comment prendre en charge la résilience vocale dans Skype Entreprise Server Voix Entreprise, à la fois sur les sites centraux et les sites de succursale. Les options de site de branche incluent le déploiement d’appliances survivable Branch ou de serveurs de branches survivables.

La résilience vocale fait référence à la capacité des utilisateurs à continuer à passer et à recevoir des appels si un site central qui héberge Skype Entreprise Server devient indisponible, qu’il s’agisse d’une défaillance du réseau étendu (WAN) ou d’une autre cause. Si un site central tombe en panne, Voix Entreprise doit basculer vers un site de sauvegarde pour assurer la continuité du service. En cas de panne du réseau étendu, les appels de la succursale doivent être redirigés vers une passerelle PSTN locale. Cette section traite de la planification pour la résistance des communications vocales en cas de panne du site central ou du réseau étendu.

## <a name="central-site-resiliency"></a>Résilience des sites centraux

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. Le maintien des services d’urgence, l’accès au support technique et la possibilité d’effectuer des tâches métier critiques lorsqu’un site central est hors service sont essentiels pour toute solution de résilience Voix Entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

- Le basculement vocal doit être fourni.

- Les utilisateurs qui s’inscrivent habituellement auprès du pool frontal sur le site central doivent être en mesure de s’inscrire auprès d’un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’entre eux est résolu en pool d’administrateurs ou pool frontal dans chacun de vos sites centraux. Vous pouvez ajuster la priorité et les pondérations des enregistrements SRV afin que les utilisateurs qui sont servis par ce site central obtiennent le pool d’administrateurs et de serveurs frontaux correspondant avant ceux des autres enregistrements SRV.

- Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

### <a name="architecture-and-topology"></a>Architecture et topologie

La planification de la résilience vocale sur un site central nécessite une compréhension de base du rôle central joué par le bureau d’enregistrement Skype Entreprise Server dans l’activation du basculement vocal. Le bureau d’enregistrement Skype Entreprise Server est un service qui permet l’inscription et l’authentification du client et fournit des services de routage. Il s’exécute sur tous les serveurs Édition Standard, serveur frontal, directeur ou survivable Branch Appliance. Un pool de bureaux d’enregistrement se compose de services de bureau d’enregistrement s’exécutant sur le pool frontal et résidant sur le même site. Un client Skype Entreprise découvre le pool frontal par le biais du mécanisme de découverte suivant :

1. Enregistrement DNS SRV

2. Service web de découverte automatique

3. Option DHCP 120

Une fois que le client Skype Entreprise se connecte au pool frontal, il est dirigé par l’équilibreur de charge vers l’un des serveurs frontaux du pool. Ce serveur frontal, à son tour, redirige le client vers un bureau d’enregistrement préféré dans le pool.

Chaque utilisateur activé pour Voix Entreprise est affecté à un pool de bureaux d’enregistrement particulier, qui devient le pool principal du bureau d’enregistrement de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite quant au nombre d’utilisateurs du site de branche, y compris les utilisateurs inscrits auprès d’une appliance survivable Branch Appliance.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide des paramètres de résilience du Générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1. Un client découvre Skype Entreprise Server par le biais d’enregistrements SRV DNS. Dans Skype Entreprise Server, les enregistrements SRV DNS peuvent être configurés pour retourner plusieurs noms de domaine complets à la requête SRV DNS. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool d’administrateurs dans l’un des emplacements est disponible, le client peut se connecter au premier tronçon Skype Entreprise Server.

    > [!NOTE]
    > L’utilisation d’un pool d’administrateurs est facultative. Un pool frontal peut être utilisé à la place.

2. Le pool d’administrateurs informe le client Skype Entreprise du pool principal du bureau d’enregistrement et du pool de serveurs d’inscriptions de sauvegarde de l’utilisateur.

3. Le client Skype Entreprise tente d’abord de se connecter au pool d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool principal du bureau d’enregistrement n’est pas disponible, le client Skype Entreprise tente de se connecter au pool de serveurs d’inscriptions de sauvegarde. Si le pool de serveurs d’inscriptions de sauvegarde est disponible et a déterminé que le pool d’inscriptions principal de l’utilisateur n’est pas disponible (en détectant l’absence de pulsation pour un intervalle de basculement spécifié), le pool de serveurs d’inscriptions de sauvegarde accepte l’inscription de l’utilisateur. Une fois que le bureau d’enregistrement de sauvegarde a détecté que le bureau d’enregistrement principal est à nouveau disponible, le pool de serveurs d’inscriptions de sauvegarde redirige les clients de basculement vers leur pool principal.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

- Les sites où résident les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

- Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

- Chaque pool de bureaux d’enregistrement doit être équilibré à l’aide de l’équilibrage de charge DNS, de l’équilibrage de charge matérielle ou des deux. Pour plus d’informations sur la planification de votre configuration d’équilibrage de charge, consultez [les exigences d’équilibrage de charge pour Skype Entreprise](../../plan-your-deployment/network-requirements/load-balancing.md).

- Chaque utilisateur doit être affecté à un pool de serveurs d’inscriptions principal à l’aide de l’applet de commande Skype Entreprise Server Management Shell **set-CsUser** ou de l’Skype Entreprise Server Panneau de configuration.

- Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

- Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde au bout de 300 secondes. Vous pouvez modifier cet intervalle à l’aide du générateur de topologie Skype Entreprise Server.

- Configurez un itinéraire de basculement. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

- Si le site central contenait votre serveur d’administration principal et que le site est susceptible d’être arrêté pendant une période prolongée, vous devrez réinstaller vos outils de gestion sur le site de sauvegarde ; Sinon, vous ne pourrez pas modifier les paramètres de gestion.

### <a name="dependencies"></a>Dépendances

Skype Entreprise Server dépend de l’infrastructure et des composants logiciels suivants pour garantir la résilience vocale :

|**Composant** <br/> |**Fonctionnelle** <br/> |
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

  - Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur pour inclure Exchange serveurs de messagerie unifiée à la fois sur le site central et sur le site de sauvegarde, mais désignez la sauvegarde Exchange serveurs de messagerie unifiée comme étant désactivés. Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs de messagerie unifiée Exchange sur le site de sauvegarde comme étant activés.

    Si aucune des solutions précédentes n’est possible, Exchange messagerie unifiée ne sera pas disponible si le site central devient indisponible.

- Conférence de tous types

    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, d’autres utilisateurs ne peuvent pas participer à des conférences hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

- standard automatique de conférence

- Routage basé sur la présence et DND

- Mise à jour des paramètres de transfert d’appel

- Service Response Group et parcage d’appel

- Provisionnement des nouveaux téléphones et clients

- Recherche web du carnet d’adresses

## <a name="branch-site-resiliency"></a>Résilience du site branch

Si vous souhaitez fournir une résilience de site de branche, c’est-à-dire un service Voix Entreprise haute disponibilité, vous disposez de trois options pour ce faire :

- Survivable Branch Appliance

- serveur Survivable Branch Server

- Un déploiement complet Skype Entreprise Server sur le site de la branche

Ce guide vous aidera à choisir la solution de résistance la plus adaptée à votre organisation et, en fonction de votre choix, la solution de connectivité PSTN à utiliser. Il vous aidera également à préparer le déploiement de la solution choisie en décrivant les conditions préalables et les autres éléments à prendre en compte pour la planification.

### <a name="branch-site-resiliency-features"></a>Fonctionnalités de résilience de site de branche

Si vous fournissez une résilience de site de branche, si la connexion WAN d’un site de branche à un site central échoue ou si le site central est inaccessible, les fonctionnalités vocales suivantes doivent continuer à être disponibles :

- Appels PSTN entrants et sortants

- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

- Messagerie instantanée entre deux utilisateurs

- Transfert d’appel, sonnerie simultanée de points de terminaison, délégation d’appel et services d’appel d’équipe, mais uniquement si le délégant et le délégué (par exemple, un responsable et l’administrateur du responsable) ou tous les membres de l’équipe sont configurés sur le même site

- Enregistrements des détails des appels (CDR)

- Conférence rendez-vous par réseau téléphonique commuté (PSTN) avec standard automatique de conférence

- Fonctionnalités de messagerie vocale, si vous configurez les paramètres de réacheminement de la messagerie vocale.

- Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes ne seront disponibles que si votre solution de résilience est un déploiement Skype Entreprise Server à grande échelle sur le site de branche :

- messagerie instantanée, conférence A/V et web

- routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

- Mise à jour des paramètres de transfert d’appel

- Application Response Group et application Parc d’appels

- Provisionnement de nouveaux téléphones et clients, mais uniquement si services de domaine Active Directory est présent sur le site de succursale.

- Enhanced 9-1-1 (E9-1-1)

    Si E9-1-1 est déployé et que la jonction SIP sur le site central n’est pas disponible, car la liaison WAN est désactivée, l’appliance survivable Branch appliance route les appels E9-1-1 vers la passerelle de branche locale. Pour activer cette fonctionnalité, les stratégies vocales des utilisateurs du site de branche doivent router les appels vers la passerelle locale en cas de défaillance du WAN.

> [!NOTE]
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Les utilisateurs hébergés dans des configurations SBA ne pourront pas envoyer d’E/S ni voir Présence avec des contacts XMPP.

### <a name="branch-site-resiliency-solutions"></a>Solutions de résilience de site de branche

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. Plus précisément, si vous perdez la connexion au site central, les utilisateurs du site de succursale continueront d’avoir Voix Entreprise service et de messagerie vocale (si vous configurez les paramètres de réacheminement de la messagerie vocale). Cependant, pour les sites comportant moins de 25 utilisateurs une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau suivant peut vous aider à déterminer l’option appropriée.

|**Si vous...**|**Nous vous recommandons d’utiliser un...**|
|:-----|:-----|
|Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’un support d’administration local  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance est un serveur de panneau standard avec un serveur d’enregistrement et de médiation Skype Entreprise Server exécuté sur Windows Server 2008 R2. Survivable Branch Appliance contient également une passerelle de réseau téléphonique commuté (RTC) publique. Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA)) assurent une connexion PSTN continue en cas de panne du WAN, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.  <br/> Pour plus d’informations sur survivable Branch Appliances, consultez « Survivable Branch Appliance Details », plus loin dans cette rubrique.  <br/> **Note:** Si vous décidez d’utiliser également une jonction SIP avec votre survivable Branch Appliance, contactez votre fournisseur Survivable Branch Appliance pour en savoir plus sur le fournisseur de services le mieux adapté à votre organisation. <br/> |
|Héberger entre 1 000 et 2 000 utilisateurs sur votre site de succursale, ne pas disposer d’une connexion WAN résiliente et avoir formé Skype Entreprise Server administrateurs disponibles  <br/> |Survivable Branch Server ou deux appliances survivable Branch.  <br/> Survivable Branch Server est un serveur Windows qui répond à la configuration matérielle requise spécifiée et sur lequel Skype Entreprise Server logiciel du serveur de bureau d’enregistrement et de médiation est installé. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.  <br/> Pour plus d’informations sur survivable Branch Servers, consultez « Survivable Branch Server Details », plus loin dans cette rubrique.  <br/> |
|Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour jusqu’à 5 000 utilisateurs, et que vous avez formé Skype Entreprise Server administrateurs disponibles  <br/> |Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.  <br/> Un déploiement Skype Entreprise Server à grande échelle fournit une connexion PSTN continue et une présence et des conférences résilientes en cas de défaillance du RÉSEAU ÉTENDU.  <br/> |

#### <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résilience de la branche vocale.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

Le Skype Entreprise Server Survivable Branch Appliance comprend les composants suivants :

- un serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs, et le routage des appels ;

- un serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;

- une passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du WAN ;

- SQL Server Express pour le stockage local des données d’utilisateur.

Survivable Branch Appliance inclut également des jonctions PSTN, des ports analogiques et une carte Ethernet.

Si la connexion WAN du site de succursale à un site central devient indisponible, les utilisateurs de branche internes continuent d’être inscrits auprès du bureau d’enregistrement survivable Branch Appliance et obtiennent un service vocal ininterrompu à l’aide de la connexion Survivable Branch Appliance au rtc. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison WAN vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion WAN redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Ni le basculement vers Survivable Branch Appliance, ni la restauration du service ne nécessitent la présence d’un administrateur informatique.

Skype Entreprise Server prend en charge jusqu’à deux survivable Branch Appliance sur un site de branche.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Survivable Branch Appliance est fabriqué par des fabricants d’équipement d’origine en partenariat avec Microsoft et déployé en leur nom par des détaillants à valeur ajoutée. Ce déploiement ne doit se produire qu’une fois que Skype Entreprise Server a été déployé sur le site central, qu’une connexion WAN au site de branche est en place et que les utilisateurs du site de branche sont activés pour Voix Entreprise.

Pour plus d’informations sur les phases ci-dessous, voir [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) dans la documentation de déploiement.

|**Étape**|**Étapes**|**Droits d’utilisateur**|
|:-----|:-----|:-----|
|Configurer services de domaine Active Directory pour survivable Branch Appliance  <br/> |**Sur le site central :** <br/>  Créez un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activera Survivable Branch Appliance sur le site de la branche. <br/>  Créez un compte d’ordinateur (avec le nom de domaine complet (FQDN) applicable pour Survivable Branch Appliance dans services de domaine Active Directory. <br/>  Dans le Générateur de topologie, créez et publiez survivable Branch Appliance. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. Survivable Branch Appliance doit appartenir au groupe RTCSBAUniversalServices, ce qui se produit automatiquement lorsque vous utilisez le Générateur de topologie.  <br/> |
|Installez et activez survivable Branch Appliance.  <br/> |**Sur le site de succursale :** <br/>  Connecter survivable Branch Appliance à un port Ethernet et un port PSTN. <br/>  Démarrez survivable Branch Appliance. <br/>  Joignez Survivable Branch Appliance au domaine à l’aide du compte d’utilisateur de domaine créé pour Survivable Branch Appliance sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur. <br/>  Configurez survivable Branch Appliance à l’aide de l’interface utilisateur OEM. <br/>  Testez la connectivité PSTN. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Serveur Survivable Branch Server en détail

Dans le Générateur de topologie, créez le site de branche, ajoutez survivable Branch Server à ce site, puis exécutez l’Assistant Déploiement Skype Entreprise Server sur l’ordinateur sur lequel vous souhaitez installer le rôle.

### <a name="branch-site-resiliency-requirements"></a>Exigences en matière de résilience des sites de succursale

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résilience du site de branche en définissant leur pool de serveurs d’inscriptions comme Survivable Branch Appliance (SBA) ou Survivable Branch Server.

#### <a name="registrar-assignments-for-branch-users"></a>Assignations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résilience de site de branche que vous choisissez, vous devez affecter un bureau d’enregistrement principal à chaque utilisateur. Les utilisateurs du site de succursale doivent toujours s’inscrire auprès du bureau d’enregistrement sur le site de succursale, que ce bureau d’enregistrement réside dans survivable Branch Appliance, Survivable Branch Server ou Skype Entreprise Server serveur standard ou Êdition Entreprise autonome. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si survivable Branch Appliance devient indisponible, les clients du site de branche découvrent automatiquement le bureau d’enregistrement de sauvegarde.

Si un site de branche n’a pas de serveur DNS, il existe deux autres façons de configurer la découverte de Survivable Branch Appliance ou survivable Branch Server :

- Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de branche pour pointer vers le nom de domaine complet (FQDN) de Survivable Branch Appliance ou survivable Branch Server.

- Configurez Survivable Branch Appliance ou Survivable Branch Server pour répondre aux requêtes DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau de l’utilisateur pour les utilisateurs d’un site de succursale. Cette stratégie doit inclure un itinéraire principal qui utilise survivable Branch Appliance ou passerelle de serveur de succursales, ainsi qu’un ou plusieurs itinéraires de sauvegarde qui utilisent une jonction avec une passerelle de réseau téléphonique commuté (RTC) publique sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire de sauvegarde qui utilise une ou plusieurs passerelles de site central est utilisé à la place. De cette façon, quel que soit l’emplacement d’inscription d’un utilisateur (sur le bureau d’enregistrement du site de succursale ou le pool de serveurs d’inscriptions de sauvegarde sur le site central), la stratégie VoIP de l’utilisateur est toujours en vigueur. Il s’agit d’une considération importante pour les scénarios de basculement. Par exemple, si vous devez renommer Survivable Branch Appliance ou reconfigurer survivable Branch Appliance pour vous connecter à un pool de serveurs d’inscriptions de sauvegarde sur le site central, vous devez déplacer les utilisateurs du site de branche vers le site central pendant toute la durée. (Pour plus d’informations sur le renommage ou la reconfiguration d’un survivable Branch Appliance, consultez [l’annexe B : Gestion d’une appliance survivable Branch appliance](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) dans la documentation de déploiement.) Si ces utilisateurs n’ont pas de stratégies VoIP au niveau de l’utilisateur ou de plans de numérotation au niveau de l’utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site central s’appliquent aux utilisateurs par défaut, au lieu des stratégies VoIP et des plans de numérotation au niveau du site de la branche. Dans ce scénario, sauf si les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde peuvent également s’appliquer aux utilisateurs du site de branche, leurs appels échouent. Par exemple, si les utilisateurs d’un site de succursale situé au Japon sont déplacés vers un site central à Redmond, il est peu probable qu’un plan de numérotation avec des règles de normalisation qui ajoutent +1425 à tous les appels à 7 chiffres ne traduise pas correctement les appels pour ces utilisateurs.

> [!IMPORTANT]
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique PSTN à la stratégie utilisateur de succursale et d’assigner des itinéraires séparés à chacun d’entre eux. Le premier itinéraire, ou principal, dirige les appels vers la passerelle associée à Survivable Branch Appliance (SBA) ou au serveur de succursales ; la deuxième route, ou sauvegarde, dirige les appels vers la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires assignés au premier enregistrement d’utilisation PSTN avant d’essayer le deuxième enregistrement.

Pour vous assurer que les appels entrants aux utilisateurs du site de branche atteignent ces utilisateurs lorsque la passerelle de branche ou le composant Windows du site Survivable Branch Appliance n’est pas disponible (ce qui se produit, par exemple, si survivable Branch Appliance ou la passerelle de branche était en panne pour la maintenance), créez un itinéraire de basculement sur la passerelle (ou travaillez avec votre fournisseur de numérotation directe entrante (DID) pour rediriger les appels entrants vers le pool du bureau d’enregistrement de sauvegarde sur le site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire traduit les numéros pour qu’ils soient conformes à la passerelle RTC ou aux formats de numéros de téléphone acceptés d’un autre homologue de jonction. Pour plus d’informations sur la création d’un itinéraire de basculement, voir [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux appliances survivable Branch sur un site de succursale, vous pouvez créer un plan de numérotation au niveau du site pour les deux, sauf si un plan distinct de niveau de service pour chacun d’eux est nécessaire.

> [!NOTE]
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite quant au nombre d’utilisateurs du site de branche, y compris les utilisateurs inscrits auprès d’une appliance survivable Branch Appliance.

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, consultez [Créer ou modifier un plan de numérotation dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md) et [créer la stratégie de routage VoIP pour les utilisateurs de branche](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) dans la documentation de déploiement.

#### <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lors de la préparation des plans de numérotation et des stratégies de voix pour les utilisateurs du site de branche, veillez à inclure des règles de normalisation et des règles de traduction qui correspondent aux chaînes et au format de numéro utilisés dans l’attribut msRTCSIP-line (ou URI de ligne), afin que les appels Skype Entreprise activés entre les utilisateurs du site de succursale et les utilisateurs du site central soient routés correctement, en particulier lorsque les appels doivent être redirigés sur le réseau PSTN, car la liaison WAN n’est pas disponible. D’autres éléments particuliers sont à prendre en considération dans le cas des numéros composés qui incluent des numéros de poste et non simplement des numéros de téléphone.

Les règles de normalisation et de traduction qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec uniquement un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Toutefois, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour traduire le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :

|**Nom de la règle**|**Description**|**Modèle de numéro**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Ne traduit pas les numéros à 5 chiffres  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 n’est pas traduit  <br/> |

Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. En cas de panne du réseau ÉTENDU, si un utilisateur de site de branche appelle un utilisateur de site central uniquement en composant l’extension de l’utilisateur du site central, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro d’extension unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez disposer d’une règle de traduction sortante qui ajoute à la place le numéro de téléphone complet de votre organisation. Par exemple :

|**Description**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Convertit les numéros à 5 chiffres en numéro de téléphone et extension d’un utilisateur  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 devient +14255550123;ext=10001  <br/> |
|Convertit les numéros à 5 chiffres en numéro de téléphone de votre organisation et en extension d’utilisateur  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 devient +14255550100;ext=10001  <br/> |

Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de traduction sortante doit également supprimer le numéro de poste. Par exemple :

|**Description**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Supprime le poste des numéros de téléphone présentant un numéro de poste  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 devient +14255550123  <br/> |

Qu’un lien WAN soit disponible ou non, si votre organisation n’a pas de numéros DID configurés pour des utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro d’extension unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro accessible par l’homologue de jonction ou la passerelle RTC sur le site de la branche. Vous devez également configurer l’URI de ligne de numéro de téléphone de votre organisation afin d’inclure sa propre extension unique pour que les appels soient routées vers ce numéro.

#### <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survavibilité de la messagerie vocale

Exchange messagerie unifiée est généralement installée uniquement sur un site central et non sur des sites de succursale. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de ligne pour le Exchange numéro de téléphone du standard automatique de messagerie unifiée qui fournit la messagerie vocale aux utilisateurs du site de succursale nécessite des considérations spéciales, en plus de la stratégie vocale, du plan de numérotation et des règles de normalisation applicables à ce numéro de messagerie vocale.

Survivable Branch Appliances (SBA) et Survivable Branch Servers offrent une survivabilité de messagerie vocale pour les utilisateurs de branche pendant une panne wan. Plus précisément, si vous utilisez survivable Branch Appliance ou Survivable Branch Server et que le wan devient indisponible, le serveur SBA ou Survivable Branch Server redirige les appels sans réponse sur le rtc pour Exchange messagerie unifiée sur le site central. Avec un serveur SBA ou Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le réseau PSTN en cas de panne du RÉSEAU ÉTENDU. Enfin, lors d’une panne du WAN, Survivable Branch Appliance ou Survivable Branch Server met en file d’attente les notifications d’appel manqué, puis les charge sur le serveur de messagerie unifiée Exchange lors de la restauration du WAN. Pour vous assurer que le réacheminement de la messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet du pool de sites central et une entrée pour le nom de domaine complet du serveur Edge au fichier hosts sur le serveur survivable Branch Server. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

- Un administrateur Microsoft Exchange doit configurer Exchange standard automatique de messagerie unifiée (AA) pour accepter uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

- L’administrateur Skype Entreprise Server doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone comme numéro de **standard automatique um d’échange** dans les paramètres de réacheminement de la messagerie vocale pour survivable Branch Appliance ou le serveur de succursales.

- L’administrateur Skype Entreprise Server doit obtenir le numéro de téléphone d’accès de l’abonné de messagerie unifiée Exchange et utiliser ce numéro comme numéro **d’accès de l’abonné** dans les paramètres de réacheminement de la messagerie vocale pour Survivable Branch Appliance ou Survivable Branch Server.

- L’administrateur Skype Entreprise Server doit configurer Exchange messagerie unifiée afin qu’un seul plan de numérotation soit associé à tous les utilisateurs de la branche qui ont besoin d’accéder à la messagerie vocale en cas de panne du RÉSEAU ÉTENDU.

- Lorsque le lien WAN n’est pas disponible, les appels aux utilisateurs du site de branche peuvent être acheminés vers la boîte aux lettres vocale Exchange messagerie unifiée de l’utilisateur, mais uniquement si la stratégie vocale appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et n’inclut pas de numéro d’extension.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

#### <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Le matériel et les logiciels requis sont intégrés à Survivable Branch Appliance. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise se trouvent uniquement dans des sites centraux, les utilisateurs du site de branche ne peuvent pas se connecter à ces derniers en cas de panne du réseau étendu. Par conséquent, Skype Entreprise Server découverte qui utilise l’enregistrement de ressource SRV (service) DNS échoue. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou d’une version de Survivable Branch Appliance qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez votre fournisseur Survivable Branch Appliance.

> [!NOTE]
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. Survivable Branch Appliance authentifie les clients à l’aide d’un certificat spécial qu’il envoie au client en réponse à la demande de certificat du client lorsqu’il se connecte.

Skype Entreprise clients peuvent découvrir l’Skype Entreprise Server à l’aide de l’option DHCP 120 (option du bureau d’enregistrement SIP). La configuration peut prendre l’une des deux formes suivantes :

- Configurez le serveur DHCP sur le site de branche pour répondre aux requêtes DHCP 120, qui retournent le nom de domaine complet du bureau d’enregistrement sur survivable Branch Appliance ou Survivable Branch Server.

- Activez Skype Entreprise Server DHCP. Lorsque cette option est activée, le bureau d’enregistrement Skype Entreprise Server répond aux requêtes DHCP Option 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Enfin, les utilisateurs du site de branche doivent être configurés pour Voix Entreprise et approvisionnés avec un point de terminaison de communication unifié approprié.

#### <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

Les exigences pour les serveurs survivable Branch sont les mêmes que pour un serveur frontal. Pour plus d’informations, consultez [la configuration requise du serveur pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Configuration requise pour les déploiements Full-Scale Skype Entreprise Server Branch-Site

Pour plus d’informations, consultez [la configuration requise du serveur pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) dans la documentation de planification.

### <a name="example-configuring-a-failover-route"></a>Exemple : configuration d’un itinéraire de basculement

 L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.

**Tableau 1. Stratégie utilisateur**

|**Stratégie utilisateur**|**Utilisation téléphonique**|
|:-----|:-----|
|Default Calling Policy  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Redmond Local Policy  <br/> |RedmondLocal  <br/> |
|Dallas Calling Policy  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tableau 2. Itinéraires**


| **Nom de l’itinéraire**             | **Modèle de numéro** | **Utilisation téléphonique**         | **Tronc**                                 | **Passerelle**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond Local Route  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Dallas Local Route  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | Local  <br/>                                    |
| Universal Route  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Dallas Users Route  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.