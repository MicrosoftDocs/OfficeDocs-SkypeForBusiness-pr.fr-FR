---
title: Enregistrements DNS requis pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé : Passez en revue les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: 8bcc8cf016b0a1774b5c7868807c946b1dbe9311
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925347"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Enregistrements DNS requis pour Skype pour Business Server

**Résumé :** Passez en revue les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype pour Business Server.

Cet article traite uniquement la planification de DNS pour Skype pour les déploiements Business Server sur un réseau d’entreprise dans les locaux. Pour Skype pour Business Online consultez « URL d’Office 365 et l’adresse IP plages » à [https://aka.ms/o365ips](https://aka.ms/o365ips).

Serveur DNS service (DNS) mappe les noms d’hôtes (tels que www.<span> </span> Contoso<span></span>.com, vraisemblablement sur un serveur web) sur des adresses IP (par exemple, 10.10.10.10). Il permet aux clients et serveurs interdépendants communiquent entre eux sur le réseau. Lorsque vous configurez une implémentation de Skype pour Business Server 2015, vous devez vous assurer que le mappage de nouveaux noms de serveur (généralement qui reflète le rôle qu’ils prendrons sur) établit une correspondance avec les adresses IP à que sont affectées.

Alors que cela peut sembler un bit complexe dans un premier temps, l’essentiel pour la planification de ce peut être effectuée à l’aide de la [Skype pour l’outil de planification de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Une fois que vous avez vérifié les questions de l’Assistant sur les fonctionnalités que vous prévoyez d’utiliser, pour chaque site que vous définissez vous pouvez afficher le rapport DNS dans le rapport et utiliser les informations répertoriées pour créer vos enregistrements DNS. Vous pouvez également ajuster à la plupart des noms et des adresses IP utilisées, pour plus d’informations consultez [examen du rapport DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Gardez en vous pouvez exporter le rapport vers une feuille de calcul Excel, et le rapport DNS sera une des feuilles de calcul dans le fichier. Cet outil inclut les fonctionnalités [déconseillées de Skype pour Business Server 2019](../../../SfBServer2019/deprecated.md), il peut toujours être utilisé pour créer un plan initial si ces fonctionnalités ne sont pas activées.

Lorsque vous installez une nouvelle implémentation comme décrit dans [créer des enregistrements DNS pour Skype pour Business Server](../../deploy/install/create-dns-records.md) et de création de votre topologie pour Skype pour Business Server, nous reconnaissons que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées à Windows Server 2016 ou un package DNS tiers, afin que nous garder les discussions dans cet article général plutôt que spécifique. Nous détaillons les conditions requises et vous laissons décider de la méthode pour les réunir.

Les tableaux suivants sera probablement utile aux expérimentés Skype pour les administrateurs d’entreprise, Lync et Office Communications Suite. Si le tableau s'avère complexe, les sections et articles à venir apporteront des précisions sur les concepts suivants :

## <a name="summary-tables"></a>Tableaux de synthèse
<a name="BK_Summary"> </a>

Les tableaux suivants indiquent les enregistrements DNS que Skype pour Business Server utilise pour fournir des services aux utilisateurs. Certains d'entre eux sont facultatifs, car ils permettent uniquement de prendre en charge certaines fonctionnalités ; vous pouvez donc les ignorer si vous ne souhaitez pas utiliser ces fonctionnalités. Les enregistrements DNS requis uniquement pour l'accès interne figurent dans le premier tableau ; un déploiement permettant l'accès interne comme externe requiert les enregistrements des deux tableaux.

**Mappages DNS internes**

|Type d'enregistrement|Valeur|Résolu en|Objectif|Obligatoire|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Nom de domaine complet pool frontal  <br/> *FE-pool. <span> </span>contoso<span></span>.com*   |Adresses IP des serveurs frontaux pool de serveurs frontaux  <br/>  DNS kg à *192.168.21.122 192.168.21.123 192.168.21.124*   |Équilibrage de charge DNS des pools frontaux Mappe le nom du pool frontal vers un ensemble d'adresses IP. <br/> Reportez-vous à la section [Déploiement de l'équilibrage de la charge DNS dans les pools frontaux et les pools directeurs](load-balancing.md#BK_FE_Dir).  |Y   |
|A/AAAA   | Nom de domaine complet de chaque serveur frontal ou Standard Edition server dans un pool ou un serveur autonome <br/>  *FE01. <span> </span>contoso. <span> </span>FE02 com. <span> </span>contoso<span></span>.com FE03. <span> </span>contoso<span></span>.com*   |IP correspondant de chaque serveur  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mappe le nom du serveur vers son adresse IP.   |Y   |
|A/AAAA   |FQDN de remplacement de services Web internes pour pool d'entreprise  <br/> *Web-int<span></span>contoso<span></span>.com*   |Adresse IP virtuelle du services Web internes de serveur frontal  <br/> *192.168.21.120*   |Requis pour permettre le trafic web server, telles que le téléchargement de la Skype pour l’application Web de gestion client. Également requis pour les clients mobiles.   |Y   |
|A/AAAA   |FQDN de remplacement de services Web externes pour pool d'entreprise  <br/> *Web-ext<span></span>contoso<span></span>.com*   |Adresse IP virtuelle pour les Services Web externes de serveur frontal  <br/>*68.123.56.90*   |Requis pour permettre le trafic web server, telles que le téléchargement de la Skype pour l’application Web de gestion client. Requis si les clients mobiles résoudront le DNS en interne. Peut être converti en adresse IP Internet ou adresse IP de proxy inverse DMZ.   ||
|A/AAAA   | Sauvegarder le FQDN du serveur SQL Server de fin <br/> *SQL1. <span> </span>contoso<span></span>.com*   |Adresse IP de serveur  <br/> *192.168.11.90*   |Mappe le nom du serveur SQL server principal fonctionne avec le pool frontal à son adresse IP   ||
|A/AAAA   |Fin serveur miroir SQL serveur nom de domaine complet  <br/> *SQL2. <span> </span>contoso<span></span>.com*   |Adresse IP de serveur  <br/> *192.168.11.91*   |Mappe le nom du serveur pour un serveur de mise en miroir SQL principale fonctionne avec le pool frontal à son adresse IP   ||
|A/AAAA   |FQDN du pool de directeurs  <br/>**Remarque :** Non applicable lors de l’utilisation d’un serveur de directeur autonome <br/> *DirPool. <span> </span>contoso<span></span>.com*   |Adresses IP de pool directeur  <br/> Livres DNS *192.168.21.132, 192.168.21.133* , 192.168.21.134   |Équilibrage des serveurs du Pool directeur de charge DNS. Mappages de nom du pool pour le pool directeur à une adresse IP, consultez [Déploiement d’un équilibrage de charge DNS sur les Pools frontaux et directeurs](load-balancing.md#BK_FE_Dir) <br/> Un pool directeur peut authentifier un utilisateur et est facultatif.   ||
|A/AAAA   |FQDN du directeur   |Adresse IP du serveur de chaque serveur directeur   |Mappages de nom du pool pour le directeur à une adresse IP, consultez [Déploiement d’un équilibrage de charge DNS sur les Pools frontaux et directeurs](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |Pool de serveurs de médiation nom de domaine complet   |Adresses IP de pools   |Le rôle du serveur de médiation est facultatif. Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN du serveur de médiation   |Adresse IP de serveur   |Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN du serveur de conversation permanente   |Adresse IP du serveur de conversation permanente   |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente mais reste facultative.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>contoso<span></span>.com*   |Adresse VIP du serveur frontal ou directeur IP  <br/>  192.168.21.121  |AutoDiscover Service1 interne, requis pour la prise en charge de la mobilité. Si le serveur DNS interne est utilisé pour résoudre les appareils mobiles, il doit pointer vers l’adresse IP externe, ou DMZ VIP.  <br/> Pour les services Web, nous avons besoin matérielle sur le pool frontal HTTPS ne peut pas exploiter DNS. Pour le pool frontal ou pool directeur que cela doit correspond à une adresse IP virtuelle du, ou une adresse IP standard pour un serveur Standard edition server ou un serveur autonome directeur.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>.com*   |FQDN de pool HLB FE ou FQDN de serveur directeur  <br/> Web-int<span></span>contoso<span></span>.com   |Service1 de découverte automatique interne <br/> Si vous le souhaitez, vous pouvez l'implémenter comme CNAME (nom canonique) au lieu d'un enregistrement A.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |Adresses IP de serveur (ou un chaque IP directeur adresse) un pool de serveurs frontaux  <br/>  DNS kg à *192.168.21.122 192.168.21.123 192.168.21.124*   |Requis pour la configuration automatique, voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un ou des enregistrements qui pointe vers les serveurs du pool frontal ou directeur serveurs sur le réseau interne, ou le service Edge d’accès lorsque le client est externe   |& #x 2777 ;  |
|A/AAAA   |UCUpdates-r2. * \<sipdomain\>* <br/> UCUpdates-r2. * <span> </span>contoso<span></span>.com*  |Adresse VIP de pool HLB FE ou VIP HLB de pool de serveurs directeur, ou IP de serveur directeur/SE  <br/>  192.168.21.121  |Déploiement de cet enregistrement est facultatif & #x 2778 ;  ||
|SRV   |\_sipinternaltls. \_tcp. * \<sipdomain\> * <br/>Port 5061 <br/>\_sipinternaltls. \_tcp. * <span> </span>contoso<span></span>.com* <br/>Port 5061  |Nom de domaine complet pool frontal  <br/>*FE-Pool. <span> </span>contoso<span></span>.com*  |Permet la connexion automatique interne des utilisateurs 1 au serveur/pool frontal ou au serveur/pool SE, qui authentifie et redirige les demandes client de connexion.    |& #x 2777 ; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>.com*  |Nom de domaine complet pool frontal  <br/>_FE-Pool. <span> </span>contoso<span></span>.com_  |Utilisateur interne access & #x 2776 ;  |& #x 2777 ;  |
|SRV   | \_NTP. \_udp. * \<sipdomain\> * <br/> \_NTP. \_udp. <span> </span> *contoso<span></span>.com*  |FQDN de serveur de temps  <br/> north-america.pool.ntp.org   |Source NTP nécessaire pour les appareils Lync Phone Edition   |Cette opération est obligatoire pour prendre en charge des téléphones de bureau.   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  | Nom de domaine complet service Edge d’accès <br/> Int-EdgePool<span></span>*contoso<span></span>.com*  |Créez un enregistrement SRV pour chaque domaine SIP comptant des clients mobiles iOS ou Windows Phone.   |Prise en charge des clients mobiles   |
|A/AAAA   |URL d'administration  <br/>*Web-int<span></span>contoso<span></span>.com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Skype pour Business Server le panneau de configuration, voir les [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de réunion  <br/>*Web-int<span></span>contoso<span></span>.com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Les réunions en ligne, voir les [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL d'accès à distance  <br/>*Web-int<span></span>contoso<span></span>.com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Conférence rendez-vous, voir les [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN des services Web internes  <br/>*Web-int<span></span>contoso<span></span>.com*  |Adresse VIP de pool HLB FE  <br/> 192.168.21.121   |Skype pour le Service Web utilisé par Skype pour l’application Web de gestion d’entreprise   ||
|A/AAAA   |FQDN du pool de serveur d’applications Web Office  <br/> OWA. <span> </span>contoso<span></span>.com   | Pool de serveur d’applications Web Office adresse IP virtuelle <br/> 192.168.1.5   |Définit le nom de domaine complet du pool Office Web Apps Server   ||
|A/AAAA   |  FQDN web interne <br/> Web-int<span></span>contoso<span></span>.com   | Adresse IP virtuelle pool frontal <br/> 192.168.21.121   |Définit le FQDN Web interne utilisé par Skype pour Business Web App  <br/> Si vous avez recours à l'équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs Web internes ne peuvent pas avoir le même nom de domaine complet.   ||

& #x 2776 ; Utilisé par un client pour découvrir le pool frontal ou serveur frontal et être authentifié et connecté en tant qu’utilisateur. Plus de détails sur ce est sur la [localisation des services Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

& #x 2777 ; Cette opération est obligatoire uniquement pour prendre en charge des clients hérités avant Lync 2013 et combinés de bureau.

& #x 2778 ; Dans le cas où un périphérique de Communications unifiées est activé, mais un utilisateur n’est jamais connecté le périphérique, l’enregistrement A permet de détecter le serveur hébergeant le service Web de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.

Le diagramme suivant illustre un exemple incluant des enregistrements DNS à la fois internes et externes, ainsi que de divers enregistrements indiqués dans les tableaux de cet article : 

**Diagramme réseau Edge utilisant des adresses IPv4 publiques**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mappages DNS du réseau de périmètre (interfaces internes et externes)**

|Type d'enregistrement|Valeur|Résolu en|Objectif|Obligatoire|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |CELUI du pool Edge interne  <br/>*EdgePool-int<span></span>contoso<span></span>.com*  |Adresses IP de côté interne Edge pool  <br/> 172.25.33.10, 172.25.33.11   |Adresses IP de l'interface interne du pool Edge consolidé   |Y   |
|A/AAAA   |Nom de domaine complet de serveur Edge  <br/>*Inconvénients-1. <span> </span>contoso<span></span>.com*  |Adresse IP du serveur interne côté pour un serveur du pool Edge  <br/> 172.25.33.10   |Créer un enregistrement pour chaque serveur du pool avec le nom de domaine complet du serveur en pointant sur son IP du nœud de serveur interne dans le pool, voir [Équilibrage de charge DNS sur Pools de serveurs Edge](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |Nom complet du Pool service Edge d’accès  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Access Edge service Pool des adresses IP externes  <br/> 131.107.16.10, 131.107.16.11   |Le service Edge d’accès fournit un point de connexion unique approuvé, pour le trafic de protocole SIP (Session Initiation) sortant et entrant.   |Y   |
|A/AAAA   |Service du serveur Edge de conférence Web nom complet du Pool  <br/>*Webcon1. <span> </span>contoso<span></span>.com*  |Les adresses IP externes de service Edge de conférence Web  <br/> 131.107.16.90, 131.107.16.91   |Le service Edge de conférence Web permet aux utilisateurs externes de participer à des réunions qui sont hébergées sur votre Skype pour un environnement Business Server interne.   |Y   |
|A/AAAA   |*av.\<domaines sip\> * Nom de domaine complet de pool <br/>*AV1. <span> </span>contoso<span></span>.com*  |Adresses IP externes de serveur Edge A/V  <br/> 131.107.16.170, 131.107.16.171   |A / V Edge service rend audio, vidéo, partage d’application et transfert de fichiers accessibles aux utilisateurs externes.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |FQDN du pool Edge d'accès externe  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Localise le pool de serveurs Edge. Voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_tls. * \<sipdomain\> * <br/>\_SIP. \_tls. <span> </span> *contoso<span></span>.com*  |Serveur Edge d’accès externe nom de domaine complet  <br/>_Access1. <span> </span>contoso<span></span>.com_  |Utilisé pour l'accès externe des utilisateurs. Voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  |Serveur Edge d’accès externe nom de domaine complet  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Utilisé pour la fédération et la connectivité PIC   |& #x 2776 ;  |
|SRV   |\_serveur-XMPP. \_tcp. *<sipdomain\> * <br/>\_serveur-XMPP. \_tcp. * <span> </span>contoso<span></span>.com*  |Serveur Edge d’accès externe nom de domaine complet  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Le service Proxy XMPP accepte et envoie XMPP et des messages de protocole (XMPP) de présence avec des partenaires fédérés XMPP configurés.   |Oui, pour déployer la fédération ; sinon, facultatif  <br/> Non disponible dans Skype pour Business Server 2019.|
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. * <span> </span>contoso<span></span>.com*  |Serveur Edge d’accès externe nom de domaine complet  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Pour prendre en charge le Service de notifications Push et service de notifications Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP. & #x 2778 ;  ||
|A/AAAA   |Nom de domaine complet des services web du pool frontal externe  <br/>*Web-ext<span></span>contoso<span></span>.com*  |Proxys inverses adresse IP publique du proxy, à l’adresse IP virtuelle de Services Web externes pour votre & de pool frontal #x 2776 ; <br/> 131.107.155.1 proxy d’à 192.168.21.120   |Front End pool externe interface utilisée par Skype pour Business Web App   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>contoso<span></span>.com*  |Reverse proxy adresse IP publique correspond à l’adresse IP virtuelle de Services Web externes pour votre pool directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas une & directeur #x 2777 ; <br/> 131.107.155.1 proxy d’à 192.168.21.120   | Enregistrement externe pour le client de découverte automatique, également utilisée par la mobilité, Skype pour Business Web App et Planificateur Web app, résolu par le serveur proxy inverse <br/> Pour prendre en charge le Service de notifications Push et service de notifications Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP dont les clients Microsoft Lync Mobile. 3  |Y   |
|A/AAAA   |respecter. * \<sipdomain\>* <br/> respecter. * <span> </span>contoso<span></span>.com*  |Inverser l’adresse IP publique proxy, correspond à l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy d’à 192.168.21.120   |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir les [URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |numérotation pouces*\<sipdomain\>* <br/> numérotation pouces*<span></span>contoso<span></span>.com*  |Proxys inverses adresse IP publique du proxy, à l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy d’à 192.168.21.120   |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir les [URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN du pool de serveur d’applications Web Office  <br/> OWA. <span> </span>contoso<span></span>.com   | Adresse IP publique proxy inverse, proxys pour l’interface Web externe pour le serveur Office Web Apps Server <br/> 131.107.155.1 proxy pour 192.168.1.5   | Pool de serveur d’applications Web Office adresse IP virtuelle <br/> 192.168.1.5   |Définit le nom de domaine complet du pool Office Web Apps Server   |

& #x 2776 ; Requis pour déployer la fédération, sinon facultative.

& #x 2777 ; Utilisé par un client pour détecter le serveur frontal ou un pool frontal et être authentifié et connecté en tant qu’utilisateur.

& #x 2778 ; Cette exigence s’applique uniquement aux clients sur Apple ou Microsoft en fonction des appareils mobiles. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.

 Pour plus d’informations sur les serveurs de périphérie et les réseaux de périmètre, consultez le contenu de [planification DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) du serveur Edge.

> [!IMPORTANT]
> Skype pour Business Server prend en charge l’utilisation de l’adressage IPv6. Pour plus d'informations, consultez l'article [Plan for IPv6 in Skype for Business](ipv6.md).

> [!IMPORTANT]
> Pour plus d'informations sur les FQDN, consultez l'article [DNS basics](basics.md). 

**Split brain DNS** 
 <a name="BK_split"> </a>

Split brain DNS est une configuration DNS où vous avez deux zones DNS avec le même espace de noms. La première zone DNS gère les demandes internes, tandis que la deuxième zone DNS gère les demandes externes, comme indiqué dans les tableaux. Pour plus d’informations, voir [DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Remarque sur les environnements hybrides
<a name="BK_Hybrid"> </a>

Si vous voulez que certains utilisateurs hébergement en ligne et certains hébergés sur site, reportez-vous à la connectivité hybride planification article [Skype pour Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Vous devez configurer DNS comme d’habitude pour Skype pour Business Server 2015 et ajouter des enregistrements DNS supplémentaires.

Vous devez également vous reporter à « URL d’Office 365 et l’adresse IP plages » au [https://aka.ms/o365ips](https://aka.ms/o365ips) pour vérifier que vos utilisateurs auront accès aux ressources en ligne dont ils auront besoin.

## <a name="simple-urls"></a>URL simples 
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource Web qui spécifie son emplacement dans un réseau informatique et un protocole utilisé pour le récupérer. 

Skype pour Business Server prend en charge trois URL « simples » pour accéder aux services :

- **Meet** est l'URL de réunion de base pour toutes les conférences dans le site. Un exemple d’une URL simple Meet est https :<span></span>//<span></span>satisfaire. <span> </span>contoso<span></span>. com. Une URL pour une réunion donnée peut être https :<span></span>//<span></span>satisfaire. <span> </span>contoso<span></span>.com /_nom d’utilisateur_/7322994.

    Avec l'URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre et à communiquer.

- **Rendez-vous** permettant d’accéder à la page web paramètres de conférence rendez-vous. Cette page affiche les numéros rendez-vous conférence avec les langues disponibles, affectées des informations sur la conférence (c'est-à-dire, pour les réunions qui ne doivent pas être planifiées) et les contrôles DTMF pendant les conférences et prend en charge la gestion de (numéro d’identification personnelle Code confidentiel) et affecté les informations de conférence. L’URL simple Dial-in est inclus dans toutes les invitations aux réunions afin que les utilisateurs qui souhaitent se connecter à la réunion peuvent accéder au numéro de téléphone nécessaire et les informations de code confidentiel. Un exemple de l’URL simple Dial-in est https://<span></span>dialin. <span> </span>contoso<span></span>. com.

- **Admin** permet d’accéder rapidement à la Skype pour le panneau de configuration serveur Business. À partir de n’importe quel ordinateur dans le pare-feu de votre organisation, un administrateur peut ouvrir la Skype pour le panneau de configuration serveur Business en tapant l’URL simple d’administration dans un navigateur. L’URL simple Admin est interne à votre organisation. Un exemple de l’URL simple Admin est https://<span></span>Admin. <span> </span>contoso<span></span>. com.

URL simples sont abordés plus en détail à la [configuration DNS requise pour les URL simples dans Skype pour Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS par rôle de serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme bon vous semble, faciles à mémoriser et reflétant leur fonction dans le système.

### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools spécifiques

Ces exigences enregistrement générique s’appliquent à un rôle de serveur utilisé par Skype pour les entreprises. Un pool est un ensemble de serveurs exécutant les mêmes services qui fonctionnent ensemble pour traiter les demandes client qu'ils reçoivent via un équilibreur de charge. Pour plus d'informations, consultez la rubrique [Load balancing requirements for Skype for Business](load-balancing.md).

**Conditions requises relatives aux enregistrements DNS pour les rôles de serveur/pool (avec équilibrage de charge DNS)**

|Scénario de déploiement|Enregistrement DNS requis|
|:-----|:-----|
|Un serveur :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal   |Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole. <span> </span>contoso<span></span>.com 10.10.10.0   |
|Pool :  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal    |Un enregistrement interne A qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur dans le pool sur son adresse IP.  <br/>**Exemple** <br/> ServerRole01. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02. <span> </span>contoso<span></span>.com 10.10.10.2  <br/> Plusieurs enregistrements internes A qui résolvent le nom de domaine complet (FQDN) du pool sur les adresses IP des nœuds de serveurs dans le pool.  <br/>**Exemple** <br/> ServerPool. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerPool. <span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Rubriques sur les DNS spécifiques au serveur Edge

 Pour planifier un déploiement de serveur edge, consultez [Plan pour les déploiements de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et [avancée Edge Server DNS planification de Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) qui comprend les sections suivantes

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuration automatique sans DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


