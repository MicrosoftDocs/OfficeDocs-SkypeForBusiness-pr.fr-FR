---
title: Configuration DNS requise pour Skype entreprise Server
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé : consultez les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982809"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Configuration DNS requise pour Skype entreprise Server

**Résumé :** Consultez les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype entreprise Server.

Cet article traite uniquement la planification DNS pour les déploiements de Skype entreprise Server sur le réseau local d’une organisation. Pour Skype entreprise Online, reportez-vous à « URL et plages d’adresses [https://aka.ms/o365ips](https://aka.ms/o365ips)IP Office 365 » à l’adresse.

Un serveur DNS (Domain Name Service) mappe des noms d’hôtes (par<span> </span> exemple, www. Contoso<span></span>. com, vraisemblablement un serveur Web) en adresses IP (par exemple, 10.10.10.10). Elle permet aux clients et aux serveurs interdépendants de communiquer les uns avec les autres sur le réseau. Lorsque vous configurez une implémentation de Skype entreprise Server 2015, vous devez vous assurer que le mappage des nouveaux noms de serveur (reflétant généralement le rôle auquel ils vont prendre en charge) correspond aux adresses IP auxquelles elles sont affectées.

Bien que cela puisse paraître un peu décourageante, l’important travail de planification de cette opération peut être réalisé à l’aide de l' [outil de planification de Skype entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=50357). Une fois que vous avez rencontré les questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez, vous pouvez afficher le rapport DNS dans le rapport Edge admin et utiliser les informations qui y sont indiquées pour créer vos enregistrements DNS. Vous pouvez également apporter des modifications à la plupart des noms et des adresses IP utilisés, pour plus d’informations, consultez [la rubrique Review the DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). N’oubliez pas que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel, et que le rapport DNS sera l’une des feuilles de calcul du fichier. Bien que cet outil comprenne [des fonctionnalités déconseillées de Skype entreprise Server 2019](../../../SfBServer2019/deprecated.md), il peut toujours être utilisé pour créer un plan initial si ces fonctionnalités ne sont pas sélectionnées.

Lorsque vous installez une nouvelle implémentation, comme décrit dans [Create DNS Records for Skype for Business Server](../../deploy/install/create-dns-records.md) et Building Your Topology for Skype for Business Server, nous vous reconnaissons que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées à Windows Server 2016 ou un package DNS tiers, de sorte que nous allons tenir les discussions dans cet article général plutôt que spécifiques. Nous détaillerons ce qui est nécessaire et la façon dont vous répondez à ce besoin est votre décision de passer.

Les administrateurs de la suite Skype entreprise, Lync et Office Communications ont pu trouver les tableaux suivants utiles. Si le tableau ne vous gêne pas, les sections ou articles suivants vous permettront de prendre en lumière les concepts suivants :

## <a name="summary-tables"></a>Tableaux de synthèse
<a name="BK_Summary"> </a>

Les tableaux suivants présentent les enregistrements DNS que Skype entreprise Server utilise pour fournir des services aux utilisateurs. Certaines sont facultatives dans la mesure où elles sont uniquement nécessaires pour prendre en charge certaines fonctionnalités, et elles peuvent être ignorées si ces fonctionnalités ne sont pas souhaitées. Les enregistrements DNS requis pour l’accès interne uniquement sont dans la première table, et un déploiement qui permet l’accès interne et externe nécessitera des enregistrements des deux tables.

**Mappages DNS internes**

|Type d’enregistrement|Value (Valeur)|Résolu en|Objectif|Obligatoire|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Nom de domaine complet du pool frontal  <br/> *FE-pool. <span> </span>Contoso<span></span>. com*   |Adresses IP de serveur de pool frontal  <br/>  DNS LB vers *192.168.21.122 192.168.21.123 192.168.21.124*   |Équilibrage de la charge DNS des pools frontaux. Mappe le nom du pool frontal à un ensemble d’adresses IP.  <br/> Consultez la rubrique [déploiement de l’équilibrage de charge DNS sur les pools frontaux et les pools de directeurs](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | Nom de domaine complet (FQDN) de chaque serveur frontal ou serveur Standard Edition d’un pool ou d’un serveur autonome <br/>  *Entre FE01. <span> </span>contoso. <span> </span>FE02 com. <span> </span>Contoso<span></span>. com FE03. <span> </span>Contoso<span></span>. com*   |IP correspondant de chaque serveur  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mappe le nom du serveur à son adresse IP.   |v   |
|A/AAAA   |Nom de domaine complet du remplacement des services Web internes du pool d’entreprise  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |CHARGE matérielle VIP pour les services Web internes du serveur frontal  <br/> *192.168.21.120*   |Obligatoire pour activer le trafic Web client vers serveur, tel que le téléchargement de Skype entreprise Web App. Également requis pour les clients mobiles.   |v   |
|A/AAAA   |Nom de domaine complet du remplacement des services Web externes du pool d’entreprise  <br/> *Web-ext.<span></span>Contoso<span></span>. com*   |CHARGE matérielle VIP pour les services Web externes de serveur frontal  <br/>*68.123.56.90*   |Obligatoire pour activer le trafic Web client vers serveur, tel que le téléchargement de Skype entreprise Web App. Obligatoire si les clients mobiles peuvent résoudre le DNS en interne. Peut être résolu en adresse IP de proxy inverse DMZ ou IP Internet.   ||
|A/AAAA   | Nom de domaine complet SQL Server du serveur principal <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |adresse IP du serveur  <br/> *192.168.11.90*   |Mappe le nom du serveur pour un serveur SQL principal utilisant le pool frontal vers son adresse IP   ||
|A/AAAA   |Nom de domaine complet du serveur miroir SQL Server du serveur principal  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |adresse IP du serveur  <br/> *192.168.11.91*   |Mappe le nom de serveur pour un serveur miroir SQL principal travaillant avec le pool frontal sur son adresse IP   ||
|A/AAAA   |Nom de domaine complet du pool directeur  <br/>**Remarque :** Non applicable lors de l’utilisation d’un serveur directeur autonome <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Adresses IP du pool directeur  <br/> DNS LB vers *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Équilibrage de la charge DNS des serveurs du pool directeur. Mappe le nom du pool pour le pool directeur à une adresse IP, consultez la rubrique déploiement de l' [équilibrage de charge DNS sur les pools frontaux et les pools de directeurs](load-balancing.md#BK_FE_Dir) <br/> Un directeur peut authentifier un utilisateur et est facultatif.   ||
|A/AAAA   |Nom de domaine complet du directeur   |Adresse IP du serveur de chaque serveur directeur   |Mappe le nom du pool pour le directeur à une adresse IP, consultez la rubrique déploiement de l' [équilibrage de charge DNS sur les pools frontaux et les pools de directeurs](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |Nom de domaine complet du pool de serveurs de médiation   |Adresses IP du pool   |Le rôle de serveur de médiation est facultatif. Vous pouvez colocaliser les services fournis par un serveur de médiation sur le serveur ou le pool frontal. Voir [utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Nom de domaine complet du serveur de médiation   |Adresse IP du serveur   |Vous pouvez colocaliser les services fournis par un serveur de médiation sur le serveur ou le pool frontal. Voir [utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Nom de domaine complet du serveur de conversation permanente   |Adresse IP du serveur de conversation permanente   |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente et est facultatif.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>Contoso<span></span>. com*   |Adresse IP du pool frontal charge matérielle ou adresse IP du directeur  <br/>  192.168.21.121  |Service1 de découverte automatique interne, requis pour la prise en charge de la mobilité. Si le DNS interne est utilisé pour la résolution des périphériques mobiles, il doit pointer vers l’adresse IP externe ou l’adresse IP virtuelle DMZ.  <br/> Pour les services Web, nous avons besoin d’charge matérielle sur le pool frontal car HTTPs ne peuvent pas exploiter le système DNS. Pour le pool frontal ou le pool Directeur, il doit être résolu en un VIP charge matérielle ou une adresse IP normale pour un serveur Standard Edition ou un serveur directeur autonome.   |v   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |Nom de domaine complet du pool FE charge matérielle ou nom de domaine complet du directeur  <br/> Web-int.<span></span>Contoso<span></span>. com   |Service1 de découverte automatique interne <br/> Si vous le souhaitez, vous pouvez l’implémenter en tant que CNAMe au lieu d’un enregistrement A.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Adresses IP des serveurs de pools frontaux (ou à une adresse IP de chaque directeur)  <br/>  DNS LB vers *192.168.21.122 192.168.21.123 192.168.21.124*   |Obligatoire pour la configuration automatique, voir [Walkthrough of Skype for Business clients Locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un ou des enregistrements pointant vers les serveurs de pool frontal ou les serveurs directeurs sur le réseau interne, ou le service Edge d’accès lorsque le client est externe   |&#x2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain\>* <br/> ucupdates-r2. * <span> </span>Contoso<span></span>. com*  |VIP de pool charge matérielle FE ou adresse IP du pool directeur charge matérielle ou IP de serveur SE/directeur  <br/>  192.168.21.121  |Le déploiement de cet enregistrement est facultatif &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Port 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Port 5061  |Nom de domaine complet du pool frontal  <br/>*FE-pool. <span> </span>Contoso<span></span>. com*  |Permet à l’utilisateur interne de se connecter automatiquement 1 au serveur/pool frontal ou au serveur/pool SE qui authentifie et redirige les demandes client de connexion.  |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet du pool frontal  <br/>_FE-pool. <span> </span>Contoso<span></span>. com_  |&#x2776; d’accès des utilisateurs internes  |&#x2777;  |
|SRV   | \_Protocole. \_UDP. * \<sipdomain\> * <br/> \_Protocole. \_UDP. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet FQDN  <br/> north-america.pool.ntp.org   |Source NTP requise pour les appareils Lync Phone Edition   |Cela est nécessaire pour prendre en charge les combinés de bureau.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  | Nom de domaine complet du service Edge d’accès <br/> EdgePool-int.<span></span>*Contoso<span></span>. com*  |Créez un enregistrement SRV pour chaque domaine SIP ayant des clients Windows Phone Mobile ou IOS.   |Pour la prise en charge des clients mobiles   |
|A/AAAA   |URL d’administration  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP de pool FE charge matérielle  <br/> 192.168.21.121   |Panneau de configuration de Skype entreprise Server, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de la réunion  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP de pool FE charge matérielle  <br/> 192.168.21.121   |Réunions en ligne, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de rendez-vous  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP de pool FE charge matérielle  <br/> 192.168.21.121   |Conférence rendez-vous, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |nom de domaine complet des services Web internes  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP de pool FE charge matérielle  <br/> 192.168.21.121   |Service Web Skype entreprise utilisé par Skype entreprise Web App   ||
|A/AAAA   |Nom de domaine complet du pool Office Web Apps Server  <br/> App. <span> </span>Contoso<span></span>. com   | Adresse IP virtuelle du pool Office Web Apps Server <br/> 192.168.1.5   |Définit le nom de domaine complet du pool Office Web Apps Server   ||
|A/AAAA   | Nom de domaine complet Web interne <br/> Web-int.<span></span>Contoso<span></span>. com   | Adresse VIP du pool frontal <br/> 192.168.21.121   |Définit le nom de domaine complet Web interne utilisé par Skype entreprise Web App  <br/> Si vous utilisez l’équilibrage de charge DNS sur ce pool, votre pool frontal et votre batterie de serveurs Web internes ne peuvent pas avoir le même nom de domaine complet.   ||

&#x2776; utilisé par un client pour détecter le serveur frontal ou le pool frontal, et s’authentifier et se connecter en tant qu’utilisateur. Pour plus d’informations, reportez-vous à la [rubrique Walkthrough of Skype for Business clients Locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; cela est uniquement requis pour prendre en charge les clients hérités avant Lync 2013 et les combinés de bureau.

&#x2778; dans le cas où un périphérique de communications unifiées est activé, mais qu’un utilisateur n’a jamais ouvert de session sur l’appareil, l’enregistrement A permet à ce dernier de découvrir le service Web de mise à jour des périphériques hébergeant le serveur et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.

Le diagramme suivant montre un exemple qui inclut des enregistrements DNS internes et externes, ainsi que de nombreux enregistrements présentés dans les tables avoisinantes :

**Diagramme de réseau Edge utilisant des adresses IPv4 publiques**

![exemple de diagramme de réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mappages DNS du réseau de périmètre (interfaces internes et externes)**

|Type d’enregistrement|Value (Valeur)|Résolu en|Objectif|Obligatoire|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Nom de domaine complet du pool de serveur Edge interne  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Adresses IP de pool de serveurs Edge internes  <br/> 172.25.33.10, 172.25.33.11   |Adresses IP de l’interface interne du pool Edge consolidé   |v   |
|A/AAAA   |Nom de domaine complet du serveur Edge  <br/>*Cons-1. <span> </span>Contoso<span></span>. com*  |IP de serveur côté interne pour un serveur dans le pool de serveurs Edge  <br/> 172.25.33.10   |Créez un enregistrement pour chaque serveur du pool avec le nom de domaine complet (FQDN) du serveur pointant vers son adresse IP de nœud de serveur interne dans le pool, voir [équilibrage de la charge DNS sur les pools de serveurs Edge](load-balancing.md#BK_Edge).   |v   |
|A/AAAA   |Nom de domaine complet du pool de services Edge d’accès  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes du pool de services Edge d’accès  <br/> 131.107.16.10, 131.107.16.11   |Le service Edge d’accès fournit un point de connexion unique sécurisé qui est utilisé pour le trafic SIP (Session Initiation Protocol) à la fois sortant et entrant.   |v   |
|A/AAAA   |Nom de domaine complet du pool de services Edge de conférence Web  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes du service Edge de conférence Web  <br/> 131.107.16.90, 131.107.16.91   |Le service Edge de conférence Web permet aux utilisateurs externes de participer à des réunions hébergées sur votre environnement Skype entreprise Server interne.   |v   |
|A/AAAA   |*av.\<SIP-Domain\> * Nom de domaine complet du pool <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes de serveur Edge A/V  <br/> 131.107.16.170, 131.107.16.171   |Le service Edge A/V rend l’audio, la vidéo, le partage d’application et le transfert de fichiers accessibles aux utilisateurs externes.   |v   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Nom de domaine complet du pool Edge d’accès externe  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Localise le pool de serveurs Edge. Voir [Walkthrough of Skype for Business clients Locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_SIP. \_TLS. * \<sipdomain\> * <br/>\_SIP. \_TLS. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet du serveur Edge d’accès externe  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Utilisé pour l’accès des utilisateurs externes. Voir [Walkthrough of Skype for Business clients Locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet du serveur Edge d’accès externe  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Utilisé pour la Fédération et la connectivité PIC   |&#x2776;  |
|SRV   |\_XMPP-Server. \_TCP. *<sipdomain\> * <br/>\_XMPP-Server. \_TCP. * <span> </span>Contoso<span></span>. com*  |Nom de domaine complet du serveur Edge d’accès externe  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Le service proxy XMPP accepte et envoie les messages XMPP (extensible Messaging and Presence Protocol) vers et depuis les partenaires fédérés XMPP configurés.   |Y, pour déployer la Fédération, sinon facultatif  <br/> Non disponible dans Skype entreprise Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |Nom de domaine complet du serveur Edge d’accès externe  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Pour prendre en charge le service de notifications et le service de notifications d’Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP. &#x2778;  ||
|A/AAAA   |Nom de domaine complet externe des services Web du pool frontal  <br/>*Web-ext.<span></span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, proxys pour l’adresse IP des services Web externes pour votre pool frontal &#x2776; <br/> proxy 131.107.155.1 vers 192.168.21.120   |Interface externe de pool frontal utilisée par Skype entreprise Web App   |v   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, résolution de l’adresse IP virtuelle des services Web externes pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous ne disposez pas d’un directeur &#x2777; <br/> proxy 131.107.155.1 vers 192.168.21.120   | Enregistrement externe pour la découverte automatique de client, également utilisé par Mobility, Skype entreprise Web App et Scheduler Web App, résolu par le serveur proxy inverse <br/> Pour prendre en charge le service de notifications et le service de notifications d’Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP doté de clients Microsoft Lync mobile. 3   |v   |
|A/AAAA   |satisfaction. * \<sipdomain\>* <br/> satisfaction. * <span> </span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, résolue vers l’interface Web externe pour le pool frontal  <br/> proxy 131.107.155.1 vers 192.168.21.120   |Proxy vers le service Web Skype entreprise  <br/> Afficher les [URL simples](dns.md#BK_Simple)  |v   |
|A/AAAA   |appels entrants.*\<sipdomain\>* <br/> appels entrants.*<span></span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, proxys pour l’interface Web externe pour le pool frontal  <br/> proxy 131.107.155.1 vers 192.168.21.120   |Proxy vers le service Web Skype entreprise  <br/> Afficher les [URL simples](dns.md#BK_Simple)  |v   |
|A/AAAA   |Nom de domaine complet du pool Office Web Apps Server  <br/> App. <span> </span>Contoso<span></span>. com   | Adresse IP publique de proxy inverse, proxys pour l’interface Web externe pour Office Web Apps Server <br/> proxy 131.107.155.1 vers 192.168.1.5   | Adresse IP virtuelle du pool Office Web Apps Server <br/> 192.168.1.5   |Définit le nom de domaine complet du pool Office Web Apps Server   |

&#x2776; requis pour déployer la Fédération, sinon, facultatif.

&#x2777; utilisé par un client pour détecter le serveur frontal ou le pool frontal, et s’authentifier et se connecter en tant qu’utilisateur.

&#x2778; cette exigence s’applique uniquement aux clients sur des appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas de notification de transmission.

 Pour plus d’informations sur les serveurs Edge et les réseaux de périmètre, voir le contenu de [planification DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) du serveur Edge.

> [!IMPORTANT]
> Skype entreprise Server prend en charge l’utilisation de l’adressage IPv6. Pour plus d’informations, reportez-vous à la rubrique [plan for IPv6 in Skype for Business](ipv6.md) .

> [!IMPORTANT]
> Pour plus d’informations sur les noms de domaine complets, consultez la rubrique [DNS Basics](basics.md).

****
 DNS<a name="BK_split"> </a> split brain

Le DNS split brain est une configuration DNS dans laquelle vous avez deux zones DNS avec le même espace de noms. La première zone DNS gère les requêtes internes, tandis que la deuxième gère les demandes externes, comme mentionné dans les tableaux suivants. Pour plus d’informations à ce sujet [, voir split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considérations hybrides
<a name="BK_Hybrid"> </a>

Si vous envisagez d’avoir des utilisateurs hébergés en ligne et des sites hébergés sur site, reportez-vous à l’article de planification de connectivité hybride [Skype entreprise server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Vous devrez configurer le DNS comme normal pour Skype entreprise Server 2015 et ajouter des enregistrements DNS supplémentaires.

Vous devez également vous reporter à « URL et plages d’adresses IP Office 365 [https://aka.ms/o365ips](https://aka.ms/o365ips) » sur pour vérifier que vos utilisateurs auront accès aux ressources en ligne dont ils ont besoin.

## <a name="simple-urls"></a>URL simples
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource Web qui spécifie son emplacement sur un réseau informatique et un protocole utilisé pour le récupérer.

Skype entreprise Server prend en charge l’utilisation de trois URL simples pour accéder aux services :

- La **réunion** est utilisée comme URL de base pour toutes les conférences du site. Un exemple d’URL simple de réunion est https :<span></span>//<span></span>réunion. <span> </span>Contoso<span></span>. com. Une URL pour une réunion particulière peut être https :<span></span>//<span></span>réunion. <span> </span>Contoso<span></span>. com/_NomUtilisateur_/7322994.

    Avec l’URL simple de réunion, les liens permettant de joindre des réunions sont faciles à comprendre et à communiquer.

- Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous. Cette page affiche les numéros d’accès de conférence avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion du numéro d’identification personnel ( PIN) et les informations de conférence affectées. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Un exemple de l’URL simple Dial-in est https://<span></span>. <span> </span>Contoso<span></span>. com.

- L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Skype entreprise Server. À partir de n’importe quel ordinateur dans les pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration de Skype entreprise Server en tapant l’URL simple administrateur dans un navigateur. L’URL simple d’administration est interne à votre organisation. Un exemple d’URL simple admin est https://<span></span>admin. <span> </span>Contoso<span></span>. com.

Les URL simples sont décrites plus en détail dans [DNS Requirements for simple URL in Skype for Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS par rôle de serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme vous le souhaitez, mais les rendre explicites et refléter leur fonction dans le système.

### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools individuels

Ces exigences d’enregistrement générique s’appliquent à tous les rôles serveur utilisés par Skype entreprise. Un pool est un ensemble de serveurs qui exécutent les mêmes services qui fonctionnent ensemble pour gérer les demandes des clients qui leur sont envoyées par le biais d’un programme d’équilibrage de charge. Pour plus d’informations, voir [Load Balancing Requirements for Skype for Business](load-balancing.md)

**Exigences liées aux enregistrements DNS pour les rôles serveur/pool (suppose l’équilibrage de la charge DNS)**

|Scénario de déploiement|Enregistrement DNS requis|
|:-----|:-----|
|Un serveur :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal   |Enregistrement A interne associant le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole. <span> </span>10.10.10.0<span></span>de contoso. com   |
|Pool  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal   |Un enregistrement interne A qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur dans le pool à son adresse IP.  <br/>**Exemple** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>10.10.10.2<span></span>de contoso. com  <br/> Plusieurs enregistrements internes A qui résolvent le nom de domaine complet (FQDN) du pool vers les adresses IP des nœuds de serveur dans le pool.  <br/>**Exemple** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>10.10.10.2<span></span>de contoso. com   |

### <a name="edge-server-specific-dns-topics"></a>Rubriques DNS spécifiques à un serveur Edge

 Pour planifier le déploiement du serveur Edge, consultez la section [plan for Edge Server Deployments in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et [Advanced Edge Server DNS Planning for Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , qui comporte les sections suivantes :

- [Récupération d’urgence DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [équilibrage de charge DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuration automatique sans DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Procédure pas à pas pour les clients Skype entreprise qui recherchent des services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


