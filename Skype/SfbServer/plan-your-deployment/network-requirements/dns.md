---
title: Conditions préalables des DNS pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé : Passez en revue les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype pour Business Server 2015.'
ms.openlocfilehash: d854c9908211a70b8fe863c9535502ba78c48521
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>Conditions préalables des DNS pour Skype Entreprise Server 2015
 
**Résumé :** Passez en revue les considérations relatives au DNS dans cette rubrique avant d’implémenter Skype pour Business Server 2015.
  
Cet article traite uniquement la planification de DNS pour Skype pour les déploiements Business Server 2015 sur un réseau d’entreprise dans les locaux. Pour Skype pour Business Online consultez « URL d’Office 365 et l’adresse IP plages » à [http://aka.ms/o365ips](http://aka.ms/o365ips). 
  
Un serveur DNS (Domain Name Service) mappe les noms d'hôte (tels que www.contoso.com, vraisemblablement un serveur Web) vers des adresses IP (par ex. : 10.10.10.10). Il permet la communication entre les clients et les serveurs interdépendants sur le réseau. Lorsque vous configurez une implémentation de Skype pour Business Server 2015, vous devez vous assurer que le mappage de nouveaux noms de serveur (généralement qui reflète le rôle qu’ils prendrons sur) établit une correspondance avec les adresses IP à que sont affectées.
  
Alors que cela peut sembler un bit complexe dans un premier temps, l’essentiel pour la planification de ce peut être effectuée à l’aide de la [Skype pour l’outil de planification de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Après avoir répondu aux questions de l'assistant sur les fonctionnalités que vous prévoyez d'utiliser, vous pouvez, pour chaque site défini, afficher le rapport DNS dans le rapport d'administrateur Edge et utiliser les informations qu'il contient pour créer vos enregistrements DNS. Vous pouvez également modifier divers noms et adresses IP. Pour plus d'informations, reportez-vous à la section [Consulter le rapport DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Notez que vous pouvez exporter le rapport d'administrateur Edge vers un tableur Excel ; l'une des feuilles de calcul comprendra le rapport DNS. 
  
Lorsque vous installez une nouvelle implémentation comme décrit dans [créer des enregistrements DNS pour Skype pour Business Server 2015](../../deploy/install/create-dns-records.md) et création de votre topologie pour Skype pour Business Server 2015, nous reconnaissons que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées dans Windows 2016 Server ou un package DNS tiers, afin que nous garder les discussions dans cet article général plutôt que spécifique. Nous détaillons les conditions requises et vous laissons décider de la méthode pour les réunir.
  
Les tableaux suivants sera probablement utile aux expérimentés Skype pour les administrateurs d’entreprise, Lync et Office Communications Suite. Si le tableau s'avère complexe, les sections et articles à venir apporteront des précisions sur les concepts suivants : 
  
- [Tableaux de synthèse](dns.md#BK_Summary)
    
- [Notions de base sur DNS](basics.md)
    
- [Considérations relatives à la hybride](dns.md#BK_Hybrid)
    
- [Fractionnement DNS](dns.md#BK_split)
    
- [URL simples](dns.md#BK_Simple)
    
- [DNS par rôle de serveur](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>Tableaux de synthèse
<a name="BK_Summary"> </a>

Les tableaux suivants indiquent les enregistrements DNS que Skype pour Business Server 2015 utilise pour fournir des services aux utilisateurs. Certains d'entre eux sont facultatifs, car ils permettent uniquement de prendre en charge certaines fonctionnalités ; vous pouvez donc les ignorer si vous ne souhaitez pas utiliser ces fonctionnalités. Les enregistrements DNS requis uniquement pour l'accès interne figurent dans le premier tableau ; un déploiement permettant l'accès interne comme externe requiert les enregistrements des deux tableaux.
  
**Mappages DNS internes**

|**Type d’enregistrement**|**Valeur**|**Est résolu en**|**Objectif**|**Obligatoire**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Nom de domaine complet pool frontal  <br/>  *FE-pool.contoso.com*  <br/> |Adresses IP des serveurs frontaux pool de serveurs frontaux  <br/>  DNS kg à *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Équilibrage de charge DNS des pools frontaux Mappe le nom du pool frontal vers un ensemble d'adresses IP.  <br/> Reportez-vous à la section [Déploiement de l'équilibrage de la charge DNS dans les pools frontaux et les pools directeurs](load-balancing.md#BK_FE_Dir). <br/> |Y  <br/> |
|A/AAAA  <br/> | Nom de domaine complet de chaque serveur frontal ou Standard Edition server dans un pool ou un serveur autonome <br/>  * FE01.contoso.com, FE02.contoso.com, FE03.contoso.com*  <br/> |IP correspondant de chaque serveur  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Mappe le nom du serveur vers son adresse IP.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de remplacement de services Web internes pour pool d'entreprise  <br/>  *Web-int.contoso.com*  <br/> |Adresse IP virtuelle du services Web internes de serveur frontal  <br/>  * 192.168.21.120 *  <br/> |Requis pour permettre le trafic web server, telles que le téléchargement de la Skype pour l’application Web de gestion client. Également requis pour les clients mobiles.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de remplacement de services Web externes pour pool d'entreprise  <br/>  *Web-ext.contoso.com*  <br/> |Adresse IP virtuelle pour les Services Web externes de serveur frontal  <br/>  *68.123.56.90*  <br/> |Requis pour permettre le trafic web server, telles que le téléchargement de la Skype pour l’application Web de gestion client. Requis si les clients mobiles résoudront le DNS en interne. Peut être converti en adresse IP Internet ou adresse IP de proxy inverse DMZ.  <br/> ||
|A/AAAA  <br/> | Sauvegarder le FQDN du serveur SQL Server de fin <br/>  *SQL1.contoso.com*  <br/> |Adresse IP de serveur  <br/>  *192.168.11.90*  <br/> |Mappe le nom du serveur SQL server principal fonctionne avec le pool frontal à son adresse IP  <br/> ||
|A/AAAA  <br/> |Fin serveur miroir SQL serveur nom de domaine complet  <br/>  *SQL2.contoso.com*  <br/> |Adresse IP de serveur  <br/>  *192.168.11.91*  <br/> |Mappe le nom du serveur pour un serveur de mise en miroir SQL principale fonctionne avec le pool frontal à son adresse IP  <br/> ||
|A/AAAA  <br/> |FQDN du pool de directeurs  <br/> **Remarque :** Non applicable lors de l’utilisation d’un serveur de directeur autonome <br/>  *DirPool.contoso.com*  <br/> |Adresses IP de pool directeur  <br/> Livres DNS *192.168.21.132, 192.168.21.133* , 192.168.21.134  <br/> |Équilibrage de la charge DNS de serveurs de pool directeur. Mappages de nom du pool pour le pool directeur à une adresse IP, consultez [Déploiement d’un équilibrage de charge DNS sur les Pools frontaux et directeurs](load-balancing.md#BK_FE_Dir) <br/> Un pool directeur peut authentifier un utilisateur et est facultatif.  <br/> ||
|A/AAAA  <br/> |FQDN du directeur  <br/> |Adresse IP du serveur de chaque serveur directeur  <br/> |Mappages de nom du pool pour le directeur à une adresse IP, consultez [Déploiement d’un équilibrage de charge DNS sur les Pools frontaux et directeurs](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |Pool de serveurs de médiation nom de domaine complet  <br/> |Adresses IP de pools  <br/> |Le rôle du serveur de médiation est facultatif. Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN du serveur de médiation  <br/> |Adresse IP de serveur  <br/> |Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN du serveur de conversation permanente  <br/> |Adresse IP du serveur de conversation permanente  <br/> |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente mais reste facultative.  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |Adresse VIP du serveur frontal ou directeur IP  <br/>  192.168.21.121 <br/> |AutoDiscover Service1 interne, requis pour la prise en charge de la mobilité. Si le serveur DNS interne est utilisé pour résoudre les appareils mobiles, il doit pointer vers l’adresse IP externe, ou DMZ VIP.  <br/> Pour les services Web, nous avons besoin matérielle sur le pool frontal HTTPS ne peut pas exploiter DNS. Pour le pool frontal ou pool directeur que cela doit correspond à une adresse IP virtuelle du, ou une adresse IP standard pour un serveur Standard edition server ou un serveur autonome directeur.  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *Contoso.com*  <br/> |FQDN de pool HLB FE ou FQDN de serveur directeur  <br/> Web-int.contoso.com  <br/> |Service1 de découverte automatique interne <br/> Si vous le souhaitez, vous pouvez l'implémenter comme CNAME (nom canonique) au lieu d'un enregistrement A.  <br/> ||
|A/AAAA  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |Adresses IP de serveur (ou un chaque IP directeur adresse) un pool de serveurs frontaux  <br/>  DNS kg à *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Requis pour la configuration automatique, voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un ou des enregistrements qui pointe vers les serveurs du pool frontal ou directeur serveurs sur le réseau interne, ou le service Edge d’accès lorsque le client est externe  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2. _\<sipdomain\>_ <br/> ucupdates-r2. _Contoso.com_ <br/> |Adresse VIP de pool HLB FE ou VIP HLB de pool de serveurs directeur, ou IP de serveur directeur/SE  <br/>  192.168.21.121 <br/> |Déploiement de cet enregistrement est facultatif 3 <br/> ||
|SRV  <br/> |_sipinternaltls._tcp. _ \<sipdomain\> _ Port 5061 <br/> _sipinternaltls._tcp. Port 5061 _contoso.com_ <br/> |Nom de domaine complet pool frontal  <br/>  _FE-pool.contoso.com_ <br/> |Permet d’interne automatique connexion de l’utilisateur 1 pour le serveur/pool frontal ou le serveur/pool SE qui authentifie et redirige les demandes des clients pour la connexion. <br/> |2 <br/> |
|SRV  <br/> |_sipinternal. _\<sipdomain\>_ <br/> _sipinternal. _Contoso.com_ <br/> |Nom de domaine complet pool frontal  <br/>  _FE-pool.contoso.com_ <br/> |Accès des utilisateurs internes 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp. _\<sipdomain\>_ <br/> _ntp._udp. _Contoso.com_ <br/> |FQDN de serveur de temps  <br/> Nord-america.pool.ntp.org  <br/> |Source NTP nécessaire pour les appareils Lync Phone Edition  <br/> |Cette opération est obligatoire pour prendre en charge des téléphones de bureau.  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> | Nom de domaine complet service Edge d’accès <br/> EdgePool-int. _contoso.com_ <br/> |Créez un enregistrement SRV pour chaque domaine SIP comptant des clients mobiles iOS ou Windows Phone.  <br/> |Prise en charge des clients mobiles  <br/> |
|A/AAAA  <br/> |URL d'administration  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Skype pour Business Server le panneau de configuration, voir les [URL simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL de réunion  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Les réunions en ligne, voir les [URL simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL d'accès à distance  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Conférence rendez-vous, voir les [URL simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |FQDN des services Web internes  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Skype pour le Service Web utilisé par Skype pour l’application Web de gestion d’entreprise  <br/> ||
|A/AAAA  <br/> |FQDN du pool de serveur d’applications Web Office  <br/> OWA.contoso.com  <br/> | Pool de serveur d’applications Web Office adresse IP virtuelle <br/> 192.168.1.5  <br/> |Définit le nom de domaine complet du pool Office Web Apps Server  <br/> ||
|A/AAAA  <br/> | FQDN web interne <br/> Web-int.contoso.com  <br/> | Adresse IP virtuelle pool frontal <br/> 192.168.21.121  <br/> |Définit le FQDN Web interne utilisé par Skype pour Business Web App  <br/> Si vous avez recours à l'équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs Web internes ne peuvent pas avoir le même nom de domaine complet.  <br/> ||
   
 **1** utilisé par un client pour découvrir le pool frontal ou serveur frontal et être authentifié et connecté en tant qu’utilisateur. Plus de détails sur ce est sur la [localisation des services Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).
  
 **2** cette opération est obligatoire uniquement pour prendre en charge des clients hérités avant Lync 2013 et combinés de bureau.
  
 **3** dans le cas où un périphérique de Communications unifiées est activé, mais un utilisateur n’est jamais connecté le périphérique, l’enregistrement A permet de détecter le serveur hébergeant le service Web de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.
  
Le diagramme suivant illustre un exemple incluant des enregistrements DNS à la fois internes et externes, ainsi que de divers enregistrements indiqués dans les tableaux de cet article : 
  
**Organigramme de bord à l’aide d’adresses IPv4 publique**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**Mappages DNS de réseau de périmètre (interfaces internes et externes)**

|**Type d’enregistrement**|**Valeur**|**Est résolu en**|**Objectif**|**Obligatoire**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |CELUI du pool Edge interne  <br/>  _EdgePool-int.contoso.com_ <br/> |Adresses IP de côté interne Edge pool  <br/> 172.25.33.10, 172.25.33.11  <br/> |Adresses IP de l'interface interne du pool Edge consolidé  <br/> |Y  <br/> |
|A/AAAA  <br/> |Nom de domaine complet de serveur Edge  <br/>  _Inconvénients-1.contoso.com_ <br/> |Adresse IP du serveur interne côté pour un serveur du pool Edge  <br/> 172.25.33.10  <br/> |Créer un enregistrement pour chaque serveur du pool avec le nom de domaine complet du serveur en pointant sur son IP du nœud de serveur interne dans le pool, voir [Équilibrage de charge DNS sur Pools de serveurs Edge](load-balancing.md#BK_Edge).  <br/> |Y  <br/> |
|A/AAAA  <br/> |Nom complet du Pool service Edge d’accès  <br/>  _Access1.contoso.com_ <br/> |Access Edge service Pool des adresses IP externes  <br/> 131.107.16.10, 131.107.16.11  <br/> |Le service Edge d’accès fournit un point de connexion unique approuvé, pour le trafic de protocole SIP (Session Initiation) sortant et entrant.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Service du serveur Edge de conférence Web nom complet du Pool  <br/>  _Webcon1.contoso.com_ <br/> |Les adresses IP externes de service Edge de conférence Web  <br/> 131.107.16.90, 131.107.16.91  <br/> |Le service Edge de conférence Web permet aux utilisateurs externes de participer à des réunions qui sont hébergées sur votre Skype pour un environnement Business Server interne.  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<domaines sip\> _ Nom de domaine complet de pool <br/>  _AV1.contoso.com_ <br/> |Adresses IP externes de serveur Edge A/V  <br/> 131.107.16.170, 131.107.16.171  <br/> |A / V Edge service rend audio, vidéo, partage d’application et transfert de fichiers accessibles aux utilisateurs externes.  <br/> |Y  <br/> |
|CNAME  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |FQDN du pool Edge d'accès externe  <br/>  _Access1.contoso.com_ <br/> |Localise le pool de serveurs Edge. Voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls. _\<sipdomain\>_ <br/> _sip._tls. _Contoso.com_ <br/> |Serveur Edge d’accès externe nom de domaine complet  <br/>  _Access1.contoso.com_ <br/> |Utilisé pour l'accès externe des utilisateurs. Voir [services de localisation de Skype de procédure pas à pas pour les clients d’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp. _\<sipdomain\>_ <br/> _sipfederationtls._tcp. _Contoso.com_ <br/> |Serveur Edge d’accès externe nom de domaine complet  <br/>  _Access1.contoso.com_ <br/> |Utilisé pour la fédération et la connectivité PIC  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp. _\<sipdomain\>_ <br/> _xmpp-server._tcp. _Contoso.com_ <br/> |Serveur Edge d’accès externe nom de domaine complet  <br/>  _Access1.contoso.com_ <br/> |Le service Proxy XMPP accepte et envoie XMPP et des messages de protocole (XMPP) de présence avec des partenaires fédérés XMPP configurés.  <br/> |Oui, pour déployer la fédération ; sinon, facultatif  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> |Serveur Edge d’accès externe nom de domaine complet  <br/>  _Access1.contoso.com_ <br/> |Pour prendre en charge le Service de notifications Push et service de notifications Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP. 3 <br/> ||
|A/AAAA  <br/> |Nom de domaine complet des services web du pool frontal externe  <br/>  _Web-ext.contoso.com_ <br/> |Proxys inverses adresse IP publique du proxy, à l’adresse IP virtuelle de Services Web externes pour votre pool frontal 1 <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Front End pool externe interface utilisée par Skype pour Business Web App  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _Contoso.com_ <br/> |Reverse proxy adresse IP publique correspond à l’adresse IP virtuelle de Services Web externes pour votre pool directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur 2 <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> | Enregistrement externe pour le client de découverte automatique, également utilisée par la mobilité, Skype pour Business Web App et Planificateur Web app, résolu par le serveur proxy inverse <br/> Pour prendre en charge le Service de notifications Push et service de notifications Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP dont les clients Microsoft Lync Mobile. 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |meet. _\<sipdomain\>_ <br/> meet. _Contoso.com_ <br/> |Inverser l’adresse IP publique proxy, correspond à l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir les [URL simples](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |rendez-vous _ \<sipdomain\>_ <br/> rendez-vous _contoso.com_ <br/> |Proxys inverses adresse IP publique du proxy, à l’interface Web externe pour le pool frontal  <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir les [URL simples](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN du pool de serveur d’applications Web Office  <br/> OWA.contoso.com  <br/> | Adresse IP publique proxy inverse, proxys pour l’interface Web externe pour le serveur Office Web Apps Server <br/> 131.107.155.1 proxy pour 192.168.1.5  <br/> | Pool de serveur d’applications Web Office adresse IP virtuelle <br/> 192.168.1.5  <br/> |Définit le nom de domaine complet du pool Office Web Apps Server  <br/> |
   
 **1** requis pour déployer la fédération, sinon facultative.
  
 **2** utilisé par un client pour détecter le serveur frontal ou un pool frontal et être authentifié et connecté en tant qu’utilisateur.
  
 **3** cette exigence s’applique uniquement aux clients sur Apple ou Microsoft en fonction des appareils mobiles. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.
  
 Pour plus d’informations sur les serveurs de périphérie et les réseaux de périmètre, consultez le contenu de [planification DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) du serveur Edge.
  
> [!IMPORTANT]
> Skype pour Business Server prend en charge l’utilisation de l’adressage IPv6. Pour plus d’informations, consultez [planification d’IPv6 dans Skype pour les entreprises](ipv6.md) .
  
> [!IMPORTANT]
> Pour plus d’informations sur les noms de domaine complets, voir [Notions de base sur DNS](basics.md). 
  
 **Split brain DNS** 
 <a name="BK_split"> </a>
 
Split brain DNS est une configuration DNS où vous avez deux zones DNS avec le même espace de noms. La première zone DNS traite les demandes internes, tandis que la deuxième zone DNS traite les demandes externes. tel qu'indiqué dans les tableaux. Pour plus d'informations, consultez la section [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS). 
  
## <a name="hybrid-considerations"></a>Remarque sur les environnements hybrides
<a name="BK_Hybrid"> </a>

Si vous prévoyez d'héberger des utilisateurs en ligne et d'autres sur site, reportez-vous à la section [Paramètres DNS](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) hybrides. Vous devez configurer DNS comme d’habitude pour Skype pour Business Server 2015 et ajouter des enregistrements DNS supplémentaires. 
  
Vous devez également vous reporter à « URL d’Office 365 et l’adresse IP plages » au [http://aka.ms/o365ips](http://aka.ms/o365ips) pour vérifier que vos utilisateurs auront accès aux ressources en ligne dont ils auront besoin.
  
## <a name="simple-urls"></a>URL simples 
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource Web qui spécifie son emplacement dans un réseau informatique et un protocole utilisé pour le récupérer. 
  
Skype pour Business Server prend en charge trois URL « simples » pour accéder aux services :
  
- **Meet** est l'URL de réunion de base pour toutes les conférences dans le site. Un exemple d’un simple Meet URL est https://meet.contoso.com. Une URL pour une réunion donnée peut être https://meet.contoso.com/ _nom d’utilisateur_/7322994. 
    
    Avec l'URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre et à communiquer.
    
- **Dial-in** permet d'accéder à la page Web Paramètres de conférence rendez-vous. Cette page indique les numéros d'accès aux conférences et les langues dans lesquels ils sont disponibles. Elle présente également les informations relatives aux conférences affectées aux utilisateurs (c'est-à-dire, pour les réunions qui ne doivent pas être planifiées) et comporte des contrôles DTMF à utiliser en cours de conférence. Enfin, elle permet aux utilisateurs de gérer leur code confidentiel et les informations relatives aux conférences qui leur ont été affectées. L'URL simple de numérotation est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Voici un exemple de l’URL simple Dial-in https://dialin.contoso.com.
    
- **Admin** permet d’accéder rapidement à la Skype pour le panneau de configuration serveur Business. À partir de n’importe quel ordinateur dans le pare-feu de votre organisation, un administrateur peut ouvrir la Skype pour le panneau de configuration serveur Business en tapant l’URL simple d’administration dans un navigateur. L’URL simple Admin est interne à votre organisation. Voici un exemple de l’URL simple Admin https://admin.contoso.com.
    
URL simples sont abordés plus en détail à la [configuration DNS requise pour les URL simples dans Skype pour Business Server 2015](simple-urls.md).
  
## <a name="dns-by-server-role"></a>DNS par rôle de serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme bon vous semble, faciles à mémoriser et reflétant leur fonction dans le système.
  
### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools spécifiques

Ces exigences enregistrement générique s’appliquent à un rôle de serveur utilisé par Skype pour les entreprises. Un pool est un ensemble de serveurs exécutant les mêmes services qui fonctionnent ensemble pour traiter les demandes client qu'ils reçoivent via un équilibreur de charge. Voir [Configuration requise pour Skype pour les entreprises l’équilibrage de charge](load-balancing.md) pour plus d’informations
  
**Exigences d’enregistrement DNS pour les rôles de serveur/pool (suppose que l’équilibrage de charge DNS)**

|**Scénario de déploiement**|**Enregistrement DNS requis**|
|:-----|:-----|
|Un serveur :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal  <br/> |Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|Pool :  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal  <br/> |Un enregistrement interne A qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur dans le pool sur son adresse IP.  <br/> **Exemple** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> Plusieurs enregistrements internes A qui résolvent le nom de domaine complet (FQDN) du pool sur les adresses IP des nœuds de serveurs dans le pool.  <br/> **Exemple** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>Rubriques sur les DNS spécifiques au serveur Edge

 Pour planifier un déploiement de serveur edge, consultez [Plan pour les déploiements de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et [avancée Edge Server DNS planification de Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) qui comprend les sections suivantes
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Configuration automatique sans DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

