---
title: Plan for Enterprise Voice resiliency in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: En savoir plus sur la prise en charge de la résilience vocale dans Skype entreprise Server Voice, sur des sites centraux et des sites de succursales. Les options de site de succursale incluent le déploiement d’appareils de succursales survivant ou de succursales survivant.
ms.openlocfilehash: e64ac79ef49339401c5b2d0bbb7d27140eca4296
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802944"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Plan for Enterprise Voice resiliency in Skype for Business Server

En savoir plus sur la prise en charge de la résilience vocale dans Skype entreprise Server Voice, sur des sites centraux et des sites de succursales. Les options de site de succursale incluent le déploiement d’appareils de succursales survivant ou de succursales survivant.

La résilience vocale désigne la possibilité pour les utilisateurs de continuer à passer et à recevoir des appels si un site central hébergeant Skype entreprise Server devient indisponible, qu’il s’agisse d’un réseau étendu (WAN) ou d’une autre cause. Si un site central ne fonctionne pas, le service de voix en entreprise doit basculer vers un site de sauvegarde pour assurer la continuité du service. En cas de panne du réseau étendu, les appels de la succursale doivent être redirigés vers une passerelle RTC locale. Cette section traite de la planification pour la résistance des communications vocales en cas de panne du site central ou du réseau étendu.

## <a name="central-site-resiliency"></a>Résistance des sites centraux

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. La mise à jour des services d’urgence, l’accès au support technique et la possibilité d’effectuer des tâches professionnelles critiques quand un site central est hors service est essentiel pour toute solution de résilience vocale d’entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

- Le basculement vocal doit être fourni.

- Les utilisateurs qui s’inscrivent habituellement avec le pool frontal sur le site central doivent pouvoir s’inscrire avec un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’eux résolu vers un pool de directeurs ou un pool frontal dans chacun de vos sites centraux. Vous pouvez ajuster la priorité et le poids des enregistrements SRV de telle sorte que les utilisateurs qui sont servis par ce site central obtiennent le directeur et la liste frontale correspondants dans d’autres enregistrements SRV.

- Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

### <a name="architecture-and-topology"></a>Architecture et topologie

La planification de la résilience vocale sur un site central nécessite une connaissance de base du rôle central joué par le Bureau d’enregistrement de Skype entreprise Server en activant le basculement sur voix. Le Bureau d’enregistrement de Skype entreprise Server est un service qui permet l’inscription et l’authentification du client et fournit les services de routage. Il s’exécute sur tous les appareils Standard Edition Server, serveur frontal, directeur ou branche Survivable. Un pool d’bureaux d’enregistrement est constitué de services d’enregistrement de registre en cours d’exécution sur le pool frontal et résidant sur le même site. Un client Skype entreprise Découvre le pool frontal par le biais du mécanisme de découverte suivant :

1. Enregistrement DNS SRV

2. Service Web de découverte automatique

3. Option DHCP 120

Une fois le client Skype entreprise connecté au pool frontal, il est dirigé par le biais de l’équilibrage de charge vers l’un des serveurs frontaux de la liste. Ce serveur frontal, à son tour, redirige le client vers un bureau d’enregistrement préféré dans le pool.

Chaque utilisateur activé pour voix entreprise est attribué à un pool d’bureaux d’enregistrement particulier, lequel devient le pool d’inscriptions principal de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite sur le nombre d’utilisateurs de sites de succursales, y compris les utilisateurs enregistrés auprès d’une unité de succursale Survivable.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide des paramètres de résilience du générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1. Un client Découvre Skype entreprise Server par le biais d’enregistrements DNS SRV. Dans Skype entreprise Server, les enregistrements DNS SRV peuvent être configurés pour renvoyer plusieurs FQDN vers la requête DNS SRV. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool de directeurs dans l’un des emplacements est disponible, le client peut se connecter au premier tronçon Skype entreprise Server.

    > [!NOTE]
    > L’utilisation d’un pool de directeurs est facultative. Un pool frontal peut être utilisé à la place.

2. Le pool de directeurs informe le client Skype entreprise du pool d’inscriptions principal de l’utilisateur et du pool d’inscriptions de sauvegarde.

3. Le client Skype entreprise tente d’abord de se connecter au pool d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool principal de bureaux d’enregistrement n’est pas disponible, le client Skype entreprise tente de se connecter au pool d’inscriptions de secours. Si le pool d’enregistrements de sauvegarde est disponible et qu’il a déterminé que le pool d’inscriptions principal de l’utilisateur n’est pas disponible (en détectant un manque de pulsation pour un intervalle de reprise spécifié), le pool d’registraire de sauvegarde accepte l’inscription de l’utilisateur. Quand le serveur d’inscriptions de sauvegarde détecte que le serveur d’inscriptions principal est de nouveau disponible, le pool de serveurs d’inscriptions de sauvegarde redirige les clients de basculement vers leur pool principal.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

- Les sites où se trouvent les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

- Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

- La charge de chaque pool de serveurs d’inscriptions doit être équilibrée via l’équilibrage de la charge DNS, l’équilibrage de la charge matérielle ou les deux. Pour plus d’informations sur la planification de la configuration de l’équilibrage de charge, consultez la section [exigences d’équilibrage de charge pour Skype entreprise](../../plan-your-deployment/network-requirements/load-balancing.md).

- Chaque utilisateur doit être affecté à un pool d’inscriptions principal en utilisant l’applet **de commande Set-Csuser** de Skype entreprise Server Management Shell ou le panneau de configuration Skype entreprise Server.

- Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

- Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde après 300 secondes. Vous pouvez modifier cet intervalle à l’aide du générateur de topologie Skype entreprise Server.

- Configurez un itinéraire de basculement. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

- Si le site central contient votre serveur de gestion principal et que le site est susceptible d’être arrêté pour une période prolongée, vous devrez réinstaller vos outils de gestion sur le site de sauvegarde. dans le cas contraire, vous ne pourrez pas modifier les paramètres de gestion.

### <a name="dependencies"></a>Dépendances

Skype entreprise Server dépend des composants d’infrastructure et de logiciels suivants pour garantir la résilience vocale :

|**Composant** <br/> |**Fonction** <br/> |
|:-----|:-----|
|DNS  <br/> |Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client  <br/> |
|Exchange et services web Exchange (EWS)  <br/> |Stockage des contacts ; données de calendrier  <br/> |
|Messagerie unifiée Exchange et services web Exchange  <br/> |Journaux des appels, liste des messages vocaux, messagerie vocale  <br/> |
|Options DHCP 120  <br/> |Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour que cette opération fonctionne, un serveur DHCP doit être configuré ou le protocole DHCP de Skype entreprise Server doit être activé.  <br/> |

### <a name="survivable-voice-features"></a>Fonctionnalités vocales de secours

Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :

- Appels RTC sortants

- Appels RTC entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde

- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

- Messagerie instantanée entre deux utilisateurs et partage audio et vidéo entre des utilisateurs situés sur le même site

- Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel (ou tous les membres de l’équipe) sont configurés sur le même site.

- Les téléphones et clients existants continuent à fonctionner.

- Enregistrement des détails des appels (CDR)

- Authentification et autorisation

En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :

- Dépôt et récupération de messages vocaux

    Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :

  - Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.

  - Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur de manière à inclure les serveurs de messagerie unifiée Exchange à la fois sur le site central et sur le site de sauvegarde, mais définissez les serveurs de messagerie unifiée Exchange Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs Exchange UM sur le site de sauvegarde comme activé.

    Si aucune des solutions précédentes n’est possible, la messagerie unifiée Exchange ne sera pas disponible dans l’éventualité où le site central ne sera pas disponible.

- Conférence de tout type

    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, les autres utilisateurs ne peuvent pas rejoindre des conférences hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

- Standard automatique de conférence

- Routage basé sur la présence et DND

- Mise à jour des paramètres de transfert d’appel

- Service Response Group et parcage d’appel

- Provisionnement des nouveaux téléphones et clients

- Recherche web du carnet d’adresses

## <a name="branch-site-resiliency"></a>Résistance des sites de succursale

Si vous souhaitez fournir une résilience de site de succursale, c’est-à-dire, un service voix entreprise haute disponibilité, trois options s’offrent à vous :

- Survivable Branch Appliance

- Serveur SBS

- Déploiement de Skype entreprise Server complet sur le site de succursale

Ce guide vous aidera à choisir la solution de résistance la plus adaptée à votre organisation et, en fonction de votre choix, la solution de connectivité RTC à utiliser. Il vous aidera également à préparer le déploiement de la solution choisie en décrivant les conditions préalables et les autres éléments à prendre en compte pour la planification.

### <a name="branch-site-resiliency-features"></a>Fonctionnalités de résistance pour sites de succursale

Si vous fournissez une résilience de site de succursale, si la connexion WAN d’un site de succursale à un site central échoue ou si le site central n’est pas joignable, les fonctionnalités vocales suivantes doivent rester disponibles :

- Appels RTC entrants et sortants

- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

- Messagerie instantanée entre deux utilisateurs

- Transfert d’appel, sonnerie simultanée de points de terminaison, délégation d’appels et services d’appel d’équipe, mais uniquement si la personne qui a la délégation et le délégué (par exemple, un responsable et l’administrateur du responsable) ou tous les membres d’une équipe sont configurés sur le même site

- Enregistrements des détails des appels (CDR)

- Conférence rendez-vous par réseau téléphonique commuté (RTC) avec standard automatique de conférence

- Fonctionnalités de messagerie vocale si vous configurez les paramètres de réacheminement de la messagerie vocale.

- Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes ne seront disponibles que si votre solution de résilience est un déploiement de Skype entreprise Server à une échelle complète sur le site de la succursale :

- Messagerie instantanée, conférence A/V et web

- Routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

- Mise à jour des paramètres de transfert d’appel

- Application de groupe de réponse et application de parc d’appels

- Attribution de nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents au niveau du site de succursale.

- Enhanced 9-1-1 (E9-1-1)

    Si E9-1-1 est déployé et que le Trunk SIP sur le site central n’est pas disponible parce que la liaison WAN est en panne, l’application branche Survivable achemine les appels E9-1-1 vers la passerelle locale. Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent acheminer les appels vers la passerelle locale en cas de panne du réseau étendu.

> [!NOTE]
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Les utilisateurs hébergés dans des configurations SBA ne seront pas en mesure d’envoyer des messages instantanés ou de voir la présence de contacts XMPP.

### <a name="branch-site-resiliency-solutions"></a>Solutions de résistance de sites de succursale

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. En particulier, si vous perdez la connexion au site central, les utilisateurs du site de succursale disposeront toujours d’un service voix entreprise et de la messagerie vocale (si vous configurez les paramètres de reroutage de la messagerie vocale). Cependant, pour les sites comportant moins de 25 utilisateurs, une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau ci-dessous peut vous aider à déterminer l’option appropriée.

|**Si vous…**|**Nous vous recommandons d’utiliser un…**|
|:-----|:-----|
|Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’une prise en charge d’administration locale.  <br/> |Survivable Branch Appliance  <br/> Le périphérique de la succursale survivant est un serveur de Blades standard doté d’un serveur d’inscription et de médiation de Skype entreprise Server exécuté sur Windows Server 2008 R2. L’unité de branchement Survivable comporte également une passerelle RTC (réseau téléphonique commuté). Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA) assurent une connexion PSTN continue en cas de panne du réseau étendu, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.  <br/> Pour plus d’informations sur les appareils de branchement Survivables, voir la section « informations sur l’appareil de branchement survivant » plus loin dans cette rubrique.  <br/> **Remarque :** Si vous décidez également d’utiliser une ligne SIP avec votre appareil de branchement survivant, contactez le fournisseur de votre application pour savoir quel fournisseur de services est le plus approprié pour votre organisation. <br/> |
|Héberger entre 1000 et 2000 sur votre site de succursale, ne pas disposer d’une connexion WAN fiable et avoir reçu des administrateurs Skype entreprise Server  <br/> |Serveur de succursales survivant ou deux dispositifs de branchement plus survivant.  <br/> Le serveur de succursales survivant est une configuration matérielle requise pour les réunions Windows Server, sur laquelle sont installés les logiciels de bureau d’enregistrement et de médiation de Skype entreprise Server. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.  <br/> Pour plus d’informations sur les serveurs de succursales Survivables, voir la section « informations sur le serveur de succursales survivant » plus loin dans cette rubrique.  <br/> |
|Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour les utilisateurs de 5000 et que vous disposez d’un accès aux administrateurs de Skype entreprise Server.  <br/> |Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.  <br/> Le déploiement de Skype entreprise Server à une échelle complète fournit une connexion RTC continue et une présence et une audioconférence résilientes en cas de panne du réseau étendu.  <br/> |

#### <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résilience de la succursale vocale](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

L’unité de branchement Survivable du serveur Skype entreprise inclut les éléments suivants :

- serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs et routage des appels ;

- serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;

- passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du réseau étendu ;

- SQL Server Express pour le stockage local des données d’utilisateur.

L’unité de branchement Survivable inclut également des Trunks RTC, des ports analogiques et une carte Ethernet.

Si la connexion WAN d’un site de succursale à un site central devient indisponible, les utilisateurs de succursales internes continuent d’être enregistrés auprès du Bureau d’enregistrement d’appliances Survivables et de bénéficier d’un service vocal ininterrompu à l’aide de la connexion de l’appareil de branchement survivant. sur PSTN. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison de réseau étendu vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion de réseau étendu redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Par ailleurs, le basculement vers l’appareil de branchement survivant ou la restauration du service nécessite la présence d’un administrateur informatique.

Skype entreprise Server prend en charge jusqu’à deux appareils de succursales Survivables dans un site de filiale.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Le matériel de branchement survivant est fabriqué par des fabricants d’équipements d’origine en partenariat avec Microsoft et déployés en leur nom par des détaillants à la valeur. Ce déploiement ne doit avoir lieu qu’après le déploiement de Skype entreprise Server sur le site central, une connexion WAN au site de succursale est en place, et les utilisateurs du site de succursale sont activés pour l’entreprise voix.

Pour plus d’informations sur les phases ci-dessous, reportez-vous à [Deploying a Survivable Branch Appliance or Server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) dans la documentation de déploiement.

|**Phase**|**Étapes**|**Droits d’utilisateur**|
|:-----|:-----|:-----|
|Configurer les services de domaine Active Directory pour l’unité de branchement Survivable  <br/> |**Sur le site central :** <br/>  Créer un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activer l’unité de branchement survivant sur le site de la succursale. <br/>  Créer un compte d’ordinateur (à l’aide du nom de domaine complet (FQDN, Fully Qualified Domain Name) pour l’appareil de succursale Survivable dans les services de domaine Active Directory (AD DS). <br/>  Dans le générateur de topologie, créez et publiez l’appareil de branchement survivant. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. L’unité de branchement survivant doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le générateur de topologie.  <br/> |
|Installez et activez l’unité de branchement Survivable.  <br/> |**Sur le site de succursale :** <br/>  Connectez l’unité de branchement survivant à un port Ethernet et un port PSTN. <br/>  Démarrez l’unité de branchement Survivable. <br/>  Rejoignez l’unité de branchement Survivable au domaine, en utilisant le compte d’utilisateur de domaine créé pour l’unité de branchement survivant sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur. <br/>  Configurez l’unité de branchement Survivable à l’aide de l’interface utilisateur OEM. <br/>  Testez la connectivité PSTN. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Serveur Survivable Branch Server en détail

Dans le générateur de topologie, créez le site de succursale, ajoutez le serveur de succursales survivant à ce site, puis exécutez l’Assistant Déploiement de Skype entreprise Server sur l’ordinateur sur lequel vous voulez installer le rôle.

### <a name="branch-site-resiliency-requirements"></a>Configuration requise pour la résistance des sites de succursale

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résilience de site de succursale en définissant leur pool de bureaux d’enregistrement comme étant le serveur de succursales Survivables (SBA) ou le serveur de succursale survivant.

#### <a name="registrar-assignments-for-branch-users"></a>Affectations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale choisie, vous devez affecter un serveur d’inscriptions principal à chaque utilisateur. Les utilisateurs du site de succursale doivent toujours s’inscrire auprès du Bureau d’enregistrement au niveau de la succursale, qu’il s’agisse de bureaux d’enregistrement, de succursales survivables ou de Skype entreprise Server standard ou Enterprise Edition autonomes. serveurs. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si l’unité de branchement Survivable devient indisponible, c’est la façon dont les clients du site de succursale découvrent automatiquement le Bureau d’enregistrement de sauvegarde.

Si un site de succursale ne possède pas de serveur DNS, il existe deux façons de configurer la découverte de l’appareil de succursales survivant ou du serveur de succursales survivant :

- Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale de manière à ce qu’elle pointe vers le nom de domaine complet (FQDN) de l’appareil ou du serveur de succursales survivant.

- Configurez l’application branche Survivable ou le serveur de succursales survivant pour répondre aux requêtes 120 DHCP.

#### <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau utilisateur pour les utilisateurs d’un site de succursale. Il doit s’agir d’un itinéraire principal qui utilise l’appareil de branchement ou la passerelle serveur survivant, et un ou plusieurs itinéraires de sauvegarde qui utilisent une passerelle de réseau téléphonique commuté (PSTN) sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire alternatif faisant appel à une ou plusieurs passerelles de site central est utilisé à la place. De cette façon, quel que soit l’emplacement d’enregistrement d’un utilisateur, sur le Bureau d’enregistrement de sites de succursale ou le pool d’registraire de sauvegarde sur le site central, la stratégie VoIP de l’utilisateur est toujours en vigueur. Il est primordial de tenir compte de ce point pour les scénarios de basculement. Par exemple, si vous avez besoin de renommer l’unité de branchement Survivable ou de reconfigurer l’unité de branchement Survivable pour vous connecter à un pool d’bureaux de connexion sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central pour la durée. (Pour plus d’informations sur le changement de nom d’une unité de branchement survivant, voir [l’annexe B : gestion d’une unité de branchement survivant](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) dans la documentation de déploiement.) Si ces utilisateurs ne disposent pas de stratégies VoIP d’utilisateur ou de plans de numérotation de niveau utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP de niveau de site et les plans de numérotation de niveau site du site central s’appliquent par défaut aux utilisateurs plutôt qu’aux stratégies VoIP et aux plans de numérotation de site. Dans ce scénario, leurs appels échoueront, à moins que les stratégies VoIP et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde puissent également s’appliquer aux utilisateurs du site de succursale. Par exemple, si les utilisateurs d’un site de succursale basé au Japon sont déplacés sur un site central situé à Redmond, il est probable qu’un plan de numérotation dont les règles de normalisation ajoutent le préfixe +1425 à tous les appels à 7 chiffres ne traduiront pas correctement les appels de ces utilisateurs.

> [!IMPORTANT]
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique RTC à la stratégie utilisateur de succursale et d’affecter des itinéraires distincts à chacun d’entre eux. Le premier itinéraire, ou principal, dirigerait les appels vers la passerelle associée à l’appareil de branchement (SBA) ou au serveur de succursales survivant. le deuxième, ou la sauvegarde, route dirigerait les appels vers la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires affectés au premier enregistrement d’utilisation RTC avant d’essayer le deuxième enregistrement.

Pour garantir que les appels entrants vers les utilisateurs du site de filiale seront indisponibles lorsque la passerelle de succursale ou le composant Windows du site de l’appareil de succursale survivant est indisponible (qui se produit, par exemple, si l’appareil ou la succursale est survivant la passerelle a été mise en place pour la maintenance), créez un itinéraire de basculement sur la passerelle (ou travaillez avec votre fournisseur de numérotation directe) pour rediriger les appels entrants vers le pool d’inscriptions de sauvegarde sur le site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire traduit les numéros conformément à la passerelle RTC ou aux formats de numéro de téléphone acceptés de l’homologue. Pour plus d’informations sur la création d’un itinéraire de basculement, reportez-vous à [Configuring a Failover Route](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux appareils de succursales Survivables dans un site de succursale, vous pouvez créer un plan de numérotation de niveau site pour les deux, sauf si un plan de niveau de service distinct est nécessaire pour chacun d’eux.

> [!NOTE]
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite sur le nombre d’utilisateurs de sites de succursales, y compris les utilisateurs enregistrés auprès d’une unité de succursale Survivable.

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, reportez-vous à [création ou modification d’un plan de numérotation dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md) et [création de la stratégie de routage VoIP pour les utilisateurs de succursale](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) dans la documentation de déploiement.

#### <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lorsque vous préparez des plans de numérotation et des stratégies vocales pour les utilisateurs de sites de succursales, veillez à inclure les règles de normalisation et les règles de traduction qui correspondent aux chaînes et au format de nombre utilisés dans l’attribut msRTCSIP-Line (ou URI de ligne), de sorte que les appels Skype entreprise soient activés entre les utilisateurs du site de succursale et les utilisateurs du site central seront routés correctement, en particulier lorsque les appels doivent être redirigés sur le RTC, car la liaison réseau étendu n’est pas disponible. D’autres éléments sont à prendre en considération dans le cas des numéros composés incluant des numéros de poste, et pas seulement des numéros de téléphone.

Les règles de normalisation et de conversion qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec uniquement un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Cependant, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour convertir le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :

|**Nom de la règle**|**Description**|**Schéma de numéro**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Ne convertit pas les numéros à 5 chiffres  <br/> |^ (\d{5}) $  <br/> |$1  <br/> |10001 n’est pas converti  <br/> |

Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. Au cours d’une panne de réseau étendu, si un utilisateur de succursale appelle un utilisateur de site central uniquement en composant son extension, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone de l’utilisateur central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste de l’utilisateur au lieu d’un numéro de téléphone complet unique pour l’utilisateur, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de votre organisation à la place. . Par exemple :

|**Description**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Convertit les numéros à 5 chiffres sur le numéro de téléphone et l’extension d’un utilisateur  <br/> |^ (\d{5}) $  <br/> |+14255550123;poste=$1  <br/> |10001 devient +14255550123;ext=10001  <br/> |
|Convertit les numéros à 5 chiffres sur le numéro de téléphone de votre organisation et l’extension d’un utilisateur.  <br/> |^ (\d{5}) $  <br/> |+14255550100;poste=$1  <br/> |10001 devient +14255550100;ext=10001  <br/> |

Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de conversion sortante doit également supprimer le numéro de poste. Par exemple :

|**Description**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Supprime le poste des numéros de téléphone présentant un numéro de poste  <br/> |^\+(\d\*); EXT = (\d\*) $  <br/> |+$1  <br/> |+14255550123;ext=10001 devient +14255550123  <br/> |

Qu’il s’agisse d’une liaison WAN, si votre organisation n’a pas effectué de numéros configurés pour les utilisateurs individuels et que l’URI de ligne pour un utilisateur contient le numéro de téléphone de votre organisation et le numéro unique de l’utilisateur, vous devez configurer votre URI de la ligne de numéro de téléphone de l’organisation avec un numéro joignable par l’homologue ou la passerelle RTC sur le site de la succursale. Vous devez également configurer l’URI de la ligne de numéro de téléphone de votre organisation de manière à inclure sa propre extension unique pour le routage des appels vers ce numéro.

#### <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survivabilité de la messagerie vocale

En règle générale, la messagerie unifiée Exchange est uniquement installée sur un site central et non sur des sites de succursales. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de ligne pour le numéro de téléphone du standard automatique de messagerie unifiée qui fournit des messages vocaux pour les utilisateurs du site de succursale nécessite des considérations spéciales, en plus de la stratégie vocale, du plan de numérotation et des règles de normalisation applicables à ce message vocal souche.

Les appareils de branchement survivables (SBAs) et les serveurs de succursales survivables permettent une survie de la messagerie vocale aux utilisateurs de succursales en cas de panne du réseau étendu. En particulier, si vous utilisez un appareil de succursale ou un serveur de succursales survivant et que le réseau WAN devient indisponible, le serveur de succursale SBA ou survivant redirige les appels sans réponse sur le RTC vers la messagerie unifiée Exchange sur le site central. Avec un serveur de succursale SBA ou Survivable, les utilisateurs peuvent également récupérer les messages vocaux par le biais du RTC lors d’une panne du réseau étendu. Enfin, au cours d’une période de connexion WAN, l’unité de succursale survivant ou le serveur de succursales survivant met en file d’attente des notifications d’appel en absence, puis les télécharge sur le serveur de messagerie unifiée Exchange lorsque le WAN est restauré. Pour vous assurer que le reroutage de messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet (FQDN) du pool de site central et une entrée pour le nom de domaine complet du serveur Edge au fichier hosts du serveur de succursales survivant. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

- Un administrateur Microsoft Exchange doit configurer le standard automatique de messagerie unifiée (AA) Exchange pour accepter uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

- L’administrateur Skype entreprise Server doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone comme numéro de **standard automatique de messagerie unifiée Exchange** dans les paramètres de routage de la messagerie vocale de l’appareil ou du serveur de succursales.

- L’administrateur Skype entreprise Server devrait obtenir le numéro de téléphone d’accès de l’abonné à la messagerie unifiée Exchange et utiliser ce numéro en tant que numéro d' **accès d’abonné** dans les paramètres de routage de la messagerie vocale pour l’appareil de succursale Survivable ou le serveur de succursales survivant.

- L’administrateur Skype entreprise Server doit configurer la messagerie unifiée Exchange de sorte qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursales qui ont besoin d’accéder à la messagerie vocale lors d’une panne du réseau étendu.

- Lorsque le lien WAN n’est pas disponible, les appels vers les utilisateurs du site de succursale peuvent être routés vers la boîte aux lettres vocale de la messagerie unifiée Exchange de l’utilisateur, mais uniquement si la stratégie vocale appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et n’incluant pas de poste. souche.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

#### <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Le matériel et le logiciel requis sont intégrés à l’appareil de branchement survivant. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise sont situés uniquement dans des sites centraux, les utilisateurs de sites de succursales ne seront pas en mesure de s’y connecter en cas de panne du réseau étendu, et par conséquent, la découverte de Skype entreprise Server qui utilise l’enregistrement de ressources SRV (service (SRV) est en échec. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou d’une version de l’application de succursale Survivable qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez le fournisseur de votre appareil pour succursales survivant.

> [!NOTE]
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. L’unité de branchement Survivable authentifie les clients en utilisant un certificat spécial qu’il envoie au client en réponse à la demande de certificat du client lors de la tentative de signature.

Les clients Skype entreprise peuvent découvrir le serveur Skype entreprise à l’aide de l’option DHCP 120 (SIP Registrar). La configuration peut prendre l’une des deux formes suivantes :

- Configurez le serveur DHCP sur le site de succursale pour répondre aux requêtes 120 DHCP, qui renvoient le nom de domaine complet du Bureau d’enregistrement sur l’appareil de succursales survivant ou le serveur de succursales survivant.

- Activez le protocole DHCP de Skype entreprise Server. Lorsque cette option est activée, le Bureau d’enregistrement de Skype entreprise Server répond aux requêtes option 120 de DHCP. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Enfin, les utilisateurs du site de succursale doivent être configurés pour Enterprise Voice et approvisionnés avec un point de terminaison de communications unifié approprié.

#### <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

La configuration requise pour les serveurs de succursales Survivables est la même que celle d’un serveur frontal. Pour plus d’informations, reportez-vous à la rubrique [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Conditions requises pour les déploiements de sites de succursales Skype entreprise Server à grande échelle

Pour plus d’informations, reportez-vous à [Configuration requise pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) dans la documentation de planification.

### <a name="example-configuring-a-failover-route"></a>Exemple : configuration d’un itinéraire de basculement

 L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.

**Tableau 1. Stratégie utilisateur**

|**Stratégie de l’utilisateur**|**Utilisation téléphonique**|
|:-----|:-----|
|Default Calling Policy  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Redmond Local Policy  <br/> |RedmondLocal  <br/> |
|Dallas Calling Policy  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tableau 2. Itinéraires**


| **Nom de l’itinéraire**             | **Schéma de numéro** | **Utilisation téléphonique**         | **Jonction**                                 | **Passerelle**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond Local Route  <br/> | ^\+1 (425           | 206                     | 253) (\d{7}) $  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Dallas Local Route  <br/>  | ^\+1 (972           | 214                     | 469) (\d{7}) $  <br/>                       | Local  <br/>                                    |
| Universal Route  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Dallas Users Route  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.


