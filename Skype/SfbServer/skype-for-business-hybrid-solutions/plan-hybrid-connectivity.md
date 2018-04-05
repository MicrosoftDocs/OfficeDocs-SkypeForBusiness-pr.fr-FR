---
title: Planification de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier la connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne. La première étape du déploiement de nombreuses solutions hybrides Skype Entreprise consiste à configurer une connectivité hybride.'
ms.openlocfilehash: 28ddfa42f11ad76cb353200cf00a4ca4d05a9da0
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Planification de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online
 
**Résumé :** consultez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.  La première étape du déploiement de nombreuses solutions hybrides Skype Entreprise consiste à configurer une connectivité hybride.
  
Cette rubrique fournit une vue d’ensemble et décrit l’infrastructure et vous devrez configurer la connectivité hybride entre votre configuration requise sur site Skype pour le déploiement du serveur de l’entreprise, avec des utilisateurs qui ont été créés dans vos locaux Active Directory — et Skype pour les entreprises en ligne. 
  
Cette rubrique contient les sections suivantes :
  
- [Vue d’ensemble](plan-hybrid-connectivity.md#BKMK_Overview)
    
- [Exigences de l’infrastructure](plan-hybrid-connectivity.md#BKMK_Infrastructure)
    
- [Prise en charge de plusieurs forêt](plan-hybrid-connectivity.md#BKMK_MultiForest)
    
- [Coexistence d’Exchange](plan-hybrid-connectivity.md#BKMK_Exchange)
    
- [Informations d’identification de l’administrateur](plan-hybrid-connectivity.md#BKMK_Credentials)
    
- [Skype pour Business Online PowerShell](plan-hybrid-connectivity.md#BKMK_PowerShell)
    
- [Skype pour la prise en charge de client entreprise](plan-hybrid-connectivity.md#BKMK_ClientSupport)
    
- [Exigences en matière de topologie](plan-hybrid-connectivity.md#BKMK_Topology)
    
- [Exigences en matière de fédération répertorie les autorisés/bloqués](plan-hybrid-connectivity.md#BKMK_Federation)
    
- [Paramètres DNS](plan-hybrid-connectivity.md#BKMK_DNS)
    
- [Considérations relatives au pare-feu](plan-hybrid-connectivity.md#BKMK_Firewall)
    
- [Exigences de port et de protocole](plan-hybrid-connectivity.md#BKMK_Ports)
    
- [Comptes d’utilisateurs et de données](plan-hybrid-connectivity.md#BKMK_UserAccounts)
    
- [Fonctionnalités des stratégies utilisateur](plan-hybrid-connectivity.md#BKMK_UserPolicies)
    
Après avoir lu cette rubrique et êtes prêt à déployer, voir [déployer une connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Les rubriques sur le déploiement fournissent des instructions détaillées sur la configuration d'une connectivité hybride entre votre déploiement sur site et Skype Entreprise Online.
  
(Pour plus d’informations sur la configuration de votre déploiement de Lync Server 2010 pour hybride ou de Lync Server 2013, voir [hybride de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=617360).)
  
## <a name="overview"></a>Vue d’ensemble
<a name="BKMK_Overview"> </a>

Les solutions hybrides permettent de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. La présente rubrique traite de la connectivité hybride entre un déploiement sur site de Skype Entreprise Server et Skype Entreprise Online. Cette connectivité vous permet d'héberger des utilisateurs sur site et d'autres en ligne.
  
Ce type de déploiement est parfois appelé « domaine de fractionnement » — les utilisateurs la signification d’un domaine, par exemple, contoso.com, sont réparties entre l’utilisation de Skype pour Business Server dans les locaux et Skype pour entreprise en ligne comme suit :
  
- Les utilisateurs hébergés sur site interagissent avec des serveurs Skype Entreprise sur site.
    
- Les utilisateurs hébergés en ligne interagissent avec d'autres services en ligne de Skype Entreprise.
    
- Les utilisateurs des deux environnements peuvent collaborer les uns avec les autres à l'aide de la messagerie instantanée, la participation à des téléconférences, des appels VoIP, etc.
    
- Azure Active Directory Connect est utilisé pour synchroniser votre répertoire sur site avec Office 365.
    
Active Directory fait autorité, procédez donc comme indiqué ci-après pour permettre la détection entre les utilisateurs sur site et en ligne :
  
- Tous les utilisateurs doivent être créés dans Active Directory sur site en premier et ensuite synchronisées avec Active Directory Azure. 
    
- Si vos utilisateurs sont hébergés sur site pour Skype Entreprise, vous devez les activer pour Skype Entreprise sur site.
    
- Si vos utilisateurs sont hébergés sur site mais souhaitent utiliser certaines fonctionnalités en ligne, telles que la diffusion de réunion Skype, vous devez leur affecter une licence Skype Entreprise Online Plan 2.
    
- Si vos utilisateurs sont hébergés dans Skype Entreprise Online, lorsque leur compte est synchronisés avec Azure AD, vous devez leur affecter une licence Skype Entreprise Online Plan 2. 
    
- Une fois la licence Skype Entreprise Online affectée aux utilisateurs, vous devez les activer pour Skype Entreprise ou pour Voix Entreprise sur site. Pour plus d’informations, reportez-vous à la section [permettre aux utilisateurs de Voix Entreprise dans les locaux](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Pour plus d’informations sur la configuration requise de voix hybride, reportez-vous à la section [Planifier le système téléphonique dans Office 365 avec la connectivité RTPC dans Skype pour Business Server local](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).
    
Les sections qui suivent fournissent de plus amples informations sur la configuration Active Directory. Mais jetons d'abord un œil à la terminologie et aux acronymes utilisés dans les diagrammes ci-après et dans de nombreuses rubriques sur la connectivité hybride :
  
- PSTN : Réseau téléphonique commuté
    
- PBX : système téléphonique autocommutateur privé
    
- Système téléphonique : solution de système téléphonique Cloud PBX de Microsoft
    
- Trunk - ligne téléphonique qui relie le PBX à RTC — un tronc peut utiliser le protocole SIP (Session Initiation) — un protocole voix sur IP (VoIP), ou l’ancienne technologie de multiplexage à Division de temps (TDM) 
    
- SBC (Session Border Controller) : dispositif utilisée comme pare-feu et routeur sur des réseaux téléphoniques. Entre autres avantages, il fournit la sécurité, la connectivité, l'interoperabilité et la qualité des services. 
    
- Passerelle PSTN : dispositif utilisé comme routeur sur des réseaux téléphoniques et qui fournit les mêmes avantages qu'un dispositif SBC, excepté la sécurité et la NAT-T (Network Address Translation Traversal).
    
Le diagramme suivant illustre un Skype pour configuration hybride du « domaine de fractionnement » d’entreprise. les utilisateurs A et B sont hébergés en ligne mais sont détectables par les utilisateurs sur site ; les utilisateurs C et D sont hébergés sur site, mais sont détectables par les utilisateurs en ligne.
  
![Connectivité hybride SfB - domaine partagé](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)
  
Vous avez probablement déjà entendu l'expression « Voix hybride », qui fait référence aux tronçons voix sur site qui fournissent les fonctionnalités aux utilisateurs hébergés dans le cloud. La fonctionnalité Voix hybride permet la migration dans le cloud tout en conservant la configuration voix sur site. Si vous disposez déjà d'un déploiement Skype Entreprise Server, la première étape de l'activation de la fonctionnalité Voix hybride consiste à configurer un environnement de domaine partagé. 
  
Par exemple, supposons que votre société a un grand champ mobile prend en charge d’organisation nécessitant un minimum PBX vocal, mais complète téléphone intelligent utiliser. Vous pouvez choisir de migrer les utilisateurs vers le cloud pour bénéficier des avantages du système téléphonique Microsoft dans Office 365 (Cloud PBX). Si votre société dispose également d’un centre d’appels local important qui requiert les logiciels avancés et complexes de centre de contact dans le cadre de votre PBX sur place, vous pouvez choisir de laisser ces utilisateurs sur site. Les utilisateurs hébergés en ligne et sur site disposent d'une connectivité PSTN via votre déploiement sur site.
  
Le diagramme ci-dessous présente un déploiement du service vocal hybride de Skype Entreprise :
  
![Domaine partagé SfB avec Cloud PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
Pour plus d’informations sur la configuration d’une solution de voix hybride avec votre Skype pour le déploiement du serveur de l’entreprise, reportez-vous à la section [Planifier le système téléphonique dans Office 365 avec la connectivité RTPC dans Skype pour Business Server local](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md). 
  
Vous pouvez également configurer des déploiements hybride pour l’intégration à Exchange et SharePoint local, ou avec des applications de Microsoft Office 365, y compris Exchange Online et SharePoint Online. Vous pouvez également configurer une solution vocale hybride qui ne requiert pas le déploiement complet de Skype Entreprise Server en utilisant la version Cloud Connector. Pour plus d’informations sur tous les Skype pour les solutions hybride et de la planification de votre migration vers le nuage, consultez [Skype pour solutions d’entreprise hybride](skype-for-business-hybrid-solutions.md).
  
## <a name="infrastructure-requirements"></a>Conditions requises pour l'infrastructure
<a name="BKMK_Infrastructure"> </a>

Pour implémenter et déployer une connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online, vous devez configurer les éléments suivants dans votre environnement :
  
- Un seul déploiement local de Skype pour Business Server ou Lync Server est déployé dans une topologie prise en charge. Dans cette rubrique, reportez-vous à la section [Configuration requise de topologie](plan-hybrid-connectivity.md#BKMK_Topology) .
    
- Un client Microsoft Office 365 avec Skype pour Business Online activé. 
    
    > [!NOTE]
    > Vous ne pouvez utiliser qu'un seul client pour une configuration hybride avec votre déploiement local. 
  
- Skype pour les outils d’administration de Business Server 2015. (Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration de Lync Server 2013. Pour plus d’informations, consultez [hybride de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=617360).)
    
- Azure Active Directory Connect pour synchroniser votre répertoire sur site avec Office 365. Pour plus d’informations, consultez [Connexion de Active Directory avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
    
    Pour prendre en charge l'authentification unique Office 365 afin que les utilisateurs puissent utiliser les mêmes informations d'identification de connexion sur site, vous pouvez utiliser les fonctionnalités de synchronisation des mots de passe Azure Active Directory (AAD) Connect. Vous pouvez également utiliser AD FS (Active Directory Federation Services) avec l’authentification unique pour Office 365. 
    
- Fédération activée entre votre déploiement Skype Entreprise sur site et votre client Office 365. La fédération permet aux utilisateurs dans votre déploiement sur site de communiquer avec les utilisateurs d’Office 365 dans votre organisation. Pour plus d’informations, voir [Fédération de configurer avec Skype pour l’activité en ligne](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).
    
- Espace d'adressage SIP (Session Initiation Protocol) partagé et activé. Une adresse SIP est un identificateur unique pour chaque utilisateur d'un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie. Avant d’essayer de déplacer des utilisateurs sur site à Skype pour professionnels en ligne, vous aurez besoin configurer vos clients Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site. Pour plus d’informations, voir [Fédération de configurer avec Skype pour l’activité en ligne](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).
    
## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts
<a name="BKMK_MultiForest"> </a>

Les utilisateurs peuvent accéder aux fonctionnalités Skype Entreprise dans une autre forêt si les conditions suivantes sont réunies :
  
- Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise ; dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu'objets utilisateurs désactivés.
    
- La forêt hébergeant Skype Entreprise doit approuver la forêt contenant les utilisateurs.
    
Pour plus d’informations sur les scénarios hybride de plusieurs forêts, consultez [configurer un environnement à plusieurs forêts pour hybride Skype pour les entreprises](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="exchange-co-existence"></a>Coexistence avec Exchange
<a name="BKMK_Exchange"> </a>

Pour prendre en charge la coexistence avec Exchange, tenez compte des points suivants :
  
- La meilleure pratique consiste à déplacer la boîte aux lettres vers Exchange Online avant de déplacer Skype de l’utilisateur pour l’entreprise familiale.
    
- Les utilisateurs disposant de boîtes aux lettres sur site sont pris en charge avec les limites connues suivantes :
    
  - Connexion client : les utilisateurs devront peut-être se connecter deux fois au client Skype Entreprise.
    
  - Historique de conversation côté serveur, d’archivage, magasin de contacts unifiée, HighRes Photo nécessite Exchange 2013 ou version ultérieure, et vous devez activer OAuth serveur pour la communication serveur. Pour plus d’informations, consultez [authentification de serveur à gérer (OAuth) et les applications partenaires dans Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).
    
Pour plus d’informations sur la coexistence avec Exchange Server, y compris la prise en charge critères et les restrictions dans différentes combinaisons de locaux et en ligne, voir [fonctionnalité prise en charge](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) de [planifier l’intégration de Skype pour les entreprises et Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="administrator-credentials"></a>Informations d'identification de l'administrateur
<a name="BKMK_Credentials"> </a>

Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe pour le compte administrateur pour vos clients d’Office 365. Vous utiliserez également ces informations d’identification lorsque vous configurez Azure Active Directory pour la fédération, la synchronisation d’annuaire, l’ouverture de session unique et le déplacement des utilisateurs de Skype pour l’activité en ligne.
  
## <a name="skype-for-business-online-powershell"></a>Skype Entreprise Online PowerShell
<a name="BKMK_PowerShell"> </a>

Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer des Skype pour Business Online et leur Skype pour les comptes d’utilisateurs professionnels en ligne. Pour ce faire, vous devez d’abord télécharger et installer le Skype pour Module Business de connecteur en ligne à partir du Microsoft Download Center. Pour plus d’informations sur le téléchargement, l’installation et l’utilisation de la Skype pour Module de connecteur Business en ligne et pour plus d’informations sur l’utilisation de Windows PowerShell pour gérer Skype pour Business Online, reportez-vous à la section [de Windows PowerShell à l’aide de Skype pour les entreprises de gérer En ligne](https://technet.microsoft.com/library/dn362831.aspx). 
  
## <a name="skype-for-business-client-support"></a>Prise en charge du client Skype Entreprise
<a name="BKMK_ClientSupport"> </a>

Des différences existent dans les fonctionnalités prises en charge dans les clients, ainsi que dans les fonctionnalités disponibles dans des environnements locaux et en ligne. Les clients suivants sont pris en charge avec Skype pour Business Online dans un déploiement hybride :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- application Lync du Windows Store
    
- Lync Web App
    
- Lync Mobile
    
- Lync pour Mac 2011
    
- Système de chambre de Lync et Skype pour système de salle d’entreprise
    
- Lync Basic 2013
    
- Microsoft Surface Hub
    
Avant de vous décider où vous souhaitez particuliers de votre organisation, vous devez examiner la [comparaison des fonctionnalités client de bureau pour Skype pour l’entreprise](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) pour déterminer la prise en charge de client pour les différentes configurations de Skype pour Business Server. Voir aussi :
  
- [Plan pour les clients et périphériques](../plan-your-deployment/clients-and-devices/clients-and-devices.md)
    
- [Comparaison des fonctionnalités de client mobile pour Skype pour entreprise](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)
    
## <a name="topology-requirements"></a>Conditions requises pour la topologie
<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement pour hybride avec Skype pour professionnels en ligne, vous devez disposer d’une des topologies prises en charge suivantes :
  
- Un Skype pour le déploiement de Business Server 2015 avec tous les serveurs exécutant Skype pour Business Server 2015.
    
- Un déploiement de Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.
    
    Dans le cadre de la connectivité voix hybride, le serveur Edge désigné comme serveur Edge de fédération doit exécuté Skype Entreprise 2015 et requiert un serveur principal Skype Entreprise Server. Vous pouvez disposer d'un pool sans utilisateur. 
    
- Un déploiement de Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les dernières mises à jour cumulatives.
    
  - La fédération de serveur de transport Edge et le serveur du tronçon suivant à partir de la fédération de serveur de transport Edge doivent exécuter Lync Server 2010 avec les dernières mises à jour cumulatives.
    
  - Le Skype pour 2015 de serveur d’entreprise ou des outils d’administration de Lync Server 2013 doit être installé sur au moins un serveur ou station de gestion.
    
- Lync Server 2013 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :
    
  - Au moins un pool d'entreprise ou serveur Standard Edition  
    
  - Pool directeur associé à la fédération SIP, le cas échéant
    
  - Pool Edge associé à la fédération SIP
    
- Lync Server 2010 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :
    
  - Au moins un pool d'entreprise ou serveur Standard Edition  
    
  - Pool directeur associé à la fédération SIP, le cas échéant
    
  - Pool Edge associé à la fédération SIP pour le site
    
- Un déploiement de Lync Server 2010 et Lync Server 2013 mixte avec les rôles de serveur suivants au moins un site Lync Server 2013 en cours d’exécution :
    
  - Au moins un pool d'entreprise ou serveur Standard Edition dans le site
    
  - Pool directeur associé à la fédération SIP, si elle existe dans le site
    
  - Pool Edge associé à la fédération SIP pour le site
    
## <a name="federation-allowedblocked-lists-requirements"></a>Configuration requise pour les listes de fédération autorisées/bloquées
<a name="BKMK_Federation"> </a>

La liste de domaines autorisés inclut les domaines qui ont un nom de domaine pleinement qualifié de bord partenaires (FQDN) configuré. Ils sont parfois en tant que partenaires de fédération de partenaire autorisé serveurs ordirect. Vous devez être familiarisé avec la différence entre la fédération ouvert et fermé fédération, appelé liste de domaine de partenaire d’andallowed de découverte de partenaire, respectivement, dans les déploiements sur site.
  
La configuration ci-dessous est requise pour configurer un déploiement hybride :
  
- La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.
    
- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.
    
- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.
    
- Fédération doit être activée pour les communications externes pour les clients en ligne, qui est configuré à l’aide de la Skype pour le panneau de configuration en ligne professionnels.
    
## <a name="dns-settings"></a>Paramètres DNS
<a name="BKMK_DNS"> </a>

Lors de la création des enregistrements DNS pour les déploiements de hybride, tous les Skype pour les enregistrements de DNS externes doit pointer vers l’infrastructure sur site. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la [configuration DNS requise pour Skype pour Business Server 2015](../plan-your-deployment/network-requirements/dns.md).
  
En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau ci-dessous fonctionne dans votre déploiement local :
  
|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp. \<sipdomain.com\> pour toutes les prises en charge des domaines SIP résoudre les adresses IP externes de Edge d’accès  <br/> |Serveur(s) Edge  <br/> |Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.  <br/> Doit utiliser un nom DNS strict identique pour le domaine du nom d'utilisateur et pour l'enregistrement SRV.  <br/> |
|Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web  <br/> |Réseau d’entreprise interne connecté les ordinateurs des utilisateurs  <br/> |Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.   <br/> |
   
En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne.
  
## <a name="firewall-considerations"></a>Éléments à prendre en compte pour le pare-feu
<a name="BKMK_Firewall"> </a>

Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.
  
En fonction de l’emplacement de votre centre de données de Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions en fonction des noms de domaines génériques (par exemple, tout le trafic \*. outlook.com). Si le pare-feu de votre organisation ne gèrent pas les configurations de nom générique, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et ports spécifiés.
  
Pour plus d’informations, consultez [Office 365 URL et les plages d’adresses IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).
  
## <a name="port-and-protocol-requirements"></a>Configuration requise pour les ports et les protocoles
<a name="BKMK_Ports"> </a>

En plus de la configuration requise pour les ports pour les communications internes, vous devez également configurer les ports suivants pour activer la connectivité hybride :
  

|**Protocole**|**TCP ou UDP**|**Adresse IP source**|**Destination IP**|**Port source**|**Port de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Serveur Edge d’accès  <br/> |Office 365  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Serveur Edge d’accès  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|STUN  <br/> |TCP  <br/> |Edge A/V  <br/> |Office 365  <br/> |50000-59999  <br/> |443, 50000-59999  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Edge A/V  <br/> |443  <br/> |50000-59999  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |UDP  <br/> |Edge A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Edge A/V  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |
   
Pour plus d’informations sur les pare-feu de planification pour le serveur de transport Edge et de port, reportez-vous à la section [exigences environnementales de serveur de transport Edge dans Skype pour Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Voir aussi [configuration de Port et de protocole pour les serveurs](../plan-your-deployment/network-requirements/ports-and-protocols.md) et le [diagramme des charges de travail de protocole](http://go.microsoft.com/fwlink/p/?LinkId=550989).
  
## <a name="user-accounts-and-data"></a>Comptes et données utilisateur
<a name="BKMK_UserAccounts"> </a>

Dans un déploiement hybride, tout utilisateur que vous souhaitez en ligne d’accueil doit d’abord être créé lors du déploiement sur site, afin que le compte d’utilisateur est créé dans les Services de domaine Active Directory. Vous pouvez ensuite déplacer l’utilisateur à Skype pour professionnels en ligne, qui affichera une liste de contacts de l’utilisateur.
  
Lorsque vous synchronisez des comptes d’utilisateurs entre votre déploiement sur site et les clients en ligne à l’aide de DAS se connecter, vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs d’entreprise ou Lync dans votre organisation, même si les utilisateurs ne sont pas déplacés vers en ligne. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.
  
> [!IMPORTANT]
> Gestion de tous les utilisateurs, y compris les utilisateur se déplace entre les locaux et Skype pour Business Online, doivent être effectué à l’aide de la dernière version installée des outils d’administration. Les outils d’administration doivent être installés sur un serveur distinct qui a un accès de connexion pour le déploiement sur site existant et à Internet. L’applet de commande pour déplacer les utilisateurs de votre déploiement sur site à Skype pour Business Online, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), doit être exécuté à partir des outils d’administration connectés à votre déploiement sur site. Pour plus d’informations sur le déplacement d’utilisateurs, voir [déplacer les utilisateurs de dans les locaux à Skype pour l’activité en ligne](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md). 
  
> [!IMPORTANT]
> Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte d'utilisateur ne sera pas synchronisé avec Active Directory en local où cet utilisateur ne figurera pas. Si vous avez déjà créé des utilisateurs dans votre client en ligne et que vous souhaitez configurer le déploiement hybride avec le déploiement local, reportez-vous à l'article Move users from online to on premises (Migration d'utilisateurs en ligne vers la version locale. 
  
> [!NOTE]
> Si vous êtes actuellement un Skype pour client entreprise en ligne qui a des utilisateurs de Skype pour entreprise en ligne qui n’ont pas été activées dans un déploiement sur site, voir [déplacer les utilisateurs de Skype pour Business en ligne sur le site](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md). 
  
Lors de la planification d'un déploiement hybride, prenez en compte les aspects suivants liés aux utilisateurs.
  
- **Contacts de l’utilisateur** La limite pour les contacts pour les utilisateurs de Lync Online est de 250. Tous les contacts au-delà de ce nombre seront retirés liste de contacts de l’utilisateur lorsque le compte est déplacé vers Lync Online.
    
- **La messagerie instantanée et présence** Listes de contacts d’utilisateur, des groupes et des listes de contrôle d’accès (ACL) sont migrées avec le compte d’utilisateur.
    
- **Données de conférence, contenu de la réunion et les réunions planifiées** Ce contenu n’est pas migré avec le compte d’utilisateur. Les utilisateurs doivent replanifier les réunions une fois leur compte migré sur Lync Online.
    
## <a name="user-policies-and-features"></a>Fonctionnalités et stratégies utilisateur
<a name="BKMK_UserPolicies"> </a>

- Dans un environnement hybride, les utilisateurs peuvent utiliser la messagerie instantanée et les réunions soit sur site soit en ligne, mais pas les deux simultanément.
    
- **Prise en charge du client** Certains utilisateurs peuvent nécessiter une nouvelle version de client lorsqu’ils sont déplacés à Skype pour l’activité en ligne. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un Skype pour le pool de serveur d’entreprise ou de Lync Server 2013 avant la migration vers Skype pour l’activité en ligne.
    
- **Configuration (utilisateur) et les stratégies locales** En ligne et sur site stratégies nécessitent une configuration distincte. Vous ne pouvez pas définir des stratégies globales qui s’appliquent au deux.
    

