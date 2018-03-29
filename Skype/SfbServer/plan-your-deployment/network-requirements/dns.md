---
title: Conditions préalables des DNS pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Résumé : Passez en revue les considérations relatives à DNS dans cette rubrique avant d’implémenter Skype pour Business Server 2015.'
ms.openlocfilehash: 2f19e6dbd040a7f553331b6bcb0d7074a30fd0ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>Conditions préalables des DNS pour Skype Entreprise Server 2015
 
**Résumé :** Passez en revue les considérations relatives à DNS dans cette rubrique avant d’implémenter Skype pour Business Server 2015.
  
Cet article traite uniquement la planification de DNS pour Skype pour les déploiements d’entreprise serveur 2015 sur un réseau d’entreprise sur site. Pour Skype pour Business Online consultez « URL d’Office 365 et l’adresse IP des plages » à [http://aka.ms/o365ips](http://aka.ms/o365ips). 
  
Un serveur DNS (Domain Name Service) mappe les noms d'hôte (tels que www.contoso.com, vraisemblablement un serveur Web) vers des adresses IP (par ex. : 10.10.10.10). Il permet la communication entre les clients et les serveurs interdépendants sur le réseau. Lorsque vous définissez une mise en œuvre de Skype pour Business Server 2015, vous devez le mappage de nouveaux noms de serveur (généralement qui reflète le rôle qu’ils prendrons sur) correspond à l’adresses IP à que sont affectées.
  
Alors que cela peut sembler un complexe de bit dans un premier temps, l’essentiel de cette planification peut être effectuée à l’aide de la [Skype pour outil de planification Microsoft Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Après avoir répondu aux questions de l'assistant sur les fonctionnalités que vous prévoyez d'utiliser, vous pouvez, pour chaque site défini, afficher le rapport DNS dans le rapport d'administrateur Edge et utiliser les informations qu'il contient pour créer vos enregistrements DNS. Vous pouvez également modifier divers noms et adresses IP. Pour plus d'informations, reportez-vous à la section [Consulter le rapport DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Notez que vous pouvez exporter le rapport d'administrateur Edge vers un tableur Excel ; l'une des feuilles de calcul comprendra le rapport DNS. 
  
Lorsque vous installez une nouvelle implémentation comme décrit dans les [enregistrements DNS de créer pour Skype pour Business Server 2015](../../deploy/install/create-dns-records.md) et la création de votre topologie pour Skype pour Business Server 2015, nous reconnaissons que vous pouvez choisir d’utiliser les fonctionnalités DNS intégrées à Windows Serveur 2016 ou un package DNS tiers, afin de nous garder les discussions dans cet article général plutôt que spécifique. Nous détaillons les conditions requises et vous laissons décider de la méthode pour les réunir.
  
Les tableaux suivants sera probablement utile aux expérimentés Skype pour les administrateurs d’entreprise, Lync et Office Communications Suite. Si le tableau s'avère complexe, les sections et articles à venir apporteront des précisions sur les concepts suivants : 
  
- [Tableaux de synthèse](dns.md#BK_Summary)
    
- [Notions de base sur DNS](basics.md)
    
- [Considérations de hybride](dns.md#BK_Hybrid)
    
- [Fractionnement DNS](dns.md#BK_split)
    
- [URL simples](dns.md#BK_Simple)
    
- [DNS par rôle de serveur](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>Tableaux de synthèse
<a name="BK_Summary"> </a>

Les tableaux suivants présentent les enregistrements DNS que Skype pour Business Server 2015 utilise pour fournir des services aux utilisateurs. Certains d'entre eux sont facultatifs, car ils permettent uniquement de prendre en charge certaines fonctionnalités ; vous pouvez donc les ignorer si vous ne souhaitez pas utiliser ces fonctionnalités. Les enregistrements DNS requis uniquement pour l'accès interne figurent dans le premier tableau ; un déploiement permettant l'accès interne comme externe requiert les enregistrements des deux tableaux.
  
**Mappages DNS internes**

|**Type d’enregistrement**|**Valeur**|**Correspond à**|**Objectif**|**Obligatoire**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Pool de fin avant nom de domaine complet  <br/>  *FE-pool.contoso.com*  <br/> |Adresses IP de serveurs de pool avant fin  <br/>  Livres de DNS à *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Équilibrage de charge DNS des pools frontaux Mappe le nom du pool frontal vers un ensemble d'adresses IP.  <br/> Reportez-vous à la section [Déploiement de l'équilibrage de la charge DNS dans les pools frontaux et les pools directeurs](load-balancing.md#BK_FE_Dir). <br/> |Y  <br/> |
|A/AAAA  <br/> | Nom de domaine complet de chaque serveur Standard Edition ou de serveur frontal dans un pool ou un serveur autonome <br/>  * FE01.contoso.com, FE02.contoso.com, FE03.contoso.com*  <br/> |IP correspondant de chaque serveur  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Mappe le nom du serveur vers son adresse IP.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de remplacement de services Web internes pour pool d'entreprise  <br/>  *Web-int.contoso.com*  <br/> |VIP d’humidification à HLB pour les Services de Front-End Server Web interne  <br/>  * 192.168.21.120 *  <br/> |Requis pour autoriser le client au trafic web server, telles que le téléchargement du Skype pour Business Web App. Également requis pour les clients mobiles.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de remplacement de services Web externes pour pool d'entreprise  <br/>  *Web-ext.contoso.com*  <br/> |VIP d’humidification à HLB pour les Services Web externes de serveur frontal  <br/>  *68.123.56.90*  <br/> |Requis pour autoriser le client au trafic web server, telles que le téléchargement du Skype pour Business Web App. Requis si les clients mobiles résoudront le DNS en interne. Peut être converti en adresse IP Internet ou adresse IP de proxy inverse DMZ.  <br/> ||
|A/AAAA  <br/> | Sauvegarder le FQDN du serveur SQL Server de fin <br/>  *SQL1.contoso.com*  <br/> |Adresse IP de serveur  <br/>  *192.168.11.90*  <br/> |Mappe le nom de serveur pour un serveur SQL de back-end fonctionne avec le pool frontal pour son adresse IP  <br/> ||
|A/AAAA  <br/> |Sauvegarder le FQDN du serveur SQL de mise en miroir de serveur fin  <br/>  *SQL2.contoso.com*  <br/> |Adresse IP de serveur  <br/>  *192.168.11.91*  <br/> |Mappe le nom de serveur pour un serveur de mise en miroir SQL dorsaux fonctionne avec le pool frontal pour son adresse IP  <br/> ||
|A/AAAA  <br/> |Pool de directeur nom de domaine complet  <br/> **Remarque :** Ne s’applique pas lors de l’utilisation d’un serveur de directeur autonome <br/>  *DirPool.contoso.com*  <br/> |Adresses IP de pool directeur  <br/> Livres de DNS *192.168.21.132, 192.168.21.133* , 192.168.21.134  <br/> |Équilibrage de la charge DNS de serveurs de pool directeur. Mappages de nom de pool pour le pool de directeur en adresse IP, reportez-vous à la section [Déploiement DNS équilibrage de la charge sur le Front End Pools et les Pools de directeur](load-balancing.md#BK_FE_Dir) <br/> Un pool directeur peut authentifier un utilisateur et est facultatif.  <br/> ||
|A/AAAA  <br/> |FQDN du directeur  <br/> |Adresse IP du serveur de chaque serveur du directeur  <br/> |Mappe le nom du pool pour le directeur en adresse IP, reportez-vous à la section [Déploiement de l’équilibrage de charge DNS sur le Front End Pools et les Pools de directeur](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |Pool nom de domaine complet du serveur de médiation  <br/> |Adresses IP de pools  <br/> |Le rôle du serveur de médiation est facultatif. Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN du serveur de médiation  <br/> |Adresse IP de serveur  <br/> |Vous pouvez colocaliser les services fournis pas un serveur de médiation vers un serveur ou pool frontal. Consultez [l’aide de DNS équilibrage de charge sur les Pools de serveurs de médiation](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN du serveur de conversation permanent  <br/> |Adresse IP de serveur Chat permanente  <br/> |Un serveur de conversation permanente est requis pour la fonctionnalité de conversation permanente mais reste facultative.  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |Pool d’humidification à HLB Front-End VIP ou directeur IP  <br/>  192.168.21.121 <br/> |Interne AutoDiscover Service1, requis pour la prise en charge de la mobilité. Si le DNS interne est utilisé pour résoudre des périphériques mobiles, il doit pointer vers l’adresse IP externe, ou DMZ VIP.  <br/> Pour les services Web, nous avons besoin HUMIDIFICATION à HLB sur le pool frontal HTTPS ne peut pas exploiter le DNS. Pour le pool de Front-End ou directeur que cela doit résout un VIP d’humidification à HLB ou un IP standard pour un serveur Standard edition server ou un serveur autonome directeur.  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *Contoso.com*  <br/> |FQDN de pool HLB FE ou FQDN de serveur directeur  <br/> Web-int.contoso.com  <br/> |Service1 de découverte automatique interne <br/> Si vous le souhaitez, vous pouvez l'implémenter comme CNAME (nom canonique) au lieu d'un enregistrement A.  <br/> ||
|A/AAAA  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |Avant le pool fin adresse IP du serveur les adresses (ou à une chaque IP directeur adresse)  <br/>  Livres de DNS à *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Requis pour la configuration automatique, consultez [procédure pas à pas de Skype pour les clients de l’entreprise recherche de services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Enregistrements pointant vers les serveurs du pool frontal ou directeur des serveurs sur le réseau interne, ou le service Edge d’accès lorsque le client est externe ou un enregistrement  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2. _\<sipdomain\>_ <br/> ucupdates-r2. _Contoso.com_ <br/> |Adresse VIP de pool HLB FE ou VIP HLB de pool de serveurs directeur, ou IP de serveur directeur/SE  <br/>  192.168.21.121 <br/> |Le déploiement de cet enregistrement est facultatif 3 <br/> ||
|SRV  <br/> |_sipinternaltls._tcp. _ \<sipdomain\> _ Port 5061 <br/> _sipinternaltls._tcp. Port 5061 _contoso.com_ <br/> |Pool de fin avant nom de domaine complet  <br/>  _FE-Pool.contoso.com_ <br/> |Permet à utilisateur interne automatique connexion à 1 pour le serveur/pool frontal ou le serveur/pool SE qui authentifie et redirige les demandes des clients pour la connexion. <br/> |2 <br/> |
|SRV  <br/> |_sipinternal. _\<sipdomain\>_ <br/> _sipinternal. _Contoso.com_ <br/> |Pool de fin avant nom de domaine complet  <br/>  _FE-Pool.contoso.com_ <br/> |Accès des utilisateurs internes 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp. _\<sipdomain\>_ <br/> _ntp._udp. _Contoso.com_ <br/> |FQDN de serveur de temps  <br/> Nord-america.pool.ntp.org  <br/> |Source NTP requis pour les périphériques Microsoft Lync Phone Edition  <br/> |Ceci est nécessaire pour prendre en charge les combinés de bureau.  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> | Nom de domaine complet le service Edge d’accès <br/> EdgePool-int. _contoso.com_ <br/> |Créez un enregistrement SRV pour chaque domaine SIP comptant des clients mobiles iOS ou Windows Phone.  <br/> |Prise en charge des clients mobiles  <br/> |
|A/AAAA  <br/> |URL d'administration  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Skype pour le panneau de configuration de Business Server, consultez [URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL de réunion  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Les réunions en ligne, consultez [URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL d'accès à distance  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Conférences à distance, consultez [URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |FQDN des services Web internes  <br/>  _Web-int.contoso.com_ <br/> |Adresse VIP de pool HLB FE  <br/> 192.168.21.121  <br/> |Skype pour le Service Web d’entreprise utilisées par Skype pour Business Web App  <br/> ||
|A/AAAA  <br/> |Pool de serveur d’applications Web Office nom de domaine complet  <br/> OWA.contoso.com  <br/> | Pool de serveur d’applications Web Office adresse VIP <br/> 192.168.1.5  <br/> |Définit le nom de domaine complet du pool Office Web Apps Server  <br/> ||
|A/AAAA  <br/> | FQDN web interne <br/> Web-int.contoso.com  <br/> | Avant le pool fin adresse VIP <br/> 192.168.21.121  <br/> |Définit le FQDN Web interne utilisé par Skype pour Business Web App  <br/> Si vous avez recours à l'équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs Web internes ne peuvent pas avoir le même nom de domaine complet.  <br/> ||
   
 Utilisé par un client pour découvrir le pool Front-End ou de serveur frontal et être authentifié et connecté en tant qu’utilisateur (s) **1** . Plus de détails sur ce est sur la [localisation des services Skype de procédure pas à pas pour les clients de l’entreprise](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).
  
 **2** il n’est nécessaire pour prendre en charge des clients hérités avant Lync 2013 et combinés de bureau.
  
 **3** dans le cas où un périphérique de Communications unifiées est allumé, mais un utilisateur n’a jamais ouvert une session dans le périphérique, l’enregistrement A permet de détecter le serveur hébergeant le service Web de mise à jour de périphérique et obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.
  
Le diagramme suivant illustre un exemple incluant des enregistrements DNS à la fois internes et externes, ainsi que de divers enregistrements indiqués dans les tableaux de cet article : 
  
**Diagramme de réseau de bord utilisation d’adresses IPv4 publiques**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**Mappages DNS de réseau de périmètre (interfaces internes et externes)**

|**Type d’enregistrement**|**Valeur**|**Correspond à**|**Objectif**|**Obligatoire**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Pool de bord interne complet  <br/>  _EdgePool-int.contoso.com_ <br/> |Adresses IP de côté interne bord pool  <br/> 172.25.33.10, 172.25.33.11  <br/> |Adresses IP de l'interface interne du pool Edge consolidé  <br/> |Y  <br/> |
|A/AAAA  <br/> |Nom de domaine complet de serveur Edge  <br/>  _Inconvénients-1.contoso.com_ <br/> |Adresse IP du serveur interne faisant face à un serveur dans le pool de bord  <br/> 172.25.33.10  <br/> |Créer un enregistrement pour chaque serveur dans le pool avec le nom de domaine complet du serveur en pointant sur son IP du nœud de serveur interne dans le pool, voir [Équilibrage de la charge de le DNS sur les Pools de serveurs Edge](load-balancing.md#BK_Edge).  <br/> |Y  <br/> |
|A/AAAA  <br/> |Service Edge d’accès FQDN du Pool  <br/>  _Access1.contoso.com_ <br/> |Accès côté service Pool des adresses IP externes  <br/> 131.107.16.10, 131.107.16.11  <br/> |Le service Edge d’accès fournit un point de connexion unique et approuvée pour le trafic de protocole SIP (Session Initiation) entrant et sortant.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Service du serveur Edge de conférence Web FQDN du Pool  <br/>  _Webcon1.contoso.com_ <br/> |Les adresses IP externes de service serveur Edge de conférence Web  <br/> 131.107.16.90, 131.107.16.91  <br/> |Le service de serveur Edge de conférence Web permet aux utilisateurs externes de participer à des conférences hébergées sur votre Skype interne pour un environnement de serveur d’entreprise.  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<-domaine sip\> _ Nom de domaine complet de pool <br/>  _AV1.contoso.com_ <br/> |Adresses IP externes de serveur Edge A/V  <br/> 131.107.16.170, 131.107.16.171  <br/> |A / V Edge service rend audio, vidéo, partage d’application et transfert de fichiers utilisateurs disponibles à externes.  <br/> |Y  <br/> |
|CNAME  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |FQDN du pool Edge d'accès externe  <br/>  _Access1.contoso.com_ <br/> |Localise le pool de serveur de transport Edge. Consultez la [procédure pas à pas de Skype pour les clients de l’entreprise recherche de services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls. _\<sipdomain\>_ <br/> _sip._tls. _Contoso.com_ <br/> |Bord d’accès externe complet  <br/>  _Access1.contoso.com_ <br/> |Utilisé pour l'accès externe des utilisateurs. Consultez la [procédure pas à pas de Skype pour les clients de l’entreprise recherche de services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp. _\<sipdomain\>_ <br/> _sipfederationtls._tcp. _Contoso.com_ <br/> |Bord d’accès externe complet  <br/>  _Access1.contoso.com_ <br/> |Utilisé pour la fédération et la connectivité PIC  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp. _\<sipdomain\>_ <br/> _xmpp-server._tcp. _Contoso.com_ <br/> |Bord d’accès externe complet  <br/>  _Access1.contoso.com_ <br/> |Le service Proxy de XMPP accepte et envoie des messages de protocole (XMPP) de présence et de messagerie extensible vers et à partir des partenaires fédérés de XMPP configurés.  <br/> |Oui, pour déployer la fédération ; sinon, facultatif  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> |Bord d’accès externe complet  <br/>  _Access1.contoso.com_ <br/> |Pour prendre en charge le Service de Notification de Push et le service de Notification de transmission Apple, vous créez un enregistrement SRV pour chaque domaine SIP. 3 <br/> ||
|A/AAAA  <br/> |Nom de domaine complet des services web de pool externe Front-End  <br/>  _Web-ext.contoso.com_ <br/> |Contrepasser les proxys pour l’adresse IP virtuelle de Services Web externes pour votre pool frontal 1 adresse IP publique du proxy, <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Avant fin pool interface externe utilisée par Skype pour Business Web App  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _Contoso.com_ <br/> |Reverse proxy public adresse IP correspond à l’adresse IP virtuelle de Services Web externes pour votre pool de directeur, si vous en avez, ou encore pour votre pool frontal si vous ne disposez pas d’un directeur de 2 <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> | Enregistrement externe pour client service de découverte automatique, également utilisé par la mobilité, Skype pour Business Web App et Planificateur Web app, résolu par le serveur proxy inverse <br/> Pour prendre en charge le Service de Notification de Push et le service de Notification de transmission Apple, vous créez un enregistrement SRV pour chaque domaine SIP avec les clients Microsoft Lync Mobile. 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |meet. _\<sipdomain\>_ <br/> meet. _Contoso.com_ <br/> |Reverse proxy public adresse IP correspond à l’interface Web externe pour le pool de Front-End  <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir [URL Simple](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |accès dans _ \<sipdomain\>_ <br/> accès à distance _contoso.com_ <br/> |Inverser les adresse IP publique du proxy, serveurs proxy à l’interface Web externe pour le pool de Front-End  <br/> 131.107.155.1 proxy d’à 192.168.21.120  <br/> |Proxy à Skype pour le Service Web d’entreprise  <br/> Voir [URL Simple](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |Pool de serveur d’applications Web Office nom de domaine complet  <br/> OWA.contoso.com  <br/> | Adresse IP publique proxy inverse, proxy vers l’interface Web externe pour un serveur Office Web Apps <br/> 131.107.155.1 proxy pour 192.168.1.5  <br/> | Pool de serveur d’applications Web Office adresse VIP <br/> 192.168.1.5  <br/> |Définit le nom de domaine complet du pool Office Web Apps Server  <br/> |
   
 **1** requis pour déployer la fédération, sinon facultative.
  
 Utilisé par un client pour découvrir le serveur frontal ou un pool de Front-End et être authentifié et connecté en tant qu’utilisateur (s) **2** .
  
 **3** cette exigence s’applique uniquement aux clients sur Apple ou Microsoft en fonction des périphériques mobiles. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.
  
 Pour plus d’informations sur les réseaux de périmètre et les serveurs Edge, consultez le contenu de [planification DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) de serveur de transport Edge.
  
> [!IMPORTANT]
> Skype pour Business Server prend en charge l’utilisation de l’adressage IPv6. Pour plus d’informations, consultez [planification d’IPv6 dans Skype pour les entreprises](ipv6.md) .
  
> [!IMPORTANT]
> Pour plus d’informations sur les noms de domaine complets, consultez [Concepts de base DNS](basics.md). 
  
 **Fractionner le cerveau DNS** 
 <a name="BK_split"> </a>
 
Fractionner le cerveau DNS est une configuration DNS où vous avez deux zones DNS avec le même espace de noms. La première zone DNS traite les demandes internes, tandis que la deuxième zone DNS traite les demandes externes. tel qu'indiqué dans les tableaux. Pour plus d'informations, consultez la section [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS). 
  
## <a name="hybrid-considerations"></a>Remarque sur les environnements hybrides
<a name="BK_Hybrid"> </a>

Si vous prévoyez d'héberger des utilisateurs en ligne et d'autres sur site, reportez-vous à la section [Paramètres DNS](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) hybrides. Vous devez configurer le service DNS comme d’habitude pour Skype pour Business Server 2015 et également ajouter d’autres enregistrements DNS. 
  
Également, consultez la section « URL d’Office 365 et l’adresse IP des plages » à [http://aka.ms/o365ips](http://aka.ms/o365ips) pour confirmer que vos utilisateurs auront accès aux ressources en ligne, ils ont besoin.
  
## <a name="simple-urls"></a>URL simples 
<a name="BK_Simple"> </a>

Une URL (Uniform Resource Locator) est une référence à une ressource Web qui spécifie son emplacement dans un réseau informatique et un protocole utilisé pour le récupérer. 
  
Skype pour Business Server prend en charge trois URL « simples » pour accéder aux services :
  
- **Meet** est l'URL de réunion de base pour toutes les conférences dans le site. Un exemple d’un simple aux URL est https://meet.contoso.com. Une URL pour une réunion donnée peut être https://meet.contoso.com/ _nom d’utilisateur_/7322994. 
    
    Avec l'URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre et à communiquer.
    
- **Dial-in** permet d'accéder à la page Web Paramètres de conférence rendez-vous. Cette page indique les numéros d'accès aux conférences et les langues dans lesquels ils sont disponibles. Elle présente également les informations relatives aux conférences affectées aux utilisateurs (c'est-à-dire, pour les réunions qui ne doivent pas être planifiées) et comporte des contrôles DTMF à utiliser en cours de conférence. Enfin, elle permet aux utilisateurs de gérer leur code confidentiel et les informations relatives aux conférences qui leur ont été affectées. L'URL simple de numérotation est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Un exemple d’URL simple accès à distance est https://dialin.contoso.com.
    
- **Admin** permet un accès rapide à la Skype pour le panneau de configuration de Business Server. À partir de n’importe quel ordinateur dans le pare-feu de votre organisation, un administrateur peut ouvrir le Skype pour panneau de commande du serveur Business en tapant l’URL d’administration simple dans un navigateur. L’URL simple Admin est interne à votre organisation. Un exemple de l’URL d’administration simple est https://admin.contoso.com.
    
URL simples sont décrits plus en détail à la [configuration DNS requise pour simples URL dans Skype pour Business Server 2015](simple-urls.md).
  
## <a name="dns-by-server-role"></a>DNS par rôle de serveur
<a name="BK_Servers"> </a>

Vous pouvez définir les noms de ces pools et serveurs comme bon vous semble, faciles à mémoriser et reflétant leur fonction dans le système.
  
### <a name="dns-records-for-individual-servers-or-pools"></a>Enregistrements DNS pour des serveurs ou pools spécifiques

Ces exigences d’enregistrement générique s’appliquent à tout rôle de serveur utilisé par Skype pour les entreprises. Un pool est un ensemble de serveurs exécutant les mêmes services qui fonctionnent ensemble pour traiter les demandes client qu'ils reçoivent via un équilibreur de charge. Voir [Configuration requise pour Skype pour entreprise l’équilibrage de charge](load-balancing.md) pour plus de détails
  
**Exigences en matière d’enregistrement DNS pour les rôles de serveur/pool (suppose que l’équilibrage de charge DNS)**

|**Scénario de déploiement**|**Condition requise pour DNS**|
|:-----|:-----|
|Un serveur :  <br/> Conversation permanente, directeur, serveur de médiation, serveur frontal  <br/> |Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|Pool :  <br/> Conversation permanente, directeur, serveur Edge, serveur de médiation, serveur frontal  <br/> |Un enregistrement interne A qui résout le nom de domaine complet (FQDN) de chaque nœud de serveur dans le pool sur son adresse IP.  <br/> **Exemple** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> Plusieurs enregistrements internes A qui résolvent le nom de domaine complet (FQDN) du pool sur les adresses IP des nœuds de serveurs dans le pool.  <br/> **Exemple** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>Rubriques sur les DNS spécifiques au serveur Edge

 Pour planifier un déploiement de serveur edge, passez en revue [le Plan de déploiement de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)et [planification de DNS du serveur de bord avancé de Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) qui comporte les sections suivantes
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Configuration automatique sans DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS Split-Brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

