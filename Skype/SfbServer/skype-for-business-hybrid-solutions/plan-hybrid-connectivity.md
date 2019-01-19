---
title: Planification de la connectivité hybride | Skype pour Business Server 2015 et en ligne
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 'Résumé : consultez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.  La première étape du déploiement de nombreuses solutions hybrides Skype Entreprise consiste à configurer une connectivité hybride.'
ms.openlocfilehash: fe862c5d25a9fca17a42fb1026b608b8656d419d
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349099"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Planification de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online

**Résumé :** consultez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.  La première étape du déploiement de nombreuses solutions hybrides Skype Entreprise consiste à configurer une connectivité hybride.

Cette rubrique fournit une vue d’ensemble et décrit l’infrastructure et vous devez configurer la connectivité hybride entre votre configuration requise locaux Skype pour le déploiement de Business Server — avec des utilisateurs qui ont été créés dans votre environnement local Active Directory — et Skype pour les entreprises en ligne.

Cette rubrique contient les sections suivantes :

- [Overview](plan-hybrid-connectivity.md#BKMK_Overview)

- [Conditions requises pour l'infrastructure](plan-hybrid-connectivity.md#BKMK_Infrastructure)

- [Prise en charge des environnements multi-forêts](plan-hybrid-connectivity.md#BKMK_MultiForest)

- [Coexistence avec Exchange](plan-hybrid-connectivity.md#BKMK_Exchange)

- [Informations d'identification de l'administrateur](plan-hybrid-connectivity.md#BKMK_Credentials)

- [Skype Entreprise Online PowerShell](plan-hybrid-connectivity.md#BKMK_PowerShell)

- [Prise en charge du client Skype Entreprise](plan-hybrid-connectivity.md#BKMK_ClientSupport)

- [Conditions requises pour la topologie](plan-hybrid-connectivity.md#BKMK_Topology)

- [Configuration requise pour les listes de fédération autorisées/bloquées](plan-hybrid-connectivity.md#BKMK_Federation)

- [Paramètres DNS](plan-hybrid-connectivity.md#BKMK_DNS)

- [Éléments à prendre en compte pour le pare-feu](plan-hybrid-connectivity.md#BKMK_Firewall)

- [Configuration requise pour les ports et les protocoles](plan-hybrid-connectivity.md#BKMK_Ports)

- [Comptes et données utilisateur](plan-hybrid-connectivity.md#BKMK_UserAccounts)

- [Fonctionnalités et stratégies utilisateur](plan-hybrid-connectivity.md#BKMK_UserPolicies)

Lorsque vous avez lu cette rubrique et êtes prêt pour le déploiement, reportez-vous à l'article [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Les rubriques sur le déploiement fournissent des instructions détaillées sur la configuration d'une connectivité hybride entre votre déploiement sur site et Skype Entreprise Online.

(Pour plus d’informations sur la configuration de votre déploiement de Lync Server 2010 pour l’environnement hybride ou de Lync Server 2013, voir [Lync Server 2013 hybride](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

## <a name="overview"></a>Vue d’ensemble

<a name="BKMK_Overview"> </a>

Les solutions hybrides permettent de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. La présente rubrique traite de la connectivité hybride entre un déploiement sur site de Skype Entreprise Server et Skype Entreprise Online. Cette connectivité vous permet d'héberger des utilisateurs sur site et d'autres en ligne.

Ce type de déploiement est parfois appelé « domaine fragmenté », les utilisateurs de signification d’un domaine, par exemple, contoso.com, sont répartis entre l’utilisation de Skype pour Business Server localement et Skype pour Business Online comme suit :

- Les utilisateurs hébergés sur site interagissent avec des serveurs Skype Entreprise sur site.

- Les utilisateurs hébergés en ligne interagissent avec d'autres services en ligne de Skype Entreprise.

- Les utilisateurs des deux environnements peuvent collaborer les uns avec les autres à l'aide de la messagerie instantanée, la participation à des téléconférences, des appels VoIP, etc.

- Azure Active Directory Connect est utilisé pour synchroniser votre répertoire sur site avec Office 365.

Active Directory fait autorité, procédez donc comme indiqué ci-après pour permettre la détection entre les utilisateurs sur site et en ligne :

- Tous les utilisateurs doivent être créés dans Active Directory local en premier et puis synchronisés avec Azure AD.

- Si vos utilisateurs sont hébergés sur site pour Skype Entreprise, vous devez les activer pour Skype Entreprise sur site.

- Si vos utilisateurs sont hébergés sur site mais souhaitent utiliser certaines fonctionnalités en ligne, telles que la diffusion de réunion Skype, vous devez leur affecter une licence Skype Entreprise Online Plan 2.

- Si vos utilisateurs sont hébergés dans Skype Entreprise Online, lorsque leur compte est synchronisés avec Azure AD, vous devez leur affecter une licence Skype Entreprise Online Plan 2.

- Une fois la licence Skype Entreprise Online affectée aux utilisateurs, vous devez les activer pour Skype Entreprise ou pour Voix Entreprise sur site. Pour plus d’informations, voir [Activer les utilisateurs pour Enterprise Voice sur site](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Pour plus d'informations sur les conditions requises pour la solution vocale hybride, reportez-vous à l'article [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Les sections qui suivent fournissent de plus amples informations sur la configuration Active Directory. Mais jetons d'abord un œil à la terminologie et aux acronymes utilisés dans les diagrammes ci-après et dans de nombreuses rubriques sur la connectivité hybride :

- PSTN : Réseau téléphonique commuté

- PBX : système téléphonique autocommutateur privé

- Système téléphonique : solution de système téléphonique Cloud PBX de Microsoft

- Jonction - ligne téléphonique qui relie le PBX vers la réseau téléphonique commuté — une jonction peut utiliser le protocole SIP (Session Initiation) — un protocole voix sur IP (VoIP), ou la technologie de multiplexage de Division de temps (TDM) antérieure

- SBC (Session Border Controller) : dispositif utilisée comme pare-feu et routeur sur des réseaux téléphoniques. Entre autres avantages, il fournit la sécurité, la connectivité, l'interoperabilité et la qualité des services.

- Passerelle PSTN : dispositif utilisé comme routeur sur des réseaux téléphoniques et qui fournit les mêmes avantages qu'un dispositif SBC, excepté la sécurité et la NAT-T (Network Address Translation Traversal).

Le diagramme suivant illustre un Skype pour la configuration hybride de « domaine fragmenté » Business. les utilisateurs A et B sont hébergés en ligne mais sont détectables par les utilisateurs sur site ; les utilisateurs C et D sont hébergés sur site, mais sont détectables par les utilisateurs en ligne.

![Connectivité hybride SfB - domaine partagé](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)

Vous avez probablement déjà entendu l'expression « Voix hybride », qui fait référence aux tronçons voix sur site qui fournissent les fonctionnalités aux utilisateurs hébergés dans le cloud. La fonctionnalité Voix hybride permet la migration dans le cloud tout en conservant la configuration voix sur site. Si vous disposez déjà d'un déploiement Skype Entreprise Server, la première étape de l'activation de la fonctionnalité Voix hybride consiste à configurer un environnement de domaine partagé.

Par exemple, supposons que votre société possède un champ mobile grande organisation nécessitant PBX minimal de prise en charge vocale, mais a largement téléphone intelligent utiliser. Vous pouvez choisir de migrer les utilisateurs vers le cloud pour bénéficier des avantages du système téléphonique Microsoft dans Office 365 (Cloud PBX). Si votre société possède également un centre d’appels local grande qui requiert le logiciel de centre de contact avancé, complexes dans le cadre de votre système PBX sur site, vous pouvez choisir de laisser les utilisateurs sur site. Les utilisateurs hébergés en ligne et sur site disposent d'une connectivité PSTN via votre déploiement sur site.

Le diagramme ci-dessous présente un déploiement du service vocal hybride de Skype Entreprise :

![Domaine partagé SfB avec Cloud PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)

Pour plus d’informations sur la configuration d’une solution de voix hybride avec votre Skype pour le déploiement de serveur d’entreprise, voir [Planifier le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Vous pouvez également configurer des déploiements hybrides pour l’intégration à Exchange et SharePoint local ou avec les applications Microsoft Office 365, notamment Exchange Online et SharePoint Online. Vous pouvez également configurer une solution vocale hybride qui ne requiert pas le déploiement complet de Skype Entreprise Server en utilisant la version Cloud Connector. Pour plus d’informations sur tous les Skype pour la planification de votre migration vers le nuage et des solutions professionnelles hybride, voir [Skype pour des solutions professionnelles hybride](skype-for-business-hybrid-solutions.md).

## <a name="infrastructure-requirements"></a>Conditions requises pour l'infrastructure

<a name="BKMK_Infrastructure"> </a>

Pour implémenter et déployer une connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online, vous devez configurer les éléments suivants dans votre environnement :

- Un seul déploiement local de Skype pour Business Server ou un serveur Lync qui est déployé dans une topologie prise en charge. Dans cette rubrique, voir [Configuration requise de topologie](plan-hybrid-connectivity.md#BKMK_Topology) .

    > [!NOTE]
    > Tous les domaines SIP qui existe dans votre environnement local doivent également exister dans votre organisation cliente Office 365 et vice versa. Vous ne pouvez pas des domaines SIP en ligne uniquement et certains domaines locaux uniquement. Dans le cas contraire, présence, messagerie instantanée et autres fonctionnalités fonctionnera pas correctement.

- Un client Microsoft Office 365 avec Skype pour Business Online activé.

    > [!NOTE]
    > Vous ne pouvez utiliser qu'un seul client pour une configuration hybride avec votre déploiement local.

- Skype pour les outils d’administration Business Server 2015. (Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration Lync Server 2013. Pour plus d'informations, reportez-vous à l'article [Lync Server 2013 hybride](https://go.microsoft.com/fwlink/p/?LinkId=617360).

- Azure Active Directory Connect pour synchroniser votre répertoire sur site avec Office 365. Pour plus d'informations, reportez-vous à la rubrique [Connexion d'Active Directory à Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Pour prendre en charge l'authentification unique Office 365 afin que les utilisateurs puissent utiliser les mêmes informations d'identification de connexion sur site, vous pouvez utiliser les fonctionnalités de synchronisation des mots de passe Azure Active Directory (AAD) Connect. Vous pouvez également utiliser AD FS (Active Directory Federation Services) avec l’authentification unique pour Office 365. 

- Fédération activée entre votre déploiement Skype Entreprise sur site et votre client Office 365. La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation. Pour plus d'informations, reportez-vous à l'article [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

- Espace d'adressage SIP (Session Initiation Protocol) partagé et activé. Une adresse SIP est un identificateur unique pour chaque utilisateur d'un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie. Avant d’essayer de déplacer les utilisateurs locaux vers Skype pour Business Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site. Pour plus d'informations, reportez-vous à l'article [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Les utilisateurs peuvent accéder aux fonctionnalités Skype Entreprise dans une autre forêt si les conditions suivantes sont réunies :

- Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise ; dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu'objets utilisateurs désactivés.

- La forêt hébergeant Skype Entreprise doit approuver la forêt contenant les utilisateurs.

Pour plus d’informations sur les scénarios hybrides à forêts multiples, consultez [configurer un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).

## <a name="exchange-co-existence"></a>Coexistence avec Exchange

<a name="BKMK_Exchange"> </a>

Pour prendre en charge la coexistence avec Exchange, tenez compte des points suivants :

- La meilleure pratique consiste à déplacer la boîte aux lettres vers Exchange Online avant de déplacer Skype l’utilisateur pour les entreprises d’accueil.

- Les utilisateurs disposant de boîtes aux lettres sur site sont pris en charge avec les limites connues suivantes :

  - Connexion client : les utilisateurs devront peut-être se connecter deux fois au client Skype Entreprise.

  - Serveur côté l’historique des conversations, d’archivage, Unified Contact Store, Photo HighRes requiert Exchange 2013 ou version ultérieure, et vous devez activer le serveur OAuth pour Communications Server. Pour plus d’informations, voir [gérer l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Skype pour Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).

Pour plus de détails sur la coexistence avec Exchange Server, notamment sur les critères de prise en charge et les limitations de plusieurs combinaisons locales et en ligne, reportez-vous à la rubrique [Fonctionnalités prises en charge](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) dans [Plan to integrate Skype for Business and Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).

## <a name="administrator-credentials"></a>Informations d'identification de l'administrateur

<a name="BKMK_Credentials"> </a>

Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe pour le compte d’administrateur pour votre client Office 365. Vous allez également utiliser ces informations d’identification lorsque vous configurez Azure Active Directory pour la fédération, la synchronisation d’annuaires, authentification unique et déplacement d’utilisateurs vers Skype pour Business en ligne.

## <a name="skype-for-business-online-powershell"></a>Skype Entreprise Online PowerShell

<a name="BKMK_PowerShell"> </a>

Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer Skype pour Business Online et leur Skype pour les comptes d’utilisateurs professionnels en ligne. Pour ce faire, vous devez d’abord télécharger et installer le Skype pour Module connecteur en ligne d’entreprise à partir du Microsoft Download Center. Pour plus d’informations sur le téléchargement, l’installation et à l’aide de la Skype pour Module connecteur en ligne d’entreprise et pour plus d’informations sur l’utilisation de Windows PowerShell pour gérer Skype pour Business Online, voir [à l’aide de Windows PowerShell pour gérer les Skype pour les entreprises En ligne](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Prise en charge du client Skype Entreprise

<a name="BKMK_ClientSupport"> </a>

Des différences existent dans les fonctionnalités prises en charge dans les clients, ainsi que dans les fonctionnalités disponibles dans des environnements locaux et en ligne. Les clients suivants sont pris en charge avec Skype pour Business Online dans un déploiement hybride :

- Skype Entreprise

- Lync 2013

- Lync 2010

- application Lync du Windows Store

- Lync Web App

- Lync Mobile

- Lync pour Mac 2011

- Système de salle de Lync et Skype pour le système d’entreprise salle

- Lync Basic 2013

- Microsoft Surface Hub

Avant de décider où vous souhaitez héberger des utilisateurs dans votre organisation, vous devez examiner la [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) pour déterminer la prise en charge du client pour les différentes configurations de Skype pour Business Server. Voir aussi :

- [Planifier des clients et des appareils](../plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparaison des fonctionnalités de client mobile pour Skype pour les entreprises](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Conditions requises pour la topologie

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec Skype pour Business Online, vous devez disposer d’un des topologies prises en charge suivantes :

- Un Skype pour le déploiement d’entreprise Server 2015 avec tous les serveurs exécutant Skype pour Business Server 2015.

- Un déploiement de Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.

    Dans le cadre de la connectivité voix hybride, le serveur Edge désigné comme serveur Edge de fédération doit exécuté Skype Entreprise 2015 et requiert un serveur principal Skype Entreprise Server. Vous pouvez disposer d'un pool sans utilisateur.

- Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les dernières mises à jour cumulatives.

  - La fédération Edge Server et le serveur du tronçon suivant de la fédération de serveur de transport Edge doivent exécuter Lync Server 2010 avec les dernières mises à jour cumulatives.

  - Le Skype pour Business Server 2015 ou les outils d’administration de Lync Server 2013 doit être installé sur au moins un serveur ou station de travail de gestion.

- Lync Server 2013 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :

  - Au moins un pool d'entreprise ou serveur Standard Edition 

  - Pool directeur associé à la fédération SIP, le cas échéant

  - Pool Edge associé à la fédération SIP

- Lync Server 2010 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :

  - Au moins un pool d'entreprise ou serveur Standard Edition 

  - Pool directeur associé à la fédération SIP, le cas échéant

  - Pool Edge associé à la fédération SIP pour le site

- Un déploiement de Lync Server 2010 et Lync Server 2013 mixte avec les rôles de serveur suivants au moins un site exécutant Lync Server 2013 :

  - Au moins un pool d'entreprise ou serveur Standard Edition dans le site

  - Pool directeur associé à la fédération SIP, si elle existe dans le site

  - Pool Edge associé à la fédération SIP pour le site

## <a name="federation-allowedblocked-lists-requirements"></a>Configuration requise pour les listes de fédération autorisées/bloquées

<a name="BKMK_Federation"> </a>

La liste des domaines autorisés inclut les domaines qui ont un nom de domaine complet de serveur Edge partenaire (FQDN) configuré. Ils sont parfois en tant que partenaires de fédération de partenaire autorisé serveurs ordirect. Vous devez connaître la différence entre la fédération ouverte et fermée la fédération, désigné comme liste des domaines partenaires découverte andallowed partenaire, respectivement, dans les déploiements sur site.

La configuration ci-dessous est requise pour configurer un déploiement hybride :

- La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.

- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

- Fédération doit être activée pour les communications externes pour le client en ligne, qui est configurée à l’aide de la Skype pour Business Online le panneau de configuration.

## <a name="dns-settings"></a>Paramètres DNS

<a name="BKMK_DNS"> </a>

Lorsque vous créez des enregistrements DNS pour les déploiements hybrides, tous les Skype pour les enregistrements DNS externes Business doit pointer sur l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la [configuration DNS requise pour Skype pour Business Server 2015](../plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau ci-dessous fonctionne dans votre déploiement local :

|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp. \<sipdomain.com\> toutes prises en charge les domaines SIP résoudre les adresses IP externes Edge d’accès  <br/> |Serveur(s) Edge  <br/> |Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.  <br/> Doit utiliser un nom DNS strict identique pour le domaine du nom d'utilisateur et pour l'enregistrement SRV.  <br/> |
|Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web  <br/> |Réseau d’entreprise interne connecté les ordinateurs des utilisateurs  <br/> |Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.   <br/> |

En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne.

[!NOTE] _sipfederationtls._tcp. \<sipdomain.com\> résolution d’enregistrement SRV depuis le serveur Edge est requise pour la configuration hybride. Si le serveur de périphérie ne peut pas résoudre ces enregistrements, les utilisateurs locaux ne sera pas en mesure de voir la présence ou de communiquer avec les utilisateurs en ligne.

## <a name="firewall-considerations"></a>Éléments à prendre en compte pour le pare-feu

<a name="BKMK_Firewall"> </a>

Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine générique (par exemple, tout le trafic \*. outlook.com). Si le pare-feu de votre organisation ne prennent pas en charge les génériques des configurations de nom, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d'informations, reportez-vous à la rubrique [URL et plages d'adresses IP Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Configuration requise pour les ports et les protocoles

<a name="BKMK_Ports"> </a>

En plus de la configuration requise pour les ports pour les communications internes, vous devez également configurer les ports suivants pour activer la connectivité hybride :

|Protocole|TCP ou UDP|Adresse IP source|Adresse IP de destination|Port source|Port de destination|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Serveur Edge d’accès  <br/> |Office 365  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Serveur Edge d’accès  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|STUN  <br/> |TCP  <br/> |Edge A/V  <br/> |Office 365  <br/> |50000-59999  <br/> |443  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Edge A/V  <br/> |50000-59999  <br/> |443  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |UDP  <br/> |Edge A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Edge A/V  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |

Pour plus d’informations sur le port et de planification pour le serveur Edge de pare-feu, consultez [exigences de serveur de transport Edge dans Skype pour Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Reportez-vous également à l'article [Port and protocol requirements for servers](../plan-your-deployment/network-requirements/ports-and-protocols.md) et au [Digramme des charges de travail de protocole](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Comptes et données utilisateur

<a name="BKMK_UserAccounts"> </a>

Dans un déploiement hybride, tout utilisateur que vous souhaitez personnel en ligne doit être créé dans le déploiement local, afin que le compte d’utilisateur est créé dans les Services de domaine Active Directory. Vous pouvez ensuite déplacer l’utilisateur à Skype pour Business en ligne, qui déplace la liste des contacts de l’utilisateur.

Lorsque vous synchronisez les comptes d’utilisateurs entre votre déploiement local et du client en ligne à l’aide de DAS se connecter, vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs de Lync ou de l’entreprise dans votre organisation, même si les utilisateurs ne sont pas déplacés vers en ligne. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.

> [!IMPORTANT]
> Gestion de tous les utilisateurs, y compris utilisateur déplace entre locale et Skype pour Business Online doivent être effectué à l’aide de la dernière version installée des outils d’administration. Les outils d’administration doivent être installés sur un serveur distinct qui a un accès de connexion pour le déploiement local existant et Internet. L’applet de commande pour déplacer les utilisateurs de votre déploiement sur site vers Skype pour Business Online, [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps), doit être exécuté à partir des outils d’administration connectées à votre déploiement sur site. Pour plus d’informations sur le déplacement d’utilisateurs, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md).

> [!IMPORTANT]
> Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte d'utilisateur ne sera pas synchronisé avec Active Directory en local où cet utilisateur ne figurera pas. Si vous avez déjà créé des utilisateurs dans votre client en ligne et que vous souhaitez configurer le déploiement hybride avec le déploiement local, reportez-vous à l'article Move users from online to on premises (Migration d'utilisateurs en ligne vers la version locale.

> [!NOTE]
> Si vous êtes actuellement un Skype pour Business Online client qui accueille des utilisateurs activés pour Skype pour Business Online qui n’ont pas été activés dans un déploiement sur site, voir [déplacer les utilisateurs de Skype pour Business en ligne et sur site](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md).

Lors de la planification d'un déploiement hybride, prenez en compte les aspects suivants liés aux utilisateurs.

- **Contacts de l’utilisateur** La limite pour les contacts Skype pour les utilisateurs professionnels en ligne est de 250. Les contacts au-delà de ce numéro seront retirés liste des contacts de l’utilisateur lorsque le compte est déplacé à Skype pour Business Online.

- **Messagerie instantanée et présence** Listes des contacts utilisateur, des groupes et des listes de contrôle d’accès (ACL) sont migrées avec le compte d’utilisateur.

- **Données de conférence, contenu de réunion et les réunions planifiées** Ce contenu n’est pas migré avec le compte d’utilisateur. Les utilisateurs doivent replanifier les réunions après que leurs comptes sont migrés vers Skype pour Business Online. Le Service de Migration de réunion sera cela automatiquement lors de la migration à partir d’un Skype pour Business server à Skype pour Business en ligne ou les équipes, voir [l’aide du Service de Migration de réunion](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

## <a name="user-policies-and-features"></a>Fonctionnalités et stratégies utilisateur

<a name="BKMK_UserPolicies"> </a>

- Dans un environnement hybride, les utilisateurs peuvent utiliser la messagerie instantanée et les réunions soit sur site soit en ligne, mais pas les deux simultanément.

- **Prise en charge du client** Certains utilisateurs peuvent nécessiter une nouvelle version de client lorsqu’ils sont déplacés vers Skype pour Business Online. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un Skype pour Business Server ou Microsoft Lync Server 2013 pool avant la migration vers Skype pour Business Online.

- **Configuration (non utilisateur) et les stratégies local** En ligne et locales stratégies nécessitent une configuration distincte. Vous ne pouvez pas définir des stratégies globales qui s'appliquent au deux.