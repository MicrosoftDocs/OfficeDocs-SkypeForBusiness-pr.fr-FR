---
title: DNS requirements for Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé : Examinez les considérations DNS de cette rubrique avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: fa81b85fb7254130302ed9163a652f03ec1bf33c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859831"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS requirements for Skype Entreprise Server

**Résumé :** Examinez les considérations DNS de cette rubrique avant d’implémenter Skype Entreprise Server.

Cet article traite uniquement de la planification DNS pour Skype Entreprise Server déploiements sur le réseau local d’une organisation. For Skype Entreprise Online refer to « Office 365 URLs and IP address ranges » at [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) .

Un serveur DNS (Domain Name Service) m’indique les noms d’hôte (par ex. www. <span></span> contoso .com, probablement un serveur web) vers des <span></span> adresses IP (telles que 10.10.10.10). Il permet aux clients et aux serveurs interdépendants de communiquer les uns avec les autres sur le réseau. Lorsque vous configurerez une implémentation de Skype Entreprise Server 2015, vous devez vous assurer que le mappage des nouveaux noms de serveur (reflétant généralement le rôle qu’ils vont jouer) correspond aux adresses IP à qui ils sont affectés.

Bien que cela puisse sembler un peu difficile au début, le travail de planification peut être effectué à l’aide de l’outil de planification [Skype Entreprise Server 2015.](https://www.microsoft.com/download/details.aspx?id=50357) Une fois que vous avez répondu aux questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez, vous pouvez afficher le rapport DNS dans le rapport d’administration Edge et utiliser les informations répertoriées ici pour créer vos enregistrements DNS. Vous pouvez également apporter des ajustements à la plupart des noms et adresses IP utilisés, pour plus d’informations, consultez le rapport [DNS.](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report) Gardez à l’esprit que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel, et le rapport DNS sera l’une des feuilles de calcul du fichier. Bien que cet outil inclut des fonctionnalités Skype Entreprise Server [2019,](../../../SfBServer2019/deprecated.md)il peut toujours être utilisé pour créer un plan initial si ces fonctionnalités ne sont pas sélectionnées.

Lorsque vous installez une nouvelle implémentation comme décrit dans Créer des enregistrements [DNS](../../deploy/install/create-dns-records.md) pour Skype Entreprise Server et créer votre topologie pour Skype Entreprise Server, nous savons que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées à Windows Server 2016 ou à un package DNS tiers. Nous allons donc conserver le d iscussions in this article general rather than specific. Nous détaillerons ce qui est nécessaire et la façon dont vous répondez à ce besoin, c’est votre décision à prendre.

Les administrateurs Skype Entreprise, Lync et Office Communications Suite trouveront probablement les tableaux suivants utiles. Si le tableau ne vous semble pas clair, les sections ou articles suivants apporteront un éclairage sur les concepts suivants :

## <a name="summary-tables"></a>Tableaux récapitulatifs
<a name="BK_Summary"> </a>

Les tableaux suivants indiquent les enregistrements DNS Skype Entreprise Server pour fournir des services aux utilisateurs. Certaines sont facultatives dans la mesure où elles ne sont nécessaires que pour prendre en charge certaines fonctionnalités, et elles peuvent être ignorées si ces fonctionnalités ne sont pas souhaitées. Les enregistrements DNS nécessaires uniquement pour l’accès interne sont dans la première table et un déploiement permettant un accès interne et externe aura besoin d’enregistrements des deux tables.

**Mappages DNS internes**

|Type d’enregistrement|Value (Valeur)|Résolu en|Objectif|Obligatoire|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN du pool frontal  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |Adresses IP du serveur de pool frontal  <br/>  DNS LB vers *192.168.21.122 192.168.21.123 192.168.21.124*   |Équilibrage de charge DNS des pools frontaux. Cartes nom du pool frontal à un ensemble d’adresses IP.  <br/> Voir [Déploiement de l’équilibrage de charge DNS sur les pools frontaux et les pools directeurs](load-balancing.md#BK_FE_Dir)  |O   |
|A/AAAA   | FQDN de chaque serveur frontal ou serveur Édition Standard serveur dans un pool, ou d’un serveur autonome <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |ADRESSE IP correspondante de chaque serveur  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Cartes nom du serveur à son adresse IP.   |O   |
|A/AAAA   |Enterprise FQDN de remplacement des services web internes du pool  <br/> *Web-int. <span></span> contoso <span></span> .com*   |Adresse VIP HLB pour les services web internes du serveur frontal  <br/> *192.168.21.120*   |Requis pour activer le trafic web client à serveur, tel que le téléchargement du Application Web Skype Entreprise. Également requis pour les clients mobiles.   |O   |
|A/AAAA   |Enterprise FQDN de remplacement des services web externes de pool  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |Adresse VIP HLB pour les services web externes de serveur frontal  <br/>*68.123.56.90*   |Requis pour activer le trafic web client à serveur, tel que le téléchargement du Application Web Skype Entreprise. Obligatoire si les clients mobiles résolvent le DNS en interne. Peut résoudre en adresse IP de proxy inverse DMZ ou IP Internet.   ||
|A/AAAA   | Nom de SQL serveur principal <br/> *SQL1. <span></span> contoso <span></span> .com*   |adresse IP du serveur  <br/> *192.168.11.90*   |Cartes nom de serveur d’un serveur principal SQL avec le pool frontal à son adresse IP   ||
|A/AAAA   |Nom de SQL serveur principal miroir  <br/> *SQL2. <span></span> contoso <span></span> .com*   |adresse IP du serveur  <br/> *192.168.11.91*   |Cartes nom de serveur d’un serveur SQL miroir principal travaillant avec le pool frontal sur son adresse IP   ||
|A/AAAA   |FQDN du pool directeur  <br/>**Remarque :** Non applicable lors de l’utilisation d’un serveur directeur autonome <br/> *DirPool. <span></span> contoso <span></span> .com*   |Adresses IP du pool directeur  <br/> DNS LB vers *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Équilibrage de charge DNS des serveurs du pool directeur. Cartes nom du pool directeur vers une adresse IP, voir [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir) <br/> Un directeur peut authentifier un utilisateur et est facultatif.   ||
|A/AAAA   |FQDN directeur   |Adresse IP du serveur de chaque serveur directeur   |Cartes nom du pool pour le directeur vers une adresse IP, voir Déploiement de l’équilibrage de charge [DNS](load-balancing.md#BK_FE_Dir) sur les pools frontaux et les pools directeurs  ||
|A/AAAA   |FQDN du pool de serveurs de médiation   |Adresses IP du pool   |Le rôle serveur de médiation est facultatif. Vous pouvez co-localiser les services fournis par un serveur de médiation vers le serveur frontal ou le pool. Voir [l’utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN du serveur de médiation   |Adresse IP du serveur   |Vous pouvez co-localiser les services fournis par un serveur de médiation vers le serveur frontal ou le pool. Voir [l’utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN du serveur de conversation permanente   |Adresse IP du serveur de conversation permanente   |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente et est autrement facultatif.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |ADRESSE IP du pool frontal HLB ou adresse IP du directeur  <br/>  192.168.21.121  |Service de découverte automatique1 interne, requis pour la prise en charge de la mobilité. Si le DNS interne est utilisé pour résoudre les appareils mobiles, il doit pointer vers l’adresse IP externe ou l’adresse IP ip DMZ.  <br/> Pour les services Web, nous avons besoin d’un hLB sur le pool frontal, car HTTPS ne peut pas tirer parti du DNS. Dans le cas d’un pool frontal ou d’un pool directeur, cette solution doit être résolue en adresse IP ip principale ou normale pour un serveur Standard Edition Server ou un serveur directeur autonome.   |O   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN de pool fe hLB ou FQDN directeur  <br/> Web-int. <span></span> contoso <span></span> .com   |Service de découverte automatique interne 1 <br/> Vous pouvez l’implémenter en tant qu’enregistrement CNAME au lieu d’un enregistrement A si vous le souhaitez.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Adresses IP du serveur de pool frontal (ou à une adresse IP de directeur)  <br/>  DNS LB vers *192.168.21.122 192.168.21.123 192.168.21.124*   |Requis pour la configuration automatique, voir [la walkthrough of Skype Entreprise clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Enregistrement ou enregistrement pointant vers les serveurs du pool frontal ou les serveurs directeurs sur le réseau interne, ou le service Edge d’accès lorsque le client est externe   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |ADRESSE IP principale ou VIP HLB du pool FE HLB ou SE/Director Server  <br/>  192.168.21.121  |Le déploiement de cet enregistrement est facultatif &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Port 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Port 5061  |FQDN du pool frontal  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Active la authentification automatique de l’utilisateur interne 1 vers le serveur/pool frontal ou le serveur/pool SE qui authentifier et redirige les demandes de client pour la signature.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN du pool frontal  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Accès des utilisateurs &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Source NTP requise pour les appareils Lync Téléphone Edition   |Cela est nécessaire pour prendre en charge les combinés de bureau.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN du service Edge d’accès <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Créez un enregistrement SRV pour chaque domaine SIP qui possède des clients IOS ou Windows téléphone mobile.   |Prise en charge du client mobile   |
|A/AAAA   |URL d’administration  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype Entreprise Server Panneau de commande, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de réunion  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Réunions en ligne, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de connexion  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conférence rendez-vous, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN des services web internes  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype Entreprise Service Web utilisé par les Application Web Skype Entreprise   ||
|A/AAAA   |Office Nom de pool de serveurs Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Office Adresse IP ip du pool Web Apps Server <br/> 192.168.1.5   |Définit le nom de Office de pool Web Apps Server   ||
|A/AAAA   | FQDN web interne <br/> Web-int. <span></span> contoso <span></span> .com   | Adresse IP ip du pool frontal <br/> 192.168.21.121   |Définit le FQDN web interne utilisé par les Application Web Skype Entreprise  <br/> Si vous utilisez l’équilibrage de charge DNS sur ce pool, votre pool frontal et votre batterie de serveurs web internes ne peuvent pas avoir le même nom de groupe.   ||

&#x2776; utilisé par un client pour découvrir le serveur frontal ou le pool frontal, et être authentifié et signé en tant qu’utilisateur. Pour plus d’informations à ce sujet, vous y trouverez la Skype Entreprise [des clients qui recherchent des services.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; uniquement pour prendre en charge les clients hérités antérieurs à Lync 2013 et les combinés de bureau.

&#x2778; Dans le cas où un périphérique de communications unifiées est allumé, mais qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet à l’appareil de découvrir le serveur hébergeant le service Web de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.

Le diagramme suivant montre un exemple qui inclut les enregistrements DNS internes et externes, ainsi que la plupart des enregistrements affichés dans les tableaux environnants :

**Diagramme du réseau Edge à l’aide d’adresses IPv4 publiques**

![exemple de diagramme réseau DNS.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mappages DNS de réseau de périmètre (interfaces internes et externes)**

|Type d’enregistrement|Value (Valeur)|Résolu en|Objectif|Obligatoire|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN du pool edge interne  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Adresses IP du pool edge côté interne  <br/> 172.25.33.10, 172.25.33.11   |Adresses IP de l’interface interne du pool Edge consolidé   |O   |
|A/AAAA   |FQDN du serveur Edge  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |Adresse IP du serveur interne pour un serveur dans le pool de serveurs Edge  <br/> 172.25.33.10   |Créez un enregistrement pour chaque serveur du pool avec le FQDN du serveur pointant vers son adresse IP de nœud de serveur interne dans le pool. Consultez l’équilibrage de charge [DNS](load-balancing.md#BK_Edge)sur les pools de serveurs Edge.   |O   |
|A/AAAA   |FQDN du pool de services Edge d’accès  <br/>*Access1. <span></span> contoso <span></span> .com*  |Adresses IP externes du pool de services Edge d’accès  <br/> 131.107.16.10, 131.107.16.11   |Le service Edge d’accès fournit un point de connexion unique sécurisé qui est utilisé pour le trafic SIP (Session Initiation Protocol) à la fois sortant et entrant.   |O   |
|A/AAAA   |FQDN du pool de services Edge de conférence web  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Adresses IP externes du service Edge de conférence web  <br/> 131.107.16.90, 131.107.16.91   |Le service Edge de conférence web permet aux utilisateurs externes de participer à des réunions hébergées sur votre environnement Skype Entreprise Server interne.   |O   |
|A/AAAA   |*av.\<sip-domain\>* Nom de domaine complet du pool <br/>*AV1. <span></span> contoso <span></span> .com*  |Adresses IP externes edge A/V  <br/> 131.107.16.170, 131.107.16.171   |Le service Edge A/V met l’audio, la vidéo, le partage d’application et le transfert de fichiers à la disposition des utilisateurs externes.   |O   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN du pool edge d’accès externe  <br/>*Access1. <span></span> contoso <span></span> .com*  |Localise le pool de serveurs Edge. Voir [la walkthrough of Skype Entreprise clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |O   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN du edge d’accès externe  <br/>_Access1. <span></span> contoso <span></span> .com_  |Utilisé pour l’accès des utilisateurs externes. Voir [la walkthrough of Skype Entreprise clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |O   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN du edge d’accès externe  <br/>*Access1. <span></span> contoso <span></span> .com*  |Utilisé pour la fédération et la connectivité DE MESSAGERIE INSTANTANÉE publique   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN du edge d’accès externe  <br/>*Access1. <span></span> contoso <span></span> .com*  |Le service proxy XMPP accepte et envoie des messages XMPP (Extensible Messaging and Presence Protocol) vers et depuis des partenaires fédérés XMPP configurés.   |Y, pour déployer la fédération, sinon facultatif  <br/> Non disponible dans Skype Entreprise Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN du edge d’accès externe  <br/>*Access1. <span></span> contoso <span></span> .com*  |Pour prendre en charge le service de notification Push et le service de notification Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP. &#x2778;  ||
|A/AAAA   |FQDN des services web de pool frontal externe  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Adresse IP publique de proxy inverse, proxys vers l’adresse IP ip des services web externes pour votre pool frontal &#x2776; <br/> 131.107.155.1 proxy vers 192.168.21.120   |Interface externe du pool frontal utilisée par les Application Web Skype Entreprise   |O   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Adresse IP publique de proxy inverse, résolue en adresse IP IP des services web externes pour votre pool directeur, si vous en avez une, ou pour votre pool frontal si vous n’avez pas de &#x2777; <br/> 131.107.155.1 proxy vers 192.168.21.120   | Enregistrement externe pour la découverte automatique du client, également utilisé par mobility, Application Web Skype Entreprise et scheduler Web app, résolu par le serveur proxy inverse <br/> Pour prendre en charge le service de notifications Push et le service de notification Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP qui possède des clients Microsoft Lync Mobile. 3  |O   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Adresse IP publique de proxy inverse, résolue en interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy vers 192.168.21.120   |Proxy to Skype Entreprise Web Service  <br/> Voir [URL simples](dns.md#BK_Simple)  |O   |
|A/AAAA   |numérotation.*\<sipdomain\>* <br/> numérotation. *<span></span> contoso <span></span> .com*  |Adresse IP publique de proxy inverse, proxys vers l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy vers 192.168.21.120   |Proxy to Skype Entreprise Web Service  <br/> Voir [URL simples](dns.md#BK_Simple)  |O   |
|A/AAAA   |Office Nom de pool de serveurs Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Adresse IP publique de proxy inverse, proxys vers l’interface Web externe pour Office Web Apps Server <br/> 131.107.155.1 proxy vers 192.168.1.5   | Office Adresse IP ip du pool Web Apps Server <br/> 192.168.1.5   |Définit le nom de Office de pool Web Apps Server   |

&#x2776; obligatoire pour déployer la fédération, sinon facultatif.

&#x2777; utilisé par un client pour découvrir le serveur frontal ou le pool frontal, et être authentifié et signé en tant qu’utilisateur.

&#x2778; cette exigence s’applique uniquement aux clients sur des appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas les notifications Push.

 Pour plus d’informations sur les serveurs Edge et les réseaux de périmètre, voir le contenu de planification [DNS du](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) serveur Edge.

> [!IMPORTANT]
> Skype Entreprise Server prend en charge l’utilisation de l’adressare IPv6. Pour [plus d’informations, consultez](ipv6.md) la Skype Entreprise plan pour IPv6.

> [!IMPORTANT]
> Pour plus d’informations sur les FQDN, voir les informations [de base sur DNS.](basics.md)

DNS Split **Brain** 
 <a name="BK_split"></a>

Le DNS Split Brain est une configuration DNS dans laquelle vous avez deux zones DNS avec le même espace de noms. La première zone DNS gère les demandes internes, tandis que la seconde zone DNS gère les demandes externes, comme mentionné dans ces tableaux. Pour plus d’informations à ce sujet, [voir DNS Split-brain.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

## <a name="hybrid-considerations"></a>Considérations sur les hybrides
<a name="BK_Hybrid"> </a>

Si vous prévoyez d’avoir certains utilisateurs en ligne et d’autres sur site, reportez-vous à l’article de planification de la connectivité hybride [Skype Entreprise server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Vous devez configurer DNS comme d’habitude pour Skype Entreprise Server 2015 et ajouter des enregistrements DNS supplémentaires.

Vous devez également vous référer à « Office 365 URL et plages d’adresses IP » pour confirmer que vos utilisateurs auront accès aux ressources en ligne dont ils [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) auront besoin.

## <a name="simple-urls"></a>URL simples
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource web qui spécifie son emplacement sur un réseau informatique et un protocole utilisé pour la récupérer.

Skype Entreprise Server prend en charge l’utilisation de trois URL « simples » pour accéder aux services :

- **Meet** est utilisé comme URL de base pour toutes les conférences dans le site. Https: meet est un exemple d’URL simple <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Une URL pour une réunion particulière peut être https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com/_username_/7322994.

    Avec l’URL simple Meet, les liens pour participer aux réunions sont faciles à comprendre et à communiquer.

- **La numérotation** permet d’accéder à la page web conférence Paramètres conférence. Cette page affiche les numéros d’accès aux conférences avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire, pour les réunions qui ne doivent pas être programmées) et les contrôles DTMF en conférence, et prend en charge la gestion du code confidentiel et des informations de conférence attribuées. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Un exemple d’URL simple dial-in est https:// <span></span> dialin. <span></span> contoso <span></span> .com.

- **L’administrateur** permet un accès rapide au Panneau de Skype Entreprise Server de contrôle. À partir de n’importe quel ordinateur des pare-feu de votre organisation, un administrateur peut ouvrir le Panneau de Skype Entreprise Server en tapant l’URL simple Admin dans un navigateur. L’URL simple d’administration est interne à votre organisation. Un exemple d’URL simple Admin est https:// <span></span> administrateur. <span></span> contoso <span></span> .com.

Les URL simples sont abordées plus en détail dans les conditions [DNS requises](simple-urls.md)pour les URL simples dans Skype Entreprise Server .

## <a name="dns-by-server-role"></a>DNS par rôle serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme vous le souhaitez, mais les rendre faciles à souvenir et refléter leur fonction dans le système.

### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools individuels

Ces exigences d’enregistrement générique s’appliquent à tout rôle serveur utilisé par Skype Entreprise. Un pool est un ensemble de serveurs exécutant les mêmes services qui fonctionnent ensemble pour gérer les demandes des clients qui leur sont adressées via un équilibrage de charge. Voir [les exigences d’équilibrage de charge Skype Entreprise](load-balancing.md) pour plus d’informations

**DNS record Requirements for Server/pool roles (suppose l’équilibrage de charge DNS)**

|Scénario de déploiement|Enregistrement DNS requis|
|:-----|:-----|
|One Server :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal   |Enregistrement A interne associant le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Pool :  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal   |Enregistrement A interne qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur du pool en son adresse IP.  <br/>**Exemple** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Plusieurs enregistrements A internes qui résolvent le nom de domaine complet (FQDN) du pool en adresses IP des noms de serveurs du pool.  <br/>**Exemple** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Rubriques DNS spécifiques au serveur Edge

 Pour planifier le déploiement de serveurs Edge, examinez planifier les déploiements de serveurs Edge dans [Skype Entreprise Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et la planification DNS du serveur Edge avancé pour [Skype Entreprise Server 2015,](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) qui contient les sections suivantes:

- [Récupération d’urgence DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [équilibrage de charge DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuration automatique sans DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype Entreprise clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)