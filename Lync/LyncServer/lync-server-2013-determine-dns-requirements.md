---
title: 'Lync Server 2013 : Détermination de la configuration requise pour DNS pour Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Détermination de la configuration requise pour DNS pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Utilisez le diagramme de flux suivant pour déterminer la configuration requise DNS (Domain Name System). Les modifications apportées aux mises à jour cumulatives pour Lync Server 2013:2013 février sont indiquées dans l’emplacement où ils s’appliquent.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 prend en charge l’utilisation de l’adressage IPv6. Pour utiliser les adresses IPv6, vous devez également fournir une prise en charge pour le DNS IPv6 et configurer les enregistrements d’hôte DNS AAAA (connus sous le nom de « Quad-A »). Dans les déploiements où IPv4 et IPv6 sont utilisés, il est préférable de configurer et de gérer les enregistrements d’hôte A pour IPv4 et l’hôte AAAA pour IPv6. Même si votre déploiement a été entièrement basculé vers IPv6, des enregistrements d’hôte DNS IPv4 peuvent toujours être requis lorsque des utilisateurs externes utilisent toujours IPv4.



</div>

**Déterminer le graphique de processus requis pour DNS**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet. Le générateur de topologie utilise les noms de domaine complets et non les noms d’hôte. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. <STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez pas les caractères ou traits de soulignement Unicode. Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat). Pour plus d’informations, voir <A href="lync-server-2013-configure-dns-host-records.md">configurer les enregistrements d’hôte DNS pour Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Comment les clients Lync trouvent les services

Microsoft Lync 2010, Lync 2013 et Lync mobile sont similaires dans la façon dont le client recherche et accède aux services dans Lync Server 2013. L’exception notable est l’application Lync du Windows Store qui utilise un processus d’emplacement de service différent. Cette section décrit en détail deux scénarios illustrant la façon dont les clients trouvent les services, d’abord la méthode classique à l’aide d’une série d’enregistrements SRV et en second lieu en utilisant uniquement les enregistrements du service de découverte automatique. Les mises à jour cumulatives apportées aux clients de bureau changent le processus d’emplacement DNS de Lync Server 2010 pour tous les clients, le processus de requête DNS se poursuit jusqu’à ce qu’une requête réussie soit renvoyée ou que la liste des enregistrements DNS possibles soit épuisée et que la dernière erreur soit retournée à le client.

Pour tous les clients, **à l’exception** de l’application Lync du Windows Store lors de la recherche DNS, les enregistrements SRV sont interrogés et renvoyés au client dans l’ordre suivant :

1.  lyncdiscoverinternal. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web internes

2.  lyncdiscover. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web externes

3.  \_sipinternaltls. \_TCP. \<enregistrement\> Domain SRV (service Locator) pour les connexions TLS internes

4.  \_sipinternal. \_TCP. \<enregistrement\> Domain SRV (Localisateur de service) pour les connexions TCP internes (exécuté uniquement si le protocole TCP est autorisé)

5.  \_SIP. \_TLS. \<enregistrement\> Domain SRV (service Locator) pour les connexions TLS externes

6.  sipinternal. \<l'\> enregistrement Domain A (Host) pour le pool frontal ou le directeur, résolu uniquement sur le réseau interne.

7.  SIP. \<enregistrement\> de domaine A (hôte) pour le pool frontal ou le directeur sur le réseau interne, ou le service Edge d’accès lorsque le client est externe

8.  sipexternal. \<enregistrement\> de domaine A (hôte) pour le service Edge d’accès lorsque le client est externe

L’application Lync du Windows Store modifie entièrement le processus, car elle utilise deux enregistrements :

1.  lyncdiscoverinternal. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web internes

2.  lyncdiscover. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web externes

Il n’y a aucun retour vers les autres types d’enregistrements.

La différence entre les méthodes utilisées pour les nouveaux clients par rapport aux clients plus anciens est que le service de découverte automatique devient la méthode préférée pour rechercher tous les services.

Quand une connexion est établie, le service de découverte automatique renvoie toutes les URL des services Web pour le pool de domicile de l’utilisateur, y compris le service de mobilité (connu sous le nom de MCX par le répertoire virtuel créé pour le service dans IIS), Microsoft Lync Web App et URL Web Scheduler. Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont associées au nom de domaine complet des services Web externes. Par conséquent, qu’il s’agisse d’un appareil mobile ou d’une connexion externe, l’appareil se connecte toujours au service de mobilité par le biais du proxy inverse.

Si les mises à jour cumulatives pour Lync Server 2013 : février 2013 ont été installées, le service de découverte automatique renvoie également des références à des éléments internes/UCWA, externes/UCWA et UCWA. Ces entrées font référence au composant WebPart Unified Communications Web API (UCWA). Pour l’instant, seul l’entrée UCWA est utilisée et fournit une référence à une URL pour le composant WebPart. UCWA est utilisé par les clients mobiles Lync 2013 au lieu du service de mobilité MCX utilisé par les clients mobiles Lync 2010.

<div>


> [!NOTE]  
> Lors de la création d’enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un enregistrement DNS A et AAAA (si vous utilisez l’adressage IPv6) dans le même domaine dans lequel l’enregistrement SRV DNS est créé. Par exemple, si l’enregistrement SRV est dans contoso.com, l’enregistrement A et le signe AAAA (si vous utilisez l’adressage IPv6) ne peuvent pas être dans fabrikam.com.



</div>

<div>


> [!TIP]  
> La configuration par défaut consiste à diriger tout le trafic du client mobile par le biais du site externe. Vous pouvez modifier les paramètres pour renvoyer uniquement l’URL interne, si cela est préférable pour vos exigences. Avec cette configuration, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’elles se trouvent à l’intérieur du réseau d’entreprise. Pour ce faire, vous devez utiliser l’applet <STRONG>de passe Set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Même si les applications mobiles peuvent également se connecter à d’autres services Lync Server 2013, tels que le service de carnet d’adresses, les demandes Web de l’application mobile interne sont dirigées vers le FQDN Web externe uniquement pour le service de mobilité. D’autres demandes de service, telles que des demandes de carnet d’adresses, ne nécessitent pas cette configuration.



</div>

Les appareils mobiles prennent en charge la découverte manuelle des services. Dans le cas présent, chaque utilisateur doit configurer les paramètres de l’appareil mobile avec les URI de service de découverte automatique internes et externes complets, y compris le protocole et le chemin d’accès comme suit :

  - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root pour l’accès externe

  - https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root pour l’accès interne

Nous vous recommandons d’utiliser la découverte automatique plutôt que la découverte manuelle. Toutefois, il peut s’avérer utile de résoudre les problèmes de connectivité des appareils mobiles.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configuration du système DNS split-brain avec Lync Server

Le système DNS split-brain est connu par un certain nombre de noms (par exemple, Split DNS ou Split-horizon). Il s’agit simplement d’une configuration DNS qui comporte deux zones DNS ayant le même espace de noms, mais une requête en interne uniquement pour les services de zone DNS, et les autres demandes externes aux services de zone DNS. Toutefois, la plupart des enregistrements DNS SRV et A contenus dans le DNS interne ne seront pas inclus dans le DNS externe et l’inverse est également vrai. Dans les cas où il existe le même enregistrement DNS dans le DNS interne et externe (par exemple, www.contoso.com), l’adresse IP renvoyée sera différente en fonction de la date à laquelle la requête a été lancée (interne ou externe).

<div>


> [!IMPORTANT]  
> Pour le moment, le DNS fractionné-Brain n’est pas pris en charge pour la mobilité, ou plus précisément, les enregistrements DNS LyncDiscover et LyncDiscoverInternal. LyncDiscover doit être défini sur un serveur DNS externe et LyncDiscoverInternal doit être défini sur un serveur DNS interne.



</div>

Dans le cadre de ces rubriques, le terme « DNS split-brain » sera utilisé.

Si vous configurez le système DNS fractionné-Brain, la zone interne et externe suivante contiennent un résumé des types d’enregistrements DNS requis dans chaque zone. Pour plus d’informations, reportez-vous à la rubrique [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interne :**

  - Contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone contoso.com interne contient les éléments suivants :
    
      - DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Lync Server 2013 interne (facultatif)
    
      - DNS A et AAAA (si vous utilisez l’adressage IPv6) ou les enregistrements CNAMe pour la découverte automatique des services Web Lync Server 2013 (facultatif)
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour le nom du pool frontal, le directeur ou le nom du pool de réalisateurs, ainsi que tous les serveurs internes exécutant Lync Server 2013 sur le réseau d’entreprise
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne latérale de chaque Lync Server 2013, serveur Edge du réseau de périmètre
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans le réseau de périmètre (facultatif pour la gestion du proxy inverse)
    
      - Toutes les interfaces Edge internes de Lync Server 2013 Edge Server dans le réseau de périmètre utilisent la zone DNS interne pour la résolution des requêtes vers contoso.com
    
      - Tous les serveurs exécutant Lync Server 2013 et les clients exécutant Lync 2013 dans le réseau d’entreprise pointent vers les serveurs DNS internes pour la résolution des requêtes vers contoso.com ou l’utilisation du fichier HOSTs sur chaque serveur Edge et de la liste A et des enregistrements AAAA (si vous utilisez l’adressage IPv6) pour serveur du tronçon suivant, en particulier le directeur ou le VIP du réalisateur, le protocole VIP de pool frontal ou le serveur Standard Edition Server

**DNS externe :**

  - Contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone contoso.com externe contient les éléments suivants :
    
      - DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Lync Server 2013 (facultatif)
    
      - DNS A et AAAA (si vous utilisez l’adressage IPv6) ou les enregistrements CNAMe pour la découverte automatique des services Web de Lync Server 2013 pour une utilisation avec la mobilité
    
      - DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour l’interface externe Edge de chaque adresse IP virtuelle Lync Server 2013, Edge Server ou du réseau de périmètre
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface externe du serveur proxy inverse ou d’une adresse IP virtuelle pour une réserve de serveurs proxy inverse dans le réseau de périmètre

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuration automatique sans DNS fractionné-Brain

À l’aide du système DNS fractionné-Brain, un utilisateur de Lync Server 2013 qui se connecte en interne peut tirer parti de la configuration automatique \_si la zone DNS interne contient une sipinternaltls. \_enregistrement SRV TCP pour chaque domaine SIP utilisé. Toutefois, si vous n’utilisez pas le DNS fractionné-Brain, la configuration automatique interne des clients exécutant Lync ne fonctionne pas, sauf si l’une des solutions de contournement décrites dans la section ci-après est implémentée. Le problème est dû au fait que Lync Server 2013 nécessite que l’URI SIP de l’utilisateur correspond au domaine du pool frontal destiné à la configuration automatique. C’est également le cas dans les versions antérieures de Communicator.

Par exemple, si deux domaines SIP sont utilisés, les enregistrements de service DNS (SRV) suivants sont nécessaires :

  - Si un utilisateur se connecte en tant que bob@contoso.com, l’enregistrement SRV suivant fonctionne pour la configuration automatique, car le domaine SIP de l’utilisateur (contoso.com) correspond au domaine du pool frontal de configuration automatique.
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un utilisateur se connecte en tant que alice@fabrikam.com, l’enregistrement SRV DNS suivant fonctionne pour la configuration automatique du deuxième domaine SIP.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Pour comparaison, si un utilisateur se connecte en tant que tim@litwareinc.com, l’enregistrement SRV DNS suivant ne fonctionne pas pour la configuration automatique, car le domaine SIP du client (litwareinc.com) ne correspond pas au domaine dans lequel se trouve le pool (fabrikam.com) :

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si la configuration automatique est requise pour les clients exécutant Lync, sélectionnez l’une des options suivantes :

  - **Les objets**   de stratégie de groupe utilisent des objets de stratégie de groupe pour renseigner les valeurs de serveur correctes.
    
    <div>
    

    > [!NOTE]  
    > Si cette option n’est pas activée dans le processus de configuration manuelle, vous n’avez pas besoin de configurer automatiquement les enregistrements SRV associés à la configuration automatique.

    
    </div>

  - **Zone interne correspondante**   créez une zone dans le DNS interne qui correspond à la zone DNS externe (par exemple, contoso.com), puis créez les enregistrements DNS a et aaaa (si vous utilisez l’adressage IPv6) correspondant au pool Lync Server 2013 utilisé pour la configuration automatique. Par exemple, si un utilisateur est hébergé sur pool01.contoso.net mais qu’il se connecte à Lync en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com et à l’intérieur de cette dernière, créez un enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour pool01.contoso.com.

  - **Zone de point d’épingle**   si vous créez une zone entière dans le DNS interne n’est pas une option disponible, vous pouvez créer des zones de point d’épingle (qui sont dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique et remplir ces zones à l’aide de dnscmd. exe. Dnscmd. exe est requis, car l’interface utilisateur DNS ne prend pas en charge la création de zones au lieu de punaise. Par exemple, si le domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 qui contient deux serveurs frontaux, vous avez besoin des zones de points de repère et des enregistrements A suivants dans votre DNS interne :
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Si votre environnement contient un deuxième domaine SIP (par exemple, fabrikam.com), vous avez besoin des zones de points de repère et des enregistrements A suivants dans votre DNS interne :
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> Le nom de domaine complet (FQDN) du pool frontal apparaît deux fois, mais avec deux adresses IP différentes. En effet, l’équilibrage de charge DNS est utilisé, mais si l’équilibrage de charge matérielle est utilisé, il n’y a qu’une entrée de pool frontal unique. Par ailleurs, les valeurs de nom de domaine complet (FQDN) du pool frontal changent entre l’exemple contoso.com et l’exemple fabrikam.com, mais les adresses IP restent identiques. En effet, les utilisateurs qui se connectent à partir d’un domaine SIP utilisent le même pool frontal pour la configuration automatique.



</div>

Pour plus d’informations, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)l’article de blog DMTF « configuration automatique de Communicator et DNS split-brain ».

<div>


> [!NOTE]  
> Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configuration du DNS (Domain Name System) pour la récupération d’urgence

Pour configurer le système DNS afin de rediriger le trafic Web de Lync Server 2013 vers vos sites de reprise et de basculement sur incident, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour le Web de manière à ce qu’ils prennent en charge la récupération après sinistre, de sorte que les fonctionnalités qui utilisent les services Web continuent de fonctionner, même si une seule partie du frontale s’affiche. Cette fonctionnalité de reprise après sinistre prend en charge la découverte automatique (URL Lyncdiscover), la réunion et les URL simples de connexion.

Vous pouvez définir et configurer des enregistrements DNS supplémentaires (A et AAAA si vous utilisez des enregistrements IPv6) pour la résolution interne et externe des services Web auprès de votre fournisseur de services de GeoDNS. Les détails suivants présupposent que le niveau de répartition des réserves, géographiquement et GeoDNS est pris en charge par votre fournisseur avec le DNS à répétition alternée ou configuré pour utiliser Pool1 comme principal, et basculer vers Pool2 en cas de perte de communication ou de défaillance matérielle.


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
<th>Enregistrements du pool (exemple)</th>
<th>Enregistrements CNAMe (exemple)</th>
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
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias de Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias de Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Utiliser le principal, se connecter à Secondary en cas d’échec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS Load Balancing

L’équilibrage de charge DNS est généralement implémenté au niveau de l’application. Dans le cas contraire, l’application (par exemple, un client exécutant Lync) essaie de se connecter à un serveur dans un pool en se connectant à l’une des adresses IP renvoyées à partir de l’enregistrement DNS A et du nom de domaine AAAA (si l’adressage IPv6 est utilisé).

Par exemple, s’il existe trois serveurs front end dans un pool intitulé pool01.contoso.com, les informations suivantes se produisent :

  - Les clients exécutant une requête Lync DNS pour pool01.contoso.com. La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre) :
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Le client tente d’établir une connexion TCP (Transmission Control Protocol) vers l’une des adresses IP. En cas d’échec, le client tente l’adresse IP suivante dans le cache.

  - Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.

  - Si le client tente d’accéder à toutes les entrées du cache sans connexion réussie, l’utilisateur est prévenu qu’aucun serveur exécutant Lync Server 2013 n’est disponible pour le moment.

<div>


> [!NOTE]  
> Le service d’équilibrage de charge DNS est différent de l’équilibrage de charge DNS (RR) qui fait généralement référence à l’équilibrage de charge en fonction du système DNS, qui fournit un ordre différent d’adresses IP correspondant aux serveurs d’un pool. En règle générale, le RR DNS active uniquement la distribution de charge, mais n’autorise pas le basculement. Par exemple, si la connexion à une adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue. C’est la raison pour laquelle le tourniquet DNS est plutôt moins fiable que le service d’équilibrage de charge DNS. Vous pouvez utiliser le tourniquet DNS conjointement avec l’équilibrage de charge DNS.



</div>

L’équilibrage de charge DNS est utilisé pour les éléments suivants :

  - Équilibrage de la charge de serveur à serveur SIP aux serveurs de périphérie

  - Les applications UCAS (Unified Communications application Services) de répartition de charge telles que le standard automatique des conférences, le groupe de réponse et le parc d’appels

  - Interdiction de nouvelles connexions aux applications UCAS (également appelées « drainage »)

  - Équilibrage de la charge de tout le trafic client à serveur entre les clients et les serveurs de périphérie

L’équilibrage de charge DNS ne peut pas être utilisé pour les éléments suivants :

  - Trafic Web de client à serveur vers le directeur ou les serveurs frontaux

Équilibrage de charge DNS et trafic fédéré :

Si plusieurs enregistrements DNS sont renvoyés par une requête DNS SRV, le service Edge d’accès sélectionne toujours l’enregistrement SRV DNS avec la priorité numérique la plus basse et la pondération numérique la plus élevée. Le document « IETF (Internet Engineering Task Force » "un RR DNS pour spécifier l’emplacement des services ( <http://www.ietf.org/rfc/rfc2782.txt> DNS SRV)" spécifie que, si plusieurs enregistrements SRV DNS sont définis, la priorité est d’abord utilisée, puis pondération. Par exemple, l’enregistrement SRV DNS a a une épaisseur de 20 et une priorité de 40 et de l’enregistrement SRV DNS B a une épaisseur de 10 et de Priority 50. L’enregistrement SRV DNS A avec la priorité 40 est sélectionnée. Les règles suivantes s’appliquent à la sélection d’enregistrements SRV DNS :

  - Priority est considéré comme premier. Un client doit tenter de contacter l’hôte cible défini par l’enregistrement SRV DNS dont la priorité numéro faible peut être atteinte. Les cibles de même priorité doivent être essayées dans un ordre défini par le champ pondération.

  - Le champ poids spécifie une pondération relative pour les entrées ayant la même priorité. Le plus grand nombre de pondérations doit être proportionnel à la sélection. Les administrateurs DNS doivent utiliser le poids 0 quand il n’y a pas de sélection de serveur à effectuer. En présence d’enregistrements contenant des pondérations supérieures à 0, les enregistrements de poids 0 doivent avoir une très petite chance d’être sélectionnés.

Si plusieurs enregistrements SRV DNS ayant une priorité et un poids identiques sont retournés, le service Edge d’accès sélectionne l’enregistrement SRV reçu en premier du serveur DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

