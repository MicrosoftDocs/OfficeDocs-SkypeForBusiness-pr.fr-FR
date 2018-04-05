---
title: Planification de la résilience de Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Découvrez comment prendre en charge la résilience vocale dans Skype pour Business Server Voix Entreprise, à des sites centraux et de succursales. Options de site de succursale incluent le déploiement Survivable Branch Appliances ou Survivable Branch Servers.
ms.openlocfilehash: 4303df46b7430ec8a7e3891baec7f9ff99d85480
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server-2015"></a>Planification de la résilience de Voix Entreprise dans Skype Entreprise Server 2015
 
Découvrez comment prendre en charge la résilience vocale dans Skype pour Business Server Voix Entreprise, à des sites centraux et de succursales. Options de site de succursale incluent le déploiement Survivable Branch Appliances ou Survivable Branch Servers.
  
La résilience vocale fait référence à la capacité des utilisateurs de continuer à effectuer et recevoir des appels si un site central que hôtes Skype pour Business Server devienne indisponible, que ce soit par un réseau étendu (WAN) défaillance ou une autre cause du réseau. Si un site central ne fonctionne pas, le service de voix en entreprise doit basculer vers un site de sauvegarde pour assurer la continuité du service. En cas de panne du réseau étendu, les appels de la succursale doivent être redirigés vers une passerelle RTC locale. Cette section traite de la planification pour la résistance des communications vocales en cas de panne du site central ou du réseau étendu.
  
## <a name="central-site-resiliency"></a>Résistance des sites centraux

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. Mise à jour des services d’urgence, l’accès aux services d’assistance, et la possibilité d’effectuer les tâches critiques de l’entreprise lorsqu’un site central est hors service est essentielle pour n’importe quelle solution de résilience de Voix Entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :
  
- Le basculement vocal doit être fourni.
    
- Les utilisateurs qui enregistrent généralement avec le pool frontal sur le site central doivent être en mesure d’inscrire par un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs DNS SRV enregistrements, dont chacun se résout en un pool du directeur ou Front-End dans chacun de vos sites central. Vous pouvez ajuster la priorité et le poids des enregistrements SRV afin que les utilisateurs qui sont pris en charge par ce site central du pool de directeurs et de Front-End correspondant à celles des autres enregistrements SRV.
    
- Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.
    
Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.
  
### <a name="architecture-and-topology"></a>Architecture et topologie

Planification de la résilience vocale dans un site central nécessite une connaissance de base du rôle central joué par le Skype de registraire de serveur d’entreprise en autorisant le basculement de la voix. Le Skype pour Business serveur Registrar est un service qui permet l’authentification et l’enregistrement du client et fournit des services de routage. Il s’exécute sur tous les serveur Standard Edition server, serveur frontal, directeur ou Survivable Branch Appliance. Un pool de Registrar se compose de Registre des Services en cours d’exécution sur le pool frontal et résidant sur le même site. Un Skype pour client d’entreprise découvre le pool frontal via le mécanisme de découverte suivant : 
  
1. Enregistrement DNS SRV
    
2. Service Web de découverte automatique 
    
3. Option DHCP 120
    
Après que le Skype pour client d’entreprise se connecte au pool frontal, il est dirigé par l’équilibreur de charge à l’un des serveurs frontaux dans le pool. Ce serveur frontal, redirige à son tour, le client à un organisme d’enregistrement par défaut dans le pool.
  
Chaque utilisateur activé pour la Voix Entreprise est affecté à un pool particulier greffier, qui devient la plage de valeurs de Registre primaire de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’y a aucune limite sur le nombre d’utilisateurs de site de succursale, y compris les utilisateurs enregistrés avec un Survivable Branch Appliance.
  
Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide de paramètres de permanence de générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.
  
Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :
  
1. Un client découvre Skype pour Business Server via les enregistrements DNS SRV. Dans Skype pour Business Server, les enregistrements SRV DNS peuvent être configurés pour renvoyer plus d’un nom de domaine complet pour la requête DNS SRV. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool de directeur dans un des emplacements est disponible, le client peut se connecter au premier tronçon Skype pour Business Server.
    
    > [!NOTE]
    > Utilisation d’un pool de directeur est facultatif. Un pool frontal peut être utilisé à la place. 
  
2. Le pool de directeur informe le Skype pour client Business pool greffier principal de l’utilisateur et le pool de sauvegarde Registrar.
    
3. Le Skype pour client d’entreprise tente de se connecter tout d’abord pool greffier principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool de Registre principal est indisponible, le Skype pour client d’entreprise tente de se connecter au pool de sauvegarde Registrar. Si le pool de sauvegarde greffier est disponible et qu’il a déterminé que le pool de Registre de l’utilisateur principal est indisponible (par détection d’un manque de pulsation pendant un intervalle spécifié de basculement) le pool de sauvegarde Registre accepte l’inscription de l’utilisateur. Quand le serveur d’inscriptions de sauvegarde détecte que le serveur d’inscriptions principal est de nouveau disponible, le pool de serveurs d’inscriptions de sauvegarde redirige les clients de basculement vers leur pool principal.
    
### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :
  
- Les sites où se trouvent les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.
    
- Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.
    
- La charge de chaque pool de serveurs d’inscriptions doit être équilibrée via l’équilibrage de la charge DNS, l’équilibrage de la charge matérielle ou les deux. Pour plus d’informations sur la planification de votre configuration de l’équilibrage de charge, voir [charger les exigences pour Skype pour les entreprises](../../plan-your-deployment/network-requirements/load-balancing.md).
    
- Chaque utilisateur doit être affecté à un pool de Registrar principal en utilisant soit le Skype pour l’applet de commande **set-CsUser** Business Server Management Shell ou le Skype pour le panneau de configuration de Business Server.
    
- Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central. 
    
- Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde après 300 secondes. Vous pouvez modifier cet intervalle pour le Générateur de topologies serveur Business à l’aide de la Skype.
    
- Configurez un itinéraire de basculement. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.
    
- Si le site central contenus à votre serveur d’administration principal et le site est probablement hors service pendant une longue période, vous devrez réinstaller vos outils de gestion sur le site de sauvegarde ; dans le cas contraire, vous ne pourrez pas modifier les paramètres de gestion.
    
### <a name="dependencies"></a>Dépendances

Skype pour Business Server repose sur les composants d’infrastructure et de logiciels suivants afin de garantir la résilience vocale :
  
|**Composant** <br/> |**Fonction** <br/> |
|:-----|:-----|
|DNS  <br/> |Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client  <br/> |
|Exchange et services web Exchange (EWS)  <br/> |Stockage des contacts ; données de calendrier  <br/> |
|Messagerie unifiée Exchange et services web Exchange  <br/> |Journaux des appels, liste des messages vocaux, messagerie vocale  <br/> |
|Options DHCP 120  <br/> |Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour ce faire, un serveur DHCP doit être configuré soit Skype pour Business serveur DHCP doit être activé.  <br/> |
   
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
    
  - Configurer de messagerie unifiée Exchange à distance plan de chaque utilisateur pour inclure des serveurs de messagerie unifiée Exchange sur le site central et le site de sauvegarde, mais désigner les serveurs de messagerie unifiée Exchange sauvegarde comme étant désactivés. Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs de messagerie unifiée Exchange sur le site de sauvegarde comme activé.
    
    Si aucune de ces solutions n’est possible, Exchange UM est alors disponible dans le cas du site central n’est plus disponible.
    
- Conférence de tout type
    
    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, d’autres utilisateurs ne peuvent pas participer à des conférences qui sont hébergés sur le pool principal de l’utilisateur concerné.
    
Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :
  
- Standard automatique de conférence
    
- Routage basé sur la présence et DND
    
- Mise à jour des paramètres de transfert d’appel
    
- Service Response Group et parcage d’appel
    
- Provisionnement des nouveaux téléphones et clients
    
- Recherche web du carnet d’adresses
    
## <a name="branch-site-resiliency"></a>Résistance des sites de succursale

Si vous souhaitez fournir la résilience de site de la succursale, c'est-à-dire, service de Voix Entreprise de haute disponibilité, vous disposez de trois options pour le faire :
  
- Survivable Branch Appliance
    
- Serveur SBS
    
- Un Skype complète pour le déploiement de serveur d’entreprise sur le site de la succursale 
    
Ce guide vous aidera à choisir la solution de résistance la plus adaptée à votre organisation et, en fonction de votre choix, la solution de connectivité RTC à utiliser. Il vous aidera également à préparer le déploiement de la solution choisie en décrivant les conditions préalables et les autres éléments à prendre en compte pour la planification.
  
### <a name="branch-site-resiliency-features"></a>Fonctionnalités de résistance pour sites de succursale

Si vous fournissez la résilience de site de la succursale, en cas d’échec de la connexion de réseau étendu d’un site de succursale à un site central ou si le site central est inaccessible, les fonctionnalités vocales suivantes devraient continuer à être disponibles :
  
- Appels RTC entrants et sortants
    
- Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents
    
- Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert
    
- Messagerie instantanée entre deux utilisateurs
    
- Transfert, d’appel simultané de sonnerie de points de terminaison et délégation de l’appel de services d’appel d’équipe, mais uniquement si la personne qui a délégué et délégué (par exemple, un responsable et l’administrateur) ou tous les membres de l’équipe, qui sont configurées sur le même site
    
- Enregistrements des détails des appels (CDR)
    
- Conférence rendez-vous par réseau téléphonique commuté (RTC) avec standard automatique de conférence
    
- Fonctionnalités de messagerie vocale si vous configurez les paramètres de réacheminement de la messagerie vocale.
    
- Authentification et autorisations des utilisateurs
    
Les fonctionnalités suivantes est disponibles uniquement si votre solution de résilience est un Skype à grande échelle pour le déploiement de serveur d’entreprise sur le site de la succursale :
  
- Messagerie instantanée, conférence A/V et web
    
- Routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)
    
- Mise à jour des paramètres de transfert d’appel
    
- Application de groupe de réponse et l’application de parc d’appel
    
- Nouvelles mise en service des téléphones et des clients, mais uniquement si les Services de domaine Active Directory est présent sur le site de la succursale.
    
- Enhanced 9-1-1 (E9-1-1)
    
    Si E9-1-1 est déployé et la jonction SIP sur le site central n’est pas disponible car la liaison réseau étendu est hors service, le programme Survivable Branch Appliance acheminera E9-1-1 des appels à la passerelle de succursale locale. Pour activer cette fonctionnalité, les stratégies de voix de leur site de la succursale doivent acheminer les appels vers la passerelle locale en cas de défaillance du réseau étendu.
    
> [!NOTE]
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Utilisateurs qui sont hébergés dans un SBA configurations ne sera pas en mesure d’envoyer IMs ou voir présence avec les contacts XMPP. 
  
### <a name="branch-site-resiliency-solutions"></a>Solutions de résistance de sites de succursale

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. En particulier, si vous perdez la connexion vers le site central, les utilisateurs de site de succursale continuera à avoir de Voix Entreprise service et la messagerie vocale (si vous configurez les paramètres de redirection de la messagerie vocale). Cependant, pour les sites comportant moins de 25 utilisateurs, une solution de résistance peut ne pas être assez rentable. 
  
Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau ci-dessous peut vous aider à déterminer l’option appropriée.
  
|**Si vous...**|**Nous vous conseillons d’utiliser un...**|
|:-----|:-----|
|Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’une prise en charge d’administration locale.  <br/> |Survivable Branch Appliance  <br/> Le Survivable Branch Appliance est un serveur lame de standard de l’industrie avec un Skype de registraire de serveur d’entreprise et serveur de médiation en cours d’exécution sur Windows Server 2008 R2. Le Survivable Branch Appliance contient également une passerelle de réseau téléphonique public commuté. Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA) assurent une connexion PSTN continue en cas de panne du réseau étendu, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.  <br/> Pour plus d’informations sur Survivable Branch Appliances, reportez-vous à la section « Survivable Branch Appliance détails », plus loin dans cette rubrique.  <br/> **Remarque :** Si vous décidez d’utiliser également un SIP trunk avec votre Survivable Branch Appliance, contactez votre fournisseur de Survivable Branch Appliance pour obtenir des informations sur les fournisseur de services est plus adapté à votre organisation. <br/> |
|L’hôte entre 1000 et 2000 utilisateurs à votre site de la succursale, ne disposent pas d’une connexion WAN robuste et ont reçu une formation Skype pour les administrateurs de serveur d’entreprise disponibles  <br/> |Serveur Survivable Branch Server ou deux Survivable Branch Appliances.  <br/> Le serveur Survivable Branch Server est un serveur de Windows répondant aux exigences de matériel spécifié et qui a Skype pour Business serveur Registrar et médiation du logiciel serveur est installé. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.  <br/> Pour plus d’informations sur les serveurs de succursale Survivable, reportez-vous à la section « Survivable Branch Server détails », plus loin dans cette rubrique.  <br/> |
|Si vous avez besoin des fonctionnalités de conférence et la présence de plus de voix propose pour un maximum de 5 000 utilisateurs et ont reçu une formation Skype pour les administrateurs de serveur d’entreprise disponibles  <br/> |Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.  <br/> Un Skype à grande échelle pour le déploiement de Business Server fournit une connexion TLS continue et de présence robuste et de conférence en cas de défaillance du réseau étendu.  <br/> |
   
#### <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.
  
**Options de résilience de site de succursale**

![Options de résilience de filiale vocale](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)
  
#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

Le Skype pour Business serveur Survivable Branch Appliance inclut les composants suivants :
  
- serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs et routage des appels ;
    
- serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;
    
- passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du réseau étendu ;
    
- SQL Server Express pour le stockage local des données d’utilisateur.
    
Le Survivable Branch Appliance inclut également les trunks RTPC, ports analogiques et une carte Ethernet. 
  
Si la connexion de réseau étendu du site de la succursale vers un site central n’est plus disponible, les utilisateurs de la branche interne continuer à être inscrit dans le Registre de solution matérielle-logicielle Survivable Branch et obtenir un service vocal sans interruption en utilisant la connexion Survivable Branch Appliance vers le RTC. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison de réseau étendu vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion de réseau étendu redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Le basculement vers le programme Survivable Branch Appliance ni le rétablissement de service nécessite la présence d’un administrateur.
  
Skype pour Business Server prend en charge jusqu'à deux Survivable Branch Appliance à un site de la succursale. 
  
#### <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Le Survivable Branch Appliance est fabriqué par les fabricants en partenariat avec Microsoft et déployé pour leur compte par les revendeurs à valeur ajoutée. Ce déploiement doit avoir lieu qu’une fois Skype pour Business Server a été déployé sur le site central, une connexion WAN vers le site de la succursale est en place et les utilisateurs de site de succursale sont activés pour les Voix Entreprise.
  
Pour plus d’informations sur ces étapes, consultez [déploiement d’un serveur ou un serveur Survivable Branch Appliance](http://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) dans la documentation de déploiement.
  
|**Phase de**|**Étapes**|**Droits de l’utilisateur**|
|:-----|:-----|:-----|
|Configurer les Services de domaine Active Directory pour le Survivable Branch Appliance  <br/> |**Sur le site central :** <br/>  Créer un compte d’utilisateur de domaine (ou l’identité de l’entreprise) pour le technicien qui va installer et activer le Survivable Branch Appliance sur le site de la succursale. <br/>  Créer un compte d’ordinateur (avec le nom de domaine pleinement qualifié applicable (FQDN)) pour Survivable Branch Appliance dans les Services de domaine Active Directory. <br/>  Dans le Générateur de topologies, créer et publier le Survivable Branch Appliance. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. Le Survivable Branch Appliance doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le Générateur de topologies.  <br/> |
|Installez et activez le Survivable Branch Appliance.  <br/> |**Sur le site de succursale :** <br/>  Connectez le Survivable Branch Appliance à un port Ethernet et d’un port de réseau RTPC. <br/>  Démarrez le programme Survivable Branch Appliance. <br/>  Joindre le Survivable Branch Appliance au domaine, en utilisant le compte d’utilisateur de domaine créé pour le programme Survivable Branch Appliance sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur. <br/>  Configurer le Survivable Branch Appliance à l’aide de l’interface utilisateur OEM. <br/>  Testez la connectivité PSTN. <br/> |Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.  <br/> |
   
#### <a name="survivable-branch-server-details"></a>Serveur Survivable Branch Server en détail

Dans le Générateur de topologie de créer le site de la succursale, ajoutez le serveur Survivable Branch Server à ce site et exécutez le Skype pour l’Assistant de déploiement de Business Server sur l’ordinateur où vous souhaitez installer le rôle.
  
### <a name="branch-site-resiliency-requirements"></a>Configuration requise pour la résistance des sites de succursale

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.
  
#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparer les utilisateurs pour la résilience de site de la succursale en définissant leur pool de Registre que la solution matérielle-logicielle de branche Survivable (SBA) ou un serveur Survivable Branch Server.
  
#### <a name="registrar-assignments-for-branch-users"></a>Affectations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale choisie, vous devez affecter un serveur d’inscriptions principal à chaque utilisateur. Les utilisateurs de site de succursale doivent toujours enregistrer dans le Registre sur le site de la succursale, que si celui-ci se trouve dans le Survivable Branch Appliance, serveur Survivable Branch Server ou Skype autonome pour Business Server Standard ou Enterprise Edition serveur. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si le programme Survivable Branch Appliance n’est pas disponible, c’est comment les clients de site de succursale détectera automatiquement le Registre de sauvegarde.
  
Si un site de la succursale ne dispose pas d’un serveur DNS, il existe deux méthodes différentes pour configurer la découverte du serveur Survivable Branch Server ou Survivable Branch Appliance :
  
- Configurez l’option DHCP 120 sur un serveur de protocole de Configuration d’hôte dynamique (DHCP) du site de la succursale pour pointer vers le nom de domaine pleinement qualifié (FQDN) de le Survivable Branch Appliance ou serveur Survivable Branch Server.
    
- Configurer le Survivable Branch Appliance ou le serveur Survivable Branch Server pour répondre aux requêtes de 120 de DHCP.
    
#### <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau utilisateur pour les utilisateurs d’un site de succursale. Cette stratégie doit inclure un itinéraire principal qui utilise la passerelle de serveur Survivable Branch Appliance ou une branche et un ou plusieurs itinéraires de sauvegarde qui utilisent une ligne avec une passerelle de réseau téléphonique public commuté sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire alternatif faisant appel à une ou plusieurs passerelles de site central est utilisé à la place. De cette façon, même où un utilisateur est inscrit, sur le site de la succursale Registrar ou le pool de sauvegarde inscription sur le site central, la stratégie d’utilisateur VoIP est toujours en vigueur. Il est primordial de tenir compte de ce point pour les scénarios de basculement. Par exemple, si vous devez renommer le Survivable Branch Appliance ou reconfigurer le Survivable Branch Appliance pour se connecter à une pool d’inscription sur le site central de sauvegarde, vous devez déplacer les utilisateurs de site de succursale vers le site central pour la durée. (Pour plus d’informations sur la modification du nom ou de reconfigurer un Survivable Branch Appliance, consultez [annexe b : un Survivable Branch Appliance de gestion](http://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) dans la documentation de déploiement.) Si ces utilisateurs n’ont pas les stratégies au niveau utilisateur VoIP ou les plans d’accès de niveau utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies de VoIP au niveau du site et au niveau du site distant plans du site central s’appliquent aux utilisateurs par défaut, au lieu de site de la succursale au niveau du site VoIP plans d’appel et les stratégies. Dans ce scénario, leurs appels échoueront, à moins que les stratégies VoIP et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde puissent également s’appliquer aux utilisateurs du site de succursale. Par exemple, si les utilisateurs d’un site de succursale basé au Japon sont déplacés sur un site central situé à Redmond, il est probable qu’un plan de numérotation dont les règles de normalisation ajoutent le préfixe +1425 à tous les appels à 7 chiffres ne traduiront pas correctement les appels de ces utilisateurs.
  
> [!IMPORTANT]
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique RTC à la stratégie utilisateur de succursale et d’affecter des itinéraires distincts à chacun d’entre eux. La première ligne ou principal, itinéraire dirige les appels à la passerelle associées à la solution matérielle-logicielle de branche Survivable (SBA) ou le serveur de la succursale ; la seconde, ou la sauvegarde, itinéraire dirige les appels à la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires affectés au premier enregistrement d’utilisation RTC avant d’essayer le deuxième enregistrement. 
  
Afin de garantir que les appels entrants pour les utilisateurs de site de succursale n’atteindra les utilisateurs lorsque la passerelle de la branche ou le composant Windows du site Survivable Branch Appliance n’est pas disponible (qui se produit, par exemple, si le Survivable Branch Appliance ou une succursale passerelle ont été vers le bas pour la maintenance), la création d’une gamme de basculement de la passerelle (ou travail auprès de votre fournisseur de numérotation directe vers l’intérieur (DID)) pour rediriger les appels entrants vers le pool de sauvegarde greffier du site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. N’oubliez pas que la gamme se traduit par des numéros pour se conformer à la passerelle RTC ou des formats de nombre de téléphone accepté l’autre homologue trunk. Pour plus d’informations sur la création d’un itinéraire de basculement, consultez [configuration d’un itinéraire de basculement](http://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux Survivable Branch Appliances à un site de la succursale, vous pouvez créer un plan de numérotation d’au niveau du site dans les deux cas, sauf si un plan de niveau de service distinct pour chaque est nécessaire.
  
> [!NOTE]
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’y a aucune limite sur le nombre d’utilisateurs de site de succursale, y compris les utilisateurs enregistrés avec un Survivable Branch Appliance. 
  
Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md) et [créer la stratégie de routage de VoIP pour les utilisateurs de la succursale](http://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) dans la documentation de déploiement.
  
#### <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lors de la préparation des plans de numérotation et les stratégies de voix pour les utilisateurs de site de succursale, veillez à inclure des règles de traduction qui correspondent aux chaînes et format de nombre utilisé dans la msRTCSIP-line (ou URI de ligne) et de règles de normalisation d’attribut, afin que l’activé de Skype pour les appels de l’entreprise entre les utilisateurs de site de succursale et le site central les utilisateurs doivent être routés correctement, en particulier lorsque les appels doivent être redirigés sur RTC, car la liaison réseau étendu n’est pas disponible. D’autres éléments sont à prendre en considération dans le cas des numéros composés incluant des numéros de poste, et pas seulement des numéros de téléphone.
  
Les règles de normalisation et de conversion qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.
  
Si votre organisation ne dispose pas de numéros de téléphone à distance vers l’intérieur directe (DID) configurés pour les utilisateurs individuels et l’URI de la ligne de chaque utilisateur est configuré avec un numéro d’extension, les utilisateurs internes peuvent appeler un autre en appelant un numéro d’extension. Cependant, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.
  
Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour convertir le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :
  
|**Nom de la règle**|**Description**|**Schéma de numéro**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Ne convertit pas les numéros à 5 chiffres  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 n’est pas converti  <br/> |
   
Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. Durant une panne de réseau étendue, si un utilisateur de site de succursale appelle un utilisateur du site central uniquement par la numérotation d’extension de l’utilisateur site central, doit avoir une règle de traduction sortant qui ajoute le numéro de téléphone de l’utilisateur site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro d’extension unique de l’utilisateur au lieu d’un numéro de téléphone complet qui est unique à l’utilisateur, vous devez avoir une règle de traduction sortant qui ajoute à la place de numéro de téléphone de votre organisation . Par exemple :
  
|**Description**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Convertit les nombres de 5 chiffres pour le numéro de téléphone et d’extension d’un utilisateur  <br/> |^(\d{5})$  <br/> |+14255550123;poste=$1  <br/> |10001 devient +14255550123;ext=10001  <br/> |
|Convertit les nombres de 5 chiffres pour le numéro de téléphone de votre organisation et l’extension de l’utilisateur  <br/> |^(\d{5})$  <br/> |+14255550100;poste=$1  <br/> |10001 devient +14255550100;ext=10001  <br/> |
   
Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de conversion sortante doit également supprimer le numéro de poste. Par exemple :
  
|**Description**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Supprime le poste des numéros de téléphone présentant un numéro de poste  <br/> |^\+(\d\*) ; ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 devient +14255550123  <br/> |
   
Ou non un lien de réseau étendu est disponible, si votre organisation n’a pas a des numéros configurées pour les utilisateurs individuels et l’URI de la ligne d’un utilisateur contient le numéro de téléphone de votre société et le numéro d’extension unique de l’utilisateur, puis vous devez configurer votre téléphone numéro ligne l’organisation URI avec un nombre qui est accessible par l’homologue du tronc ou passerelle PSTN au site de la succursale. Vous devez également configurer la ligne de numéro de téléphone de votre organisation URI à inclure son propre extension unique pour les appels à être acheminés vers ce numéro.
  
#### <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survivabilité de la messagerie vocale

Exchange la messagerie unifiée (MU) est généralement installé uniquement sur un site central et pas sur les sites des succursales. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de la ligne pour le numéro de téléphone Standard automatique Exchange UM qui fournit la messagerie vocale pour les utilisateurs de site de succursale nécessite des considérations particulières, en plus de la stratégie voice, composer le plan et les règles de normalisation applicables à la messagerie vocale nombre.
  
Survivable Branch Appliances (SBA) et Survivable Branch serveurs fournissent la survivabilité de messagerie vocale pour les utilisateurs de la succursale suite à une panne de réseau étendue. En particulier, si vous utilisez un Survivable Branch Appliance ou serveur Survivable Branch Server et le réseau étendu n’est pas disponible, les SBA ou un serveur Survivable Branch Server redirige les appels en attente sur le réseau RTPC pour la messagerie unifiée Exchange sur le site central. Un SBA ou un serveur Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le réseau RTPC suite à une panne de réseau étendue. Enfin, suite à une panne de réseau étendue la Survivable Branch Appliance ou le serveur Survivable Branch Server files d’attente de notifications d’appels manqués et les transfère au serveur de messagerie unifiée Exchange lorsque le réseau étendu est restauré. Pour vous assurer que le réacheminement de messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet du pool site central et une entrée pour le FQDN du serveur Edge au fichier hosts sur le serveur Survivable Branch Server. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.
  
Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées : 
  
- Un administrateur de Microsoft Exchange doit configurer Exchange UM Standard automatique (sa) pour accepter uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.
    
- Le Skype pour l’administrateur du serveur de l’entreprise doit prendre le numéro AA et utiliser ce numéro de téléphone comme numéro de **exchange auto surveillance du service de messagerie unifiée** dans le reroutage des paramètres pour le serveur de la succursale ou de Survivable Branch Appliance de la messagerie vocale.
    
- Le Skype pour l’administrateur du serveur de l’entreprise doit obtenir de numéro de téléphone d’accès de l’abonné de messagerie unifiée Exchange et utiliser ce nombre comme le numéro **d’accès abonné** dans la messagerie vocale reroutage des paramètres pour le Survivable Branch Appliance ou le serveur Survivable Branch Server .
    
- Le Skype pour l’administrateur du serveur de l’entreprise doit configurer Exchange UM pour ce plan de numérotation qu’une seule est associé à tous les utilisateurs de succursales qui ont besoin d’accéder à la messagerie vocale pendant une panne du réseau étendue.
    
- Lors de la liaison réseau étendu n’est pas disponible, les appels aux utilisateurs de site de succursale peut être routé vers la boîte aux lettres de l’utilisateur Exchange la messagerie unifiée (MU) voix, mais uniquement si la stratégie voice appliqué à l’appel spécifie un numéro de téléphone de messagerie vocale qui est unique et ne comprend pas une extension nombre.
    
#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.
  
#### <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Matériel et logiciel nécessaires est intégrée dans le programme Survivable Branch Appliance. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.
  
Si les serveurs DNS d’entreprise se trouvent uniquement dans les sites centraux, les utilisateurs de site de succursale ne pourront pas se connecter à leur suite à une panne de réseau étendue, et par conséquent Skype pour la découverte de serveur de l’entreprise qui utilise DNS SRV (enregistrement de ressource emplacement du service (SRV)) échoue. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou une version de Survivable Branch Appliance qui prend en charge les fonctionnalités de DNS. Pour plus d’informations, contactez votre fournisseur de Survivable Branch Appliance.
  
> [!NOTE]
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. Le Survivable Branch Appliance authentifie les clients à l’aide d’un certificat spécial qu’il envoie au client en réponse à une demande de certificat du client lorsqu’il se connecte. 
  
Skype pour les clients d’entreprise peut découvrir le Skype pour Business Server à l’aide de DHCP Option 120 (Option de Registre SIP). La configuration peut prendre l’une des deux formes suivantes :
  
- Configurer le serveur DHCP sur le site de la succursale pour répondre aux requêtes DHCP 120, qui renvoie le nom de domaine complet de l’agent d’enregistrement sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
- Activer Skype pour Business serveur DHCP. Lorsque cette option est activée, le Skype pour Business serveur Registrar répond à des requêtes DHCP Option 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.
    
De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).
  
Enfin, les utilisateurs de site de succursale doivent être configurés pour Voix Entreprise et mis en service avec un point de terminaison des communications unifiées approprié.
  
#### <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

La configuration requise pour les serveurs de succursale Survivable est les mêmes que la configuration requise pour un serveur frontal. Pour plus d’informations, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Configuration requise pour Skype à grande échelle pour les déploiements de Site de la succursale Business Server

Pour plus d’informations, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) dans la documentation de planification.
  
### <a name="example-configuring-a-failover-route"></a>Exemple : configuration d’un itinéraire de basculement

 L’exemple suivant montre comment un administrateur peut définir un itinéraire de basculement à utiliser en cas de maintenance ou d’indisponibilité de Dallas-GW1. Les tableaux suivants illustrent la modification de configuration requise.
  
**Le tableau 1. Stratégie de l’utilisateur**

|**Stratégie de l’utilisateur**|**Utilisation du téléphone**|
|:-----|:-----|
|Default Calling Policy  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Redmond Local Policy  <br/> |RedmondLocal  <br/> |
|Dallas Calling Policy  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |
   
**Le tableau 2. Itinéraires**

|**Nom de l’itinéraire**|**Schéma de numéro**|**Utilisation du téléphone**|**Trunk**|**Passerelle**|
|:-----|:-----|:-----|:-----|:-----|
|Redmond Local Route  <br/> |^\+1 (425|206|253)(\d{7})$  <br/> |Local  <br/> RedmondLocal  <br/> |Trunk1  <br/> Trunk2  <br/> |Red-GW1  <br/> Red-GW2  <br/> |
|Dallas Local Route  <br/> |^\+1 (972|214|469)(\d{7})$  <br/> |Local  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
|Universal Route  <br/> |^\+?(\d\*)$  <br/> |GlobalPSTNHopoff  <br/> |Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> |Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
|Dallas Users Route  <br/> |^\+?(\d\*)$  <br/> |DallasUsers  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
   
Dans le tableau 1, une utilisation téléphonique GlobalPSTNHopoff est ajoutée après l’utilisation téléphonique DallasUsers dans la stratégie Dallas Calling Policy. Cela permet aux appels dotés de la stratégie Dallas Calling Policy d’utiliser des itinéraires configurés pour l’utilisation téléphonique GlobalPSTNHopoff, lorsqu’aucun itinéraire n’est disponible pour l’utilisation téléphonique DallasUsers.
  

