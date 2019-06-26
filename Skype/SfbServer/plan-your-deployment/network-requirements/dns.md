---
title: Configuration requise pour le service DNS pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé: pour plus d’informations sur l’implémentation de Skype entreprise Server, reportez-vous à la section Considérations relatives au DNS.'
ms.openlocfilehash: 5e6bb5866cfc52dc02a1fc48c19b1f43af6077f7
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221223"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Configuration requise pour le service DNS pour Skype entreprise Server

**Résumé:** Pour plus d’informations sur l’implémentation de Skype entreprise Server, reportez-vous à la section Considérations en matière de DNS.

Cet article n’aborde que la planification du DNS pour les déploiements de Skype entreprise Server sur le réseau local d’une organisation. Pour Skype entreprise Online, reportez-vous à la section «URL et plages [https://aka.ms/o365ips](https://aka.ms/o365ips)d’adresses IP Office 365» à l’adresse.

Un serveur DNS (Domain Name Service) mappe les noms d’hôte (par<span> </span> exemple, www). Contoso<span></span>. com, vraisemblablement un serveur Web) vers des adresses IP (par exemple, 10.10.10.10). Il aide les clients et les serveurs interdépendants à communiquer entre eux sur le réseau. Lorsque vous configurez une implémentation de Skype entreprise Server 2015, vous devez vous assurer que le mappage des nouveaux noms de serveurs (reflétant généralement le rôle sur lequel ils seront pris en charge) correspond aux adresses IP auxquelles elles sont affectées.

Même si l’utilisation de l' [outil de planification de Skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357)peut sembler une véritable gageure, vous pouvez le faire en premier pour la planification. Après avoir consulté les questions de l’Assistant sur les fonctionnalités que vous envisagez d’utiliser, pour chaque site que vous définissez, vous pouvez afficher le rapport DNS dans le rapport d’administration latérale et utiliser les informations répertoriées dans cet État pour créer vos enregistrements DNS. Pour plus d’informations, consultez [la section examen du rapport DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)pour plus d’informations sur les noms et les adresses IP utilisés. Gardez à l’esprit que vous pouvez exporter le rapport d’administration Edge vers une feuille de calcul Excel et que le rapport DNS est l’une des feuilles de calcul du fichier. Bien que l’outil inclut [des fonctionnalités déconseillées dans Skype entreprise Server 2019](../../../SfBServer2019/deprecated.md), il peut toujours être utilisé pour créer un plan initial si ces fonctionnalités ne sont pas sélectionnées.

Lorsque vous installez une nouvelle mise en œuvre comme décrit dans [créer des enregistrements DNS pour Skype entreprise Server](../../deploy/install/create-dns-records.md) et créer votre topologie pour Skype entreprise Server, nous avons conscience que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées à Windows Server. 2016 ou un package DNS tiers, nous mettrons à jour les discussions dans cet article plutôt que spécifiques. Nous détaillons les conditions requises et vous laissons décider de la méthode pour les réunir.

Les tableaux suivants sont utiles pour les administrateurs Skype entreprise, Lync et Office Communications suite. Si le tableau s'avère complexe, les sections et articles à venir apporteront des précisions sur les concepts suivants :

## <a name="summary-tables"></a>Tableaux de synthèse
<a name="BK_Summary"> </a>

Les tableaux suivants illustrent les enregistrements DNS utilisés par Skype entreprise Server pour fournir des services aux utilisateurs. Certains d'entre eux sont facultatifs, car ils permettent uniquement de prendre en charge certaines fonctionnalités ; vous pouvez donc les ignorer si vous ne souhaitez pas utiliser ces fonctionnalités. Les enregistrements DNS requis uniquement pour l'accès interne figurent dans le premier tableau ; un déploiement permettant l'accès interne comme externe requiert les enregistrements des deux tableaux.

**Mappages DNS internes**

|Type d'enregistrement|Valeur|Résolu en|Objectif|Obligatoire|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Nom de domaine complet (FQDN) du pool frontal  <br/> *Pool de FE. <span> </span>Contoso<span></span>. com*   |Adresses IP du serveur pool frontal  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*   |Équilibrage de charge DNS des pools frontaux Mappe le nom du pool frontal vers un ensemble d'adresses IP. <br/> Reportez-vous à la section [Déploiement de l'équilibrage de la charge DNS dans les pools frontaux et les pools directeurs](load-balancing.md#BK_FE_Dir).  |Y   |
|A/AAAA   | Nom de domaine complet (FQDN) de chaque serveur frontal ou serveur d’édition standard dans un pool ou serveur autonome <br/>  *FE01. <span> </span>contoso. <span> </span>FE02 com. <span> </span>Contoso<span></span>. com FE03. <span> </span>Contoso<span></span>. com*   |IP correspondant de chaque serveur  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mappe le nom du serveur vers son adresse IP.   |Y   |
|A/AAAA   |FQDN de remplacement de services Web internes pour pool d'entreprise  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |HLB VIP pour les services Web internes du serveur principal  <br/> *192.168.21.120*   |Requis pour autoriser le trafic Web du client vers le serveur, par exemple pour télécharger l’application Web Skype entreprise. Également requis pour les clients mobiles.   |Y   |
|A/AAAA   |FQDN de remplacement de services Web externes pour pool d'entreprise  <br/> *Web-ext.<span></span>Contoso<span></span>. com*   |HLB VIP pour les services Web externes du serveur frontal  <br/>*68.123.56.90*   |Requis pour autoriser le trafic Web du client vers le serveur, par exemple pour télécharger l’application Web Skype entreprise. Requis si les clients mobiles résoudront le DNS en interne. Peut être converti en adresse IP Internet ou adresse IP de proxy inverse DMZ.   ||
|A/AAAA   | Nom de domaine complet SQL Server du serveur principal <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |Adresse IP de serveur  <br/> *192.168.11.90*   |Mappe le nom du serveur pour un serveur SQL Server principal travaillant avec le pool frontal à son adresse IP.   ||
|A/AAAA   |Nom de domaine complet (FQDN) SQL Server en miroir du serveur principal  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |Adresse IP de serveur  <br/> *192.168.11.91*   |Mappe le nom de serveur d’un serveur miroir SQL principal fonctionnant avec le pool frontal et son adresse IP.   ||
|A/AAAA   |Nom de domaine complet du pool de réalisateur  <br/>**Remarque:** Non applicable lors de l’utilisation d’un serveur Director autonome <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Adresses IP du pool de réalisateurs  <br/> *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Équilibrage de charge DNS des serveurs du pool de directeurs. Mappe le nom du pool pour le pool de directeurs à une adresse IP, en vous reportez à la section déploiement de l' [équilibrage de charge DNS pour les pools front-end et les pools de réalisateur](load-balancing.md#BK_FE_Dir) <br/> Un pool directeur peut authentifier un utilisateur et est facultatif.   ||
|A/AAAA   |Nom de domaine complet du réalisateur   |Adresse IP du serveur de chaque serveur Director   |Mappe le nom du pool au directeur auprès d’une adresse IP, voir déploiement de l' [équilibrage de charge DNS pour les pools front-end et les pools de réalisateur](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |Nom de domaine complet du pool de serveurs de médiation   |Adresses IP de pools   |Le rôle du serveur de médiation est facultatif. Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Voir [utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Nom de domaine complet du serveur de médiation   |Adresse IP de serveur   |Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Voir [utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Nom de domaine complet du serveur de chat permanent   |Adresse IP du serveur de chat permanent   |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente mais reste facultative.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>Contoso<span></span>. com*   |Adresse VIP du pool frontal de HLB ou du directeur  <br/>  192.168.21.121  |Le Service1 de découverte automatique interne, requis pour la prise en charge de la mobilité. Si le DNS interne est utilisé pour résoudre les appareils mobiles, il doit pointer vers l’adresse IP externe ou le protocole VIP de la DMZ.  <br/> Pour les services Web, nous avons besoin de HLB sur le pool frontal, car HTTPs ne peuvent pas utiliser DNS. Pour le pool frontal ou le pool de réalisateurs, cela devrait résoudre vers une adresse VIP HLB ou une adresse IP standard pour un serveur Standard Edition Server ou un serveur Director autonome.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |FQDN de pool HLB FE ou FQDN de serveur directeur  <br/> Web-int.<span></span>Contoso<span></span>. com   |Service1 de découverte automatique interne <br/> Si vous le souhaitez, vous pouvez l'implémenter comme CNAME (nom canonique) au lieu d'un enregistrement A.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Adresses IP du serveur pool frontal (ou à une adresse IP de Director)  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*   |Requis pour la configuration automatique, voir [procédure pas à pas pour les clients qui recherchent des services dans Skype entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Enregistrement ou enregistrement qui pointent vers les serveurs du pool frontal ou les serveurs directeurs du réseau interne, ou le service Edge d’accès lorsque le client est externe   |&#x2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain\>* <br/> ucupdates-r2. * <span> </span>Contoso<span></span>. com*  |Adresse VIP de pool HLB FE ou VIP HLB de pool de serveurs directeur, ou IP de serveur directeur/SE  <br/>  192.168.21.121  |Le déploiement de cet enregistrement est facultatif &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Port 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Port 5061  |Nom de domaine complet (FQDN) du pool frontal  <br/>*Pool de FE. <span> </span>Contoso<span></span>. com*  |Permet la connexion automatique interne des utilisateurs 1 au serveur/pool frontal ou au serveur/pool SE, qui authentifie et redirige les demandes client de connexion.    |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet (FQDN) du pool frontal  <br/>_Pool de FE. <span> </span>Contoso<span></span>. com_  |&#x2776; d’accès des utilisateurs internes  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<sipdomain\> * <br/> \_NTP. \_UDP. <span> </span> *Contoso<span></span>. com*  |FQDN de serveur de temps  <br/> north-america.pool.ntp.org   |Source NTP requise pour les appareils Lync Phone Edition   |Cela est nécessaire pour prendre en charge les combinés de bureau.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  | Nom de domaine complet du service Edge d’accès <br/> EdgePool-int.<span></span>*Contoso<span></span>. com*  |Créez un enregistrement SRV pour chaque domaine SIP comptant des clients mobiles iOS ou Windows Phone.   |Prise en charge des clients mobiles   |
|A/AAAA   |URL d'administration  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Panneau de configuration Skype entreprise Server, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de réunion  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Réunions en ligne, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL d'accès à distance  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Conférence rendez-vous, voir [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN des services Web internes  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Service Web Skype entreprise utilisé par Skype entreprise Web App   ||
|A/AAAA   |Nom de domaine complet (FQDN) du pool Office Web Apps Server  <br/> App. <span> </span>Contoso<span></span>. com   | Adresse VIP du pool Office Web Apps Server <br/> 192.168.1.5   |Définit le nom de domaine complet (FQDN) du pool Office Web Apps Server   ||
|A/AAAA   |  FQDN web interne <br/> Web-int.<span></span>Contoso<span></span>. com   | Adresse VIP du pool frontal <br/> 192.168.21.121   |Définit le FQDN Web interne utilisé par Skype entreprise Web App  <br/> Si vous avez recours à l'équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs Web internes ne peuvent pas avoir le même nom de domaine complet.   ||

&#x2776; utilisé par un client pour détecter le serveur frontal ou le pool frontal, et être authentifié et connecté en tant qu’utilisateur. Pour plus d’informations, c’est dans la [procédure pas à pas pour les clients qui recherchent des services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; cela est requis uniquement pour prendre en charge les clients hérités avant Lync 2013 et les combinés de bureau.

&#x2778; dans le cas où un appareil de communications unifiées est activé, mais qu’aucun utilisateur ne s’est connecté à l’appareil, l’enregistrement A permet à l’appareil de détecter le service Web de mise à jour de l’appareil d’hébergement du serveur et d’obtenir les mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.

Le diagramme suivant illustre un exemple incluant des enregistrements DNS à la fois internes et externes, ainsi que de divers enregistrements indiqués dans les tableaux de cet article : 

**Diagramme réseau Edge utilisant des adresses IPv4 publiques**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mappages DNS du réseau de périmètre (interfaces internes et externes)**

|Type d'enregistrement|Valeur|Résolu en|Objectif|Obligatoire|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Nom de domaine complet du pool d’arête interne  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Adresses IP du pool de bords internes  <br/> 172.25.33.10, 172.25.33.11   |Adresses IP de l'interface interne du pool Edge consolidé   |Y   |
|A/AAAA   |Nom de domaine complet du serveur de périphérie  <br/>*Cons-1. <span> </span>Contoso<span></span>. com*  |Adresse IP du serveur interne pour un serveur dans le pool de périphériques  <br/> 172.25.33.10   |Créer un enregistrement pour chaque serveur dans le pool avec le nom de domaine complet (FQDN) du serveur pointant vers son adresse IP de nœud serveur interne dans le pool, voir [équilibrage de charge DNS sur les pools de serveurs de périphérie](load-balancing.md#BK_Edge)   |Y   |
|A/AAAA   |Nom de domaine complet du pool de services Edge Access  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes du pool de services Edge Access  <br/> 131.107.16.10, 131.107.16.11   |Le service Edge d’accès fournit un point de connexion unique et approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.   |Y   |
|A/AAAA   |Nom de domaine complet (FQDN) du pool de services Edge  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes du service Edge de conférence Web  <br/> 131.107.16.90, 131.107.16.91   |Le service Edge de conférence Web permet aux utilisateurs externes de rejoindre des réunions hébergées sur votre environnement Skype entreprise Server interne.   |Y   |
|A/AAAA   |*av.\<SIP-Domain\> * Nom de domaine complet du pool <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Adresses IP externes de serveur Edge A/V  <br/> 131.107.16.170, 131.107.16.171   |Le service d’Edge A/V effectue des opérations audio, vidéo, de partage d’application et de transfert de fichiers aux utilisateurs externes.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |FQDN du pool Edge d'accès externe  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Recherche le pool de serveurs Edge. Voir [procédure pas à pas pour les clients recherchant des services Skype entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_TLS. * \<sipdomain\> * <br/>\_SIP. \_TLS. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet Edge Access  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Utilisé pour l'accès externe des utilisateurs. Voir [procédure pas à pas pour les clients recherchant des services Skype entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  |Nom de domaine complet Edge Access  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Utilisé pour la fédération et la connectivité PIC   |&#x2776;  |
|SRV   |\_XMPP-serveur. \_TCP. *<sipdomain\> * <br/>\_XMPP-serveur. \_TCP. * <span> </span>Contoso<span></span>. com*  |Nom de domaine complet Edge Access  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Le service proxy XMPP accepte et envoie les messages de la messagerie électronique extensible (XMPP) vers et depuis les partenaires fédérés de XMPP configurés.   |Oui, pour déployer la fédération ; sinon, facultatif  <br/> Non disponible dans Skype entreprise Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |Nom de domaine complet Edge Access  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Pour prendre en charge les services de notifications de transmission et de notifications de type Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP. &#x2778;  ||
|A/AAAA   |Nom de domaine complet des services Web de réserve externe  <br/>*Web-ext.<span></span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, proxys vers le VIP des services Web externes pour votre pool frontal &#x2776; <br/> 131.107.155.1 proxy to 192.168.21.120   |Interface externe de pool frontal utilisée par Skype entreprise Web App   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, résolue vers l’adresse VIP des services Web externes de votre pool de Director, si vous en avez une, ou si vous n’avez pas de réalisateur &#x2777; <br/> 131.107.155.1 proxy to 192.168.21.120   | Enregistrement externe pour la découverte automatique du client, également utilisé par la mobilité, Skype entreprise Web App et le planificateur Web App, résolu par le serveur proxy inverse <br/> Pour prendre en charge les services de notifications de transmission et de notifications de type Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP doté de clients mobiles Microsoft Lync. 3  |Y   |
|A/AAAA   |correspondre. * \<sipdomain\>* <br/> correspondre. * <span> </span>Contoso<span></span>. com*  |Adresse IP publique de proxy inverse, résolue en interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy to 192.168.21.120   |Proxy pour le service Web Skype entreprise  <br/> Voir la section [URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |appel entrant.*\<sipdomain\>* <br/> appel entrant.*<span></span><span></span>contoso. com*  |Adresse IP publique de proxy inverse, proxys vers l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy to 192.168.21.120   |Proxy pour le service Web Skype entreprise  <br/> Voir la section [URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Nom de domaine complet (FQDN) du pool Office Web Apps Server  <br/> App. <span> </span>Contoso<span></span>. com   | Adresse IP publique de proxy inverse, proxys vers l’interface Web externe pour Office Web Apps Server <br/> 131.107.155.1 proxy pour 192.168.1.5   | Adresse VIP du pool Office Web Apps Server <br/> 192.168.1.5   |Définit le nom de domaine complet (FQDN) du pool Office Web Apps Server   |

&#x2776; requis pour déployer la Fédération, sinon facultatif.

&#x2777; utilisé par un client pour détecter le serveur frontal ou le pool frontal, et être authentifié et connecté en tant qu’utilisateur.

&#x2778; cette obligation s’applique uniquement aux clients utilisant des appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.

 Pour plus d’informations sur les serveurs de périphérie et les réseaux de périmètre, voir le contenu de [planification DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) du serveur Edge.

> [!IMPORTANT]
> Skype entreprise Server prend en charge l’utilisation de l’adressage IPv6. Pour plus d'informations, consultez l'article [Plan for IPv6 in Skype for Business](ipv6.md).

> [!IMPORTANT]
> Pour plus d'informations sur les FQDN, consultez l'article [DNS basics](basics.md). 

**Partage du DNS** 
 <a name="BK_split"> </a> du cerveau

Le système DNS split brain est une configuration DNS dans laquelle vous avez deux zones DNS avec le même espace de noms. Dans la première zone DNS, les requêtes internes sont gérées, tandis que la seconde gère les demandes externes, comme indiqué dans les tableaux ci-dessous. Pour plus d’informations à ce sujet [, voir DNS fractionné-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Remarque sur les environnements hybrides
<a name="BK_Hybrid"> </a>

Si vous envisagez de faire en sorte que certains utilisateurs soient hébergés en ligne et qu’ils soient hébergés en local, reportez-vous à l’article planification de connectivité hybride [Skype entreprise server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Vous devez configurer le système DNS comme standard pour Skype entreprise Server 2015 et ajouter des enregistrements DNS supplémentaires.

Vous devez également vous référer aux URL et plages [https://aka.ms/o365ips](https://aka.ms/o365ips) d’adresses IP Office 365 pour vérifier que vos utilisateurs ont accès aux ressources en ligne nécessaires.

## <a name="simple-urls"></a>URL simples 
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource Web qui spécifie son emplacement dans un réseau informatique et un protocole utilisé pour le récupérer. 

Skype entreprise Server prend en charge l’utilisation des trois URL «simples» pour accéder à des services:

- **Meet** est l'URL de réunion de base pour toutes les conférences dans le site. Voici un exemple d’URL simple de la réunion:<span></span>//<span></span>rencontre. <span> </span>Contoso<span></span>. com. Une URL pour une réunion particulière peut être https:<span></span>//<span></span>se réunir. <span> </span>Contoso<span></span>. com/_nom_utilisateur_/7322994.

    Avec l'URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre et à communiquer.

- Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous. Cette page présente les numéros de conférence rendez-vous avec les langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées), les commandes DTMF en conférence et prend en charge la gestion du numéro d’identification personnel ( Code confidentiel) et informations de conférence affectées. L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Par exemple, l’URL d’accès à la Conférence rendez-vous est https://<span></span>. <span> </span>Contoso<span></span>. com.

- L' **administrateur** permet d’accéder rapidement au panneau de configuration Skype entreprise Server. À partir de n’importe quel ordinateur au sein des pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration Skype entreprise Server en entrant l’URL simple d’administration dans un navigateur. L’URL simple Admin est interne à votre organisation. Un exemple d’URL simple d’administration est https://<span></span>admin. <span> </span>Contoso<span></span>. com.

Pour plus d’informations sur la [Configuration requise de DNS dans Skype entreprise Server](simple-urls.md), voir les URL simples.

## <a name="dns-by-server-role"></a>DNS par rôle de serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme bon vous semble, faciles à mémoriser et reflétant leur fonction dans le système.

### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools spécifiques

Ces exigences relatives aux enregistrements génériques s’appliquent à tous les rôles de serveur utilisés par Skype entreprise. Un pool est un ensemble de serveurs exécutant les mêmes services qui fonctionnent ensemble pour traiter les demandes client qu'ils reçoivent via un équilibreur de charge. Pour plus d'informations, consultez la rubrique [Load balancing requirements for Skype for Business](load-balancing.md).

**Conditions requises relatives aux enregistrements DNS pour les rôles de serveur/pool (avec équilibrage de charge DNS)**

|Scénario de déploiement|Enregistrement DNS requis|
|:-----|:-----|
|Un serveur :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal   |Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool :  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal    |Un enregistrement interne A qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur dans le pool sur son adresse IP.  <br/>**Exemple** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Plusieurs enregistrements internes A qui résolvent le nom de domaine complet (FQDN) du pool sur les adresses IP des nœuds de serveurs dans le pool.  <br/>**Exemple** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Rubriques sur les DNS spécifiques au serveur Edge

 Pour planifier le déploiement de Microsoft Edge Server, reportez-vous à la section [plan pour les déploiements de serveurs de périmètre dans Skype entreprise server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et [planification DNS de Advanced Edge Server pour skype entreprise Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , qui comporte les sections suivantes.

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuration automatique sans DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


