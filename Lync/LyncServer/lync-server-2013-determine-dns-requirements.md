---
title: "Lync Server 2013 : Dét. de la conf. req. pour DNS pour Lync Server 2013"
TOCTitle: Détermination de la configuration requise pour DNS pour Lync Server 2013
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398758(v=OCS.15)
ms:contentKeyID: 49298120
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Détermination de la configuration requise pour DNS pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Utilisez l’organigramme suivant pour déterminer les exigences relatives au système DNS (Domain Name System). Les modifications concernant les Mises à jour cumulatives pour Lync Server 2013 de février 2013 sont notées là où elles sont applicables.

> [!IMPORTANT]  
> Microsoft Lync Server 2013 prend en charge l’utilisation de l’adressage IPv6. Pour utiliser les adresses IPv6, vous devez également fournir la prise en charge d’un DNS IPv6 et configurer les enregistrements AAAA (également connus sous le nom de « quad-A »). Dans les déploiements où IPv4 et IPv6 sont utilisés, il est préférable de configurer et maintenir à la fois des enregistrements A hôtes pour IPv4 et des enregistrements AAAA hôtes pour IPv6. Même si votre déploiement a subi une transition complète vers IPv6, des enregistrements hôtes DNS IPv4 peuvent encore être nécessaires lorsque des utilisateurs externes utilisent encore IPv4.

**Organigramme des enregistrements DNS requis**

![Diagramme des exigences DNS](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "Diagramme des exigences DNS")

> [!IMPORTANT]  
> Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet. Le Générateur de topologie utilise des noms de domaine complets, pas des noms d’hôtes. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. <strong>Utilisez uniquement des caractères standard</strong> (A–Z, a–z, 0–9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont généralement pas pris en charge par les systèmes DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configure-dns-host-records.md">Configuration des enregistrements hôte DNS pour Lync Server 2013</a>.

## Comment les clients Lync localisent les services

Microsoft Lync 2010, Lync 2013 et Lync Mobile sont semblables dans la manière dont le client trouve et accède aux services dans Lync Server 2013. La principale exception concerne l’application Lync du Windows Store qui utilise un processus de recherche de service différent. Cette section détaille deux scénarios de recherche des services par les clients, tout d’abord selon la méthode traditionnelle à l’aide d’une série d’enregistrements SRV et d’enregistrements d’hôtes A, puis à l’aide des enregistrements du service de découverte automatique uniquement. Les mises à jour cumulatives des clients de bureau modifient le processus de recherche DNS par rapport à Lync Server 2010. Pour tous les clients, le processus d’interrogation DNS continue jusqu’à ce qu’une requête aboutisse ou que la liste d’enregistrements DNS possibles soit épuisée et que l’erreur finale soit renvoyée au client.

Pour tous les clients **à l’exception** de l’application Lync du Windows Store Au cours de la recherche DNS, les enregistrements SRV sont interrogés et renvoyés au client dans l’ordre suivant :

1.  lyncdiscoverinternal. *\<domaine\>*    Enregistrement A (hôte) pour le service de découverte automatique sur les services web internes

2.  lyncdiscover. *\<domaine\>*    Enregistrement A (hôte) pour le service de découverte automatique sur les services web externes

3.  \_sipinternaltls.\_tcp. *\<domaine\>*    Enregistrement SRV (localisation de service) pour les connexions TLS internes

4.  \_sipinternal.\_tcp. *\<domaine\>*    Enregistrement SRV (localisation de service) pour les connexions TCP (uniquement si le protocole TCP est autorisé)

5.  \_sip.\_tls. *\<domaine\>*    Enregistrement SRV (localisation de service) pour les connexions TLS externes

6.  sipinternal. *\<domaine\>*    Enregistrement A (hôte) pour le pool de serveurs frontaux ou directeur, résolvable uniquement sur le réseau interne

7.  sip. *\<domaine\>*    Enregistrement A (hôte) pour le pool de serveurs frontaux ou directeur sur le réseau interne, ou le service Edge d’accès lorsque le client est externe

8.  sipexternal. *\<domaine\>*    Enregistrement A (hôte) pour le service Edge d’accès lorsque le client est externe

L’application Lync du Windows Store modifie entièrement le processus car elle utilise deux enregistrements :

1.  lyncdiscoverinternal. *\<domaine\>*    Enregistrement A (hôte) pour le service de découverte automatique sur les services web internes

2.  lyncdiscover. *\<domaine\>*    Enregistrement A (hôte) pour le service de découverte automatique sur les services web externes

Il n’existe aucune solution de secours pour les autres types d’enregistrements.

La différence entre les méthodes employées pour les clients les plus récents et les anciens clients est que le service de découverte automatique devient progressivement la méthode préférée pour rechercher tous les services.

Lorsqu’une connexion est établie, le service de découverte automatique renvoie toutes les URL des services web correspondant au pool d’accueil de l’utilisateur, y compris les URL du service de mobilité (appelé Mcx par le répertoire virtuel créé pour le service dans les services Internet \[IIS\]), de Microsoft Lync Web App et du Planificateur web. Cependant, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont toutes deux associées au nom de domaine complet externe des services web. Par conséquent, qu’il soit interne ou externe au réseau, un appareil mobile se connecte toujours au service de mobilité de manière externe par le biais du proxy inverse.

Si les Mises à jour cumulatives pour Lync Server 2013 de février 2013 ont été installées, le service de découverte automatique renvoie également des références à Internal/UCWA, External/UCWA et UCWA. Ces entrées font référence au composant web de l’API web de communications unifiées (UCWA). À l’heure actuelle, seule l’entrée UCWA est utilisée et fournit une référence à une URL pour le composant web. UCWA est utilisé par les clients Lync 2013 Mobile au lieu du service de mobilité Mcx utilisé par les clients Lync 2010 Mobile.

> [!NOTE]  
> Lors de la création d’enregistrements SRV, n’oubliez pas qu’ils doivent pointer vers un enregistrement DNS (A) et AAAA (si vous utilisez l’adressage IPv6) dans le même domaine que celui sur lequel l’enregistrement DNS SRV est créé. Par exemple, si l’enregistrement SRV se trouve dans contoso.com, l’enregistrement A et AAAA (si vous utilisez l’adressage IPv6) sur lequel il pointe ne peut pas se trouver dans fabrikam.com.

> [!TIP]  
> La configuration par défaut consiste à diriger tout le trafic des clients mobiles à travers le site externe. Vous pouvez modifier les paramètres de façon à renvoyer uniquement l’URL interne, si cela correspond davantage à vos exigences. Dans cette configuration, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau d’entreprise. Pour définir cette configuration, vous devez exécuter l’applet de commande <strong>Set-CsMcxConfiguration</strong>.

> [!NOTE]  
> Même si les applications mobiles peuvent également se connecter à d’autres services Lync Server 2013, tels que le service de carnet d’adresses, les demandes web des applications mobiles internes vont au nom de domaine complet web externe uniquement pour le service de mobilité. Cette configuration n’est pas nécessaire pour les autres demandes de services, telles que les demandes de carnet d’adresses.

Les appareils mobiles prennent en charge la découverte manuelle des services. Dans ce cas, chaque utilisateur doit configurer les paramètres de l’appareil mobile avec les URI complètes interne et externe du service de découverte automatique, y compris le protocole et le chemin d’accès, comme suit :

  - https:// *\<nom\_domaine\_complet\_pool\_ext\>* /Autodiscover/autodiscoverservice.svc/Racine pour l’accès externe

  - https:// *\<nom\_domaine\_complet\_pool\_int\>* /AutoDiscover/AutoDiscover.svc/Racine pour l’accès interne

L’utilisation de la découverte automatique, plutôt que manuelle, est vivement recommandée. Cependant, le recours aux paramètres manuels est utile pour la résolution des problèmes de connectivité d’appareil mobile.

## Configuration DNS « split-brain » avec Lync Server

Le terme DNS split-brain est connu sous différents, parmi lesquels « split DNS » et « split-horizon DNS ». Il décrit une configuration DNS dans laquelle il existe deux zones DNS avec le même espace de noms (l’une répond aux demandes internes et l’autre aux demandes externes). Cependant, de nombreux enregistrements DNS (SRV et A) contenus dans le DNS interne ne seront pas contenus dans le DNS externe, et inversement. Dans les cas où le même enregistrement DNS existe à la fois dans le DNS interne et externe (par exemple, www<span/>.contoso.com), l’adresse IP renvoyée sera différente en fonction de l’endroit d’où provient la requête (interne ou externe).

> [!IMPORTANT]  
> Actuellement, DNS split-Brain n’est pas pris en charge pour la mobilité ou, plus précisément, les enregistrements DNS LyncDiscover et LyncDiscoverInternal. LyncDiscover doit être défini sur un serveur DNS externe et LyncDiscoverInternal doit être défini sur un serveur DNS interne.

Pour les besoins de ces rubriques, le terme DNS split-brain sera utilisé.

Si vous configurez DNS split-brain, les zones interne et externe suivantes contiennent un résumé des types d’enregistrements DNS requis dans chaque zone. Pour plus d’informations, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interne :**

  - contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone interne contoso.com contient :
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 interne (facultatif) ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAME pour la découverte automatique des services web Lync Server 2013 (facultatif) ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) le nom du pool frontal, le directeur ou nom du pool directeur et pour tous les serveurs internes exécutant Lync Server 2013 sur le réseau d’entreprise ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne Edge de chaque serveur Lync Server 2013, serveur Edge sur le réseau de périmètre ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse sur le réseau de périmètre (facultatif pour la gestion de proxy inverse) ;
    
      - toutes les interfaces Edge internes de serveur EdgeLync Server 2013 sur le réseau de périmètre utilisent la zone DNS interne pour résoudre les requêtes vers contoso.com ;
    
      - tous les serveurs exécutant Lync Server 2013 et les clients exécutant Lync 2013 sur le réseau d’entreprise pointent vers les serveurs DNS internes pour résoudre les requêtes vers contoso.com, ou utilisation de fichiers HOSTS sur chaque serveur Edge et mention d’enregistrements A et AAAA (si vous utilisez l’adressage IPv6) pour le serveur de tronçon suivant, plus spécifiquement le directeur ou adresse VIP de directeur, adresse VIP de pool frontal ou serveur Standard Edition.

**DNS externe :**

  - contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone externe contoso.com contient :
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 (facultatif) ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAME pour la découverte automatique des services web Lync Server 2013 pour une utilisation avec la mobilité ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour l’interface externe Edge de chaque serveur Lync Server 2013, serveur Edge ou adresse IP virtuelle (VIP) d’équilibrage de la charge matérielle sur le réseau de périmètre ;
    
      - des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface externe du serveur proxy inverse ou adresse VIP pour un pool de serveurs proxy inverse sur le réseau de périmètre.

## Configuration automatique sans DNS split-brain

Avec le DNS split-brain, un utilisateur Lync Server 2013 qui se connecte en interne peut tirer parti de la configuration automatique si la zone DNS interne contient un enregistrement SRV \_sipinternaltls.\_tcp pour chaque domaine SIP utilisé. Cependant, si vous n’utilisez pas DNS split-brain, la configuration interne automatique des clients Lync ne fonctionnera pas tant qu’une des solutions décrites dans la suite de cette section n’aura pas été mise en œuvre. Cela est dû au fait que Lync Server 2013 a besoin que l’URI SIP de l’utilisateur corresponde au domaine du pool frontal destiné à la configuration automatique. C’est également le cas avec les versions précédentes de Communicator.

Si par exemple, vous avez deux domaines SIP utilisés, les enregistrements DNS SRV suivants seront nécessaires :

  - Si un utilisateur se connecte en tant que bob@contoso, l’enregistrement SRV suivant fonctionnera pour la configuration automatique, car le domaine SIP de l’utilisateur (contoso.com) correspond au domaine du pool frontal de configuration automatique :
    
     \_sipinternaltls.\_tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un utilisateur se connecte en tant que alice@fabrikam, l’enregistrement DNS SRV suivant fonctionnera pour la configuration automatique du deuxième domaine SIP.
    
     \_sipinternaltls.\_tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

À titre de comparaison, si un utilisateur se connecte en tant que tim@litwareinc, l’enregistrement DNS SRV suivant ne fonctionnera pas pour la configuration automatique, car le domaine SIP du client (litwareinc.com) ne correspond pas au domaine sur lequel se trouve le pool (fabrikam.com) :

 \_sipinternaltls.\_tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si la configuration automatique est requise pour les clients Lync, sélectionnez l’une des options suivantes :

  - **Objets de stratégie de groupe**   Utilisez les objets de stratégie de groupe (GPO) pour remplir le serveur avec les valeurs correctes.
    
    > [!NOTE]  
    > Cette option n’active pas la configuration automatique, mais automatise le processus de configuration manuelle. Par conséquent, en suivant cette approche, les enregistrements SRV associés à la configuration automatique ne sont pas nécessaires.

  - **Zone interne correspondante**   Créez une zone dans le DNS interne qui correspond à la zone DNS externe (par exemple, contoso.com) et créez les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) correspondant au pool Lync Server 2013 utilisé pour la configuration automatique. Par exemple, si un utilisateur est hébergé sur pool01.contoso.net mais se connecte sur Lync en tant que bob@contoso, créez une zone DNS interne appelée contoso.com dans laquelle vous créez un enregistrement DNS A et AAAA (si vous utilisez l’adressage IPv6) pour pool01.contoso.com.

  - **Repérer la zone interne**   Si la création d’une zone complète dans le DNS interne n’est pas une solution, vous pouvez créer des zones repère (c’est-à-dire dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique et renseigner ces zones à l’aide de dnscmd.exe. Dnscmd.exe est obligatoire car l’interface utilisateur DNS ne prend pas en charge la création de zones repère. Par exemple, si le domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 contenant deux serveurs frontaux, vous avez besoin des zones repère en enregistrements A suivants dans votre DNS interne :
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Si votre environnement contient un deuxième domaine SIP (par exemple, fabrikam.com), vous avez besoin des zones repère et des enregistrements A suivants dans votre DNS interne :
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

> [!NOTE]  
> Le nom de domaine complet du pool frontal s’affiche deux fois, mais avec deux adresses IP différentes. Cela est dû à l’utilisation de l’équilibrage de la charge DNS, mais si l’équilibrage de la charge matérielle était utilisé, il n’y aurait qu’une seule entrée de pool frontal. De même, les valeurs du nom de domaine complet du pool frontal entre l’exemple contoso.com et l’exemple fabrikam.com changent, mais les adresses IP sont conservées. La raison est que les utilisateurs qui se connectent à partir de l’un de ces domaines IP utilisent le même pool frontal pour la configuration automatique.

Pour plus d’informations, reportez-vous à l’article du blog DMTF intitulé « Configuration automatique de Communicator et DNS split-brain » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).

> [!NOTE]  
> Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.

## Configuration du système de noms de domaine (DNS) pour la récupération d’urgence

Pour configurer le système DNS de façon à rediriger le trafic web Lync Server 2013 vers vos sites de récupération d’urgence et de basculement, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour le web afin de prendre en charge la récupération d’urgence, de sorte que les fonctionnalités qui utilisent des services web continuent d’être opérationnelles même en cas de panne d’un pool de serveurs frontaux entier. Cette fonctionnalité de récupération d’urgence prend en charge les URL simples de découverte automatique (URL Lyncdiscover), de réunion et de rendez-vous.

Vous définissez et configurez des enregistrements hôtes DNS (A et AAAA en cas d’utilisation d’IPv6) supplémentaires pour la résolution interne et externe des services web au niveau de votre fournisseur GeoDNS. Les détails suivants supposent l’existence de pools associés et géographiquement dispersés, et le fait que GeoDNS est pris en charge par votre fournisseur avec DNS round-robin ou qu’il est configuré de façon à utiliser Pool1 comme pool principal et à basculer vers Pool2 en cas de perte de communication ou de défaillance matérielle.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Enregistrement GeoDNS (exemple)</th>
<th>Enregistrements de pool (exemple)</th>
<th>Enregistrements CNAME (exemple)</th>
<th>Paramètres DNS (sélectionnez une option)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utilisez le principal, se connecter au secondaire en cas de défaillance</p></td>
</tr>
</tbody>
</table>


## Équilibrage de charge DNS

L’équilibrage de la charge DNS est généralement mis en œuvre au niveau de l’application. L’application (par exemple, un client Lync) essaie de se connecter à un serveur d’un pool en se connectant à l’une des adresses IP résultant de la requête d’enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour le nom de domaine complet du pool.

Si par exemple, il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, voilà ce qui se produit :

  - Les clients Lync interrogent le système DNS pour pool01.contoso.com. La requête renvoie trois adresses IP et les met dans le cache comme suit (pas nécessairement dans cet ordre) :
    
    pool01.contoso.com      192.168.10.90
    
    pool01.contoso.com      192.168.10.91
    
    pool01.contoso.com      192.168.10.92

  - Le client tente d’établir une connexion TCP à l’une des adresses IP. En cas d’échec, le client essaie l’adresse IP suivante dans le cache.

  - Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.

  - Si le client essaie toutes les entrées mises en cache et que la connexion échoue, l’utilisateur est informé qu’aucun serveur Lync Server 2013 n’est disponible pour le moment.

> [!NOTE]  
> L’équilibrage de la charge DNS est différent du tourniquet (round robin) DNS (DNS RR), qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour fournir un ordre d’adresses IP différent correspondant aux serveurs d’un pool. DNS RR active en général uniquement la distribution de la charge, mais n’active pas le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue. Par conséquent, le tourniquet DNS (round robin) seul est moins fiable que l’équilibrage de la charge DNS. Vous pouvez utiliser le tourniquet DNS (round robin) conjointement avec l’équilibrage de la charge DNS.

L’équilibrage de la charge DNS est utilisé dans les cas suivants :

  - Équilibrage de la charge du trafic SIP vers les serveurs Edge

  - Équilibrage de la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel.

  - Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)

  - Équilibrage de la charge de l’ensemble du trafic client-serveur entre les clients et les serveurs Edge

L’équilibrage de la charge DNS ne peut pas être utilisé dans les cas suivants :

  - Trafic web de client à serveur vers serveurs frontaux ou directeurs

Équilibrage de la charge DNS et trafic fédéré :

Si plusieurs enregistrements DNS sont renvoyés par une requête SRV DNS, le service Edge d’accès choisit toujours l’enregistrement SRV DNS dont la priorité numérique est la plus faible et le poids numérique le plus élevé. Le document de l’Internet Engineering Task Force intitulé « A DNS RR for specifying the location of services (DNS SRV) » <http://www.ietf.org/rfc/rfc2782.txt> stipule que si plusieurs enregistrements SRV DNS sont définis, la priorité est utilisée en premier, puis le poids. Par exemple, si un enregistrement SRV DNS A a un poids de 20 et une priorité de 40 et qu’un enregistrement SRV DNS B a un poids de 10 et une priorité de 50, c’est l’enregistrement SRV DNS A avec une priorité de 40 qui sera sélectionné. Les règles suivantes s’appliquent à la sélection des enregistrements SRV DNS :

  - La priorité est prise en compte en premier. Un client DOIT tenter de contacter l’hôte cible défini par l’enregistrement SRV DNS ayant le chiffre de priorité le plus faible parmi ceux qu’il peut joindre. Pour les cibles ayant la même priorité, la tentative de connexion DOIT être effectuée en fonction d’un ordre défini par le champ de poids.

  - Le champ de poids spécifie un poids relatif pour les entrées de même priorité. Les poids plus élevés DOIVENT présenter une probabilité de sélection proportionnellement plus élevée. Les administrateurs DNS DOIVENT utiliser un poids égal à 0 quand il n’y a aucune sélection de serveur à effectuer. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements de poids nul doivent avoir une chance très faible d’être sélectionnés.

Si plusieurs enregistrements SRV DNS de même priorité et de même poids sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV qui a été reçu en premier en provenance du serveur DNS.

