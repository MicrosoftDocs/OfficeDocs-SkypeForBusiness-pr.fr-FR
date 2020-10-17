---
title: 'Lync Server 2013 : déterminer les exigences DNS'
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
ms.openlocfilehash: d00f86eb437f673e83e2ea2e610ad9b35dbea082
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522601"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>Déterminer les exigences DNS pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Utilisez l’organigramme suivant pour déterminer les enregistrements DNS requis. Les modifications apportées aux mises à jour cumulatives pour Lync Server 2013 : février 2013 sont indiquées à l’endroit où elles s’appliquent.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 prend en charge l’utilisation de l’adressage IPv6. Pour utiliser les adresses IPv6, vous devez également fournir la prise en charge du DNS IPv6 et configurer les enregistrements d’hôte DNS AAAA (appelés « Quad-A »). Dans les déploiements où les protocoles IPv4 et IPv6 sont utilisés, il est préférable de configurer et de gérer à la fois les enregistrements d’hôte A pour IPv4 et l’hôte AAAA pour IPv6. Même si votre déploiement a été intégralement transféré vers IPv6, les enregistrements d’hôte DNS IPv4 peuvent toujours être requis lorsque des utilisateurs externes continuent à utiliser IPv4.



</div>

**Détermination de l’organigramme des enregistrements DNS requis**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Par défaut, le nom d’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet (FQDN). Le générateur de topologie utilise des noms de domaine complets, pas des noms d’hôte. Par conséquent, vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non membre d’un domaine. <STRONG>Utilisez uniquement des caractères standard</STRONG> (A–Z, a–z, 0–9 et tirets) lorsque vous assignez des noms de domaines complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaines complets ne sont généralement pas pris en charge par les DNS externes et les autorités publiques de certification (c’est-à-dire lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat). Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-host-records.md">configurer des enregistrements d’hôte DNS pour Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Comment les clients Lync localisent les services

Microsoft Lync 2010, Lync 2013 et Lync mobile sont similaires dans la façon dont le client trouve et accède aux services dans Lync Server 2013. L’exception notable est l’application Lync Windows Store qui utilise un processus d’emplacement de service différent. Cette section décrit deux scénarios de localisation des services par les clients, la méthode traditionnelle qui utilise une série d’enregistrements d’hôte SRV et A, ainsi que les enregistrements du service de découverte automatique uniquement. Les mises à jour cumulatives des clients de bureau modifient le processus d’emplacement DNS à partir de Lync Server 2010 pour tous les clients, le processus de requête DNS continue jusqu’à ce qu’une requête réussie soit renvoyée, ou la liste des enregistrements DNS possibles soit épuisée et la dernière erreur est renvoyée au client.

Pour tous les clients **à l’exception** de l’application Lync Windows Store pendant la recherche DNS, les enregistrements SRV sont interrogés et renvoyés au client dans l’ordre suivant :

1.  lyncdiscoverinternal. \<domain\>     Enregistrement A (hôte) pour le service de découverte automatique sur les services Web internes

2.  lyncdiscover. \<domain\>     Enregistrement A (hôte) pour le service de découverte automatique sur les services Web externes

3.  \_sipinternaltls. \_ TCP. \<domain\>     Enregistrement SRV (Localisateur de service) pour les connexions TLS internes

4.  \_sipinternal. \_ TCP. \<domain\>     Enregistrement SRV (Localisateur de service) pour les connexions TCP internes (effectué uniquement si TCP est autorisé)

5.  \_SIP. \_ TLS. \<domain\>     Enregistrement SRV (Localisateur de service) pour les connexions TLS externes

6.  sipinternal. \<domain\>     Enregistrement A (hôte) pour le pool frontal ou le directeur, pouvant être résolu uniquement sur le réseau interne

7.  SIP. \<domain\>     Un enregistrement (hôte) pour le pool frontal ou le directeur sur le réseau interne, ou le service Edge d’accès lorsque le client est externe

8.  sipexternal. \<domain\>     Enregistrement A (hôte) pour le service Edge d’accès lorsque le client est externe

L’application Lync Windows Store modifie complètement le processus, car il utilise deux enregistrements :

1.  lyncdiscoverinternal. \<domain\>     Enregistrement A (hôte) pour le service de découverte automatique sur les services Web internes

2.  lyncdiscover. \<domain\>     Enregistrement A (hôte) pour le service de découverte automatique sur les services Web externes

Il n’y a pas de secours pour les autres types d’enregistrements.

La différence entre les méthodes utilisées pour les clients plus récents et les clients plus anciens est que le service de découverte automatique devient la méthode préférée pour rechercher tous les services.

Lorsqu’une connexion réussit, le service de découverte automatique renvoie toutes les URL des services Web pour le pool d’accueil de l’utilisateur, y compris le service de mobilité (appelé MCX par le répertoire virtuel créé pour le service dans les services Internet (IIS), Microsoft Lync Web App et les URL du planificateur Web. Toutefois, l'URL du Service Mobilité interne et l'URL du Service Mobilité externe sont associées au nom de domaine complet des services web externes. Par conséquent, qu’il soit interne ou externe au réseau, un appareil mobile se connecte toujours au service de mobilité de manière externe, par le biais du proxy inverse.

Si les mises à jour cumulatives pour Lync Server 2013 : février 2013 ont été installées, le service de découverte automatique renvoie également des références à Internal/UCWA, External/UCWA et UCWA. Ces entrées font référence au composant web de l'API web Unified Communications (UCWA). Actuellement, seule l’entrée UCWA est utilisée et fournit une référence à une URL pour le composant Web. UCWA est utilisé par les clients mobiles Lync 2013 au lieu du service de mobilité MCX utilisé par les clients mobiles Lync 2010.

<div>


> [!NOTE]  
> Lors de la création d’enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un enregistrement DNS A et AAAA (si vous utilisez l’adressage IPv6) dans le même domaine que celui dans lequel l’enregistrement DNS SRV est créé. Par exemple, si l’enregistrement SRV se trouve dans contoso.com, l’enregistrement A et AAAA (si vous utilisez l’adressage IPv6) sur lequel pointe vers ne peut pas être dans fabrikam.com.



</div>

<div>


> [!TIP]  
> La configuration par défaut consiste à diriger tout le trafic client mobile via le site externe. Vous pouvez modifier les paramètres pour qu’ils ne renvoient que l’URL interne, si cela est plus préférable pour vos besoins. Dans cette configuration, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau d’entreprise. Pour définir cette configuration, vous utilisez la cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Bien que les applications mobiles puissent également se connecter à d’autres services Lync Server 2013, tels que le service de carnet d’adresses, les demandes Web d’applications mobiles internes sont dirigées vers le nom de domaine complet Web externe uniquement pour le service de mobilité. Cette configuration n’est pas nécessaire pour les autres demandes de services, telles que les demandes de carnet d’adresses.



</div>

Les appareils mobiles prennent en charge la découverte manuelle des services. Dans ce cas, chaque utilisateur doit configurer les paramètres de l’appareil mobile avec les URI complètes interne et externe du service de découverte automatique, y compris le protocole et le chemin d’accès, comme suit :

  - https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/root pour l’accès externe

  - https:// \<IntPoolFQDN\> /autodiscover/autodiscover.svc/root pour l’accès interne

Nous vous recommandons d’utiliser la découverte automatique au lieu de la découverte manuelle. Toutefois, les paramètres manuels peuvent être utiles pour résoudre les problèmes de connectivité des appareils mobiles.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configuration de DNS Split-Brain avec Lync Server

Le DNS split-brain est connu sous la dénomination d’un certain nombre de noms, par exemple, Split DNS ou Split-horizon DNS. En fait, il décrit une configuration DNS dans laquelle il existe deux zones DNS avec le même espace de noms, mais une seule requête de services de zone DNS en interne uniquement et les autres requêtes externes aux services de zone DNS. Toutefois, de nombreux enregistrements DNS (SRV et A) contenus dans le DNS interne ne seront pas contenus dans le DNS externe, et inversement. Dans les cas où le même enregistrement DNS existe à la fois dans le DNS interne et dans le DNS externe (par exemple, www.contoso.com), l’adresse IP renvoyée sera différente selon l’emplacement (interne ou externe) de la requête.

<div>


> [!IMPORTANT]  
> Actuellement, Split-Brain DNS n’est pas pris en charge pour la mobilité, ou plus spécifiquement, les enregistrements DNS LyncDiscover et LyncDiscoverInternal. LyncDiscover doit être défini sur un serveur DNS externe et LyncDiscoverInternal doit être défini sur un serveur DNS interne.



</div>

Pour les besoins de ces rubriques, le terme DNS split-brain est utilisé.

Si vous configurez DNS split-brain, les zones interne et externe suivantes contiennent un résumé des types d’enregistrements DNS requis dans chaque zone. Pour plus d’informations, reportez-vous à [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interne :**

  - contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone interne contoso.com contient :
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 interne (facultatif)
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAMe pour la découverte automatique des services Web Lync Server 2013 (facultatif)
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour le nom du pool frontal, le nom du pool directeur ou du pool Directeur, ainsi que tous les serveurs internes exécutant Lync Server 2013 dans le réseau d’entreprise
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne du serveur Edge de chaque Lync Server 2013, serveur Edge dans le réseau de périmètre
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans le réseau de périmètre (facultatif pour la gestion des proxys inverses)
    
      - Toutes les interfaces Edge internes du serveur Edge Lync Server 2013 dans le réseau de périmètre utilisent la zone DNS interne pour résoudre les requêtes vers contoso.com
    
      - Tous les serveurs exécutant Lync Server 2013 et les clients exécutant Lync 2013 dans le réseau d’entreprise pointent vers les serveurs DNS internes pour résoudre les requêtes vers contoso.com ou utiliser le fichier HOSTs sur chaque serveur Edge et les enregistrements de liste A et AAAA (si vous utilisez l’adressage IPv6) pour le serveur du tronçon suivant, en particulier le directeur ou l’adresse VIP du pool frontal ou un serveur Standard Edition Server

**DNS externe :**

  - contient une zone DNS appelée contoso.com pour laquelle il fait autorité

  - La zone externe contoso.com contient :
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 (facultatif)
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAMe pour la découverte automatique des services Web Lync Server 2013 pour une utilisation avec la mobilité
    
      - Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour l’interface externe de serveur Edge de chaque Lync Server 2013, serveur Edge ou adresse IP virtuelle du programme d’équilibrage de la charge matérielle dans le réseau de périmètre
    
      - Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface externe du serveur proxy inverse ou de l’adresse IP virtuelle pour un pool de serveurs proxy inverses dans le réseau de périmètre

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuration automatique sans DNS split-brain

À l’aide du DNS split-brain, un utilisateur de Lync Server 2013 qui se connecte en interne peut tirer parti de la configuration automatique si la zone DNS interne contient un \_ sipinternaltls. \_ enregistrement TCP SRV pour chaque domaine SIP utilisé. Toutefois, si vous n’utilisez pas le DNS split-brain, la configuration interne automatique des clients exécutant Lync ne fonctionnera pas, sauf si l’une des solutions de contournement décrites plus loin dans cette section est implémentée. En effet, Lync Server 2013 nécessite l’URI SIP de l’utilisateur pour correspondre au domaine du pool frontal désigné pour la configuration automatique. Cela était également le cas avec les versions antérieures de Communicator.

Si par exemple vous avez deux domaines SIP utilisés, les enregistrements DNS SRV suivants seront nécessaires :

  - Si un utilisateur se connecte en tant que bob@contoso.com l’enregistrement SRV suivant fonctionnera pour la configuration automatique, car le domaine SIP de l’utilisateur (contoso.com) correspond au domaine du pool frontal de configuration automatique) :
    
     \_sipinternaltls. \_ tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un utilisateur se connecte en tant que alice@fabrikam.com, l’enregistrement DNS SRV suivant fonctionnera pour la configuration automatique du deuxième domaine SIP.
    
     \_sipinternaltls. \_ tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

À titre de comparaison, si un utilisateur se connecte en tant que tim@litwareinc.com, l’enregistrement DNS SRV suivant ne fonctionne pas pour la configuration automatique, car le domaine SIP du client (litwareinc.com) ne correspond pas au domaine dans lequel se trouve le pool (fabrikam.com) :

 \_sipinternaltls. \_ tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si la configuration automatique est requise pour les clients exécutant Lync, sélectionnez l’une des options suivantes :

  - Objets de stratégie de **groupe**     Utiliser des objets de stratégie de groupe (GPO) pour remplir les valeurs de serveur correctes.
    
    <div>
    

    > [!NOTE]  
    > Cette option n’active pas la configuration automatique, mais automatise le processus de configuration manuelle. Par conséquent, en suivant cette approche, les enregistrements SRV associés à la configuration automatique ne sont pas nécessaires.

    
    </div>

  - **Zone**     interne correspondante Créez une zone dans le DNS interne correspondant à la zone DNS externe (par exemple, contoso.com) et créez des enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) correspondant au pool Lync Server 2013 utilisé pour la configuration automatique. Par exemple, si un utilisateur est hébergé sur pool01.contoso.net, mais qu’il se connecte à Lync en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com et à l’intérieur de celle-ci, créez un enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour pool01.contoso.com.

  - Zone interne de **point de code**     Si vous créez une zone entière dans le DNS interne n’est pas une option, vous pouvez créer des zones de code confidentiel (c’est-à-dire des zones dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique, et renseignez ces zones à l’aide de dnscmd.exe. Dnscmd.exe est obligatoire car l’interface utilisateur DNS ne prend pas en charge la création de zones repère. Par exemple, si le domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 contenant deux serveurs frontaux, vous avez besoin des zones repère en enregistrements A suivants dans votre DNS interne :
    
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

<div>


> [!NOTE]  
> Le nom de domaine complet du pool frontal apparaît deux fois, mais avec deux adresses IP différentes. Cela est dû à l’utilisation de l’équilibrage de la charge DNS, mais si l’équilibrage de la charge matérielle était utilisé, il n’y aurait qu’une seule entrée de pool frontal. De même, les valeurs du nom de domaine complet du pool frontal entre l’exemple contoso.com et l’exemple fabrikam.com changent, mais les adresses IP sont conservées. La raison est que les utilisateurs qui se connectent à partir de l’un de ces domaines IP utilisent le même pool frontal pour la configuration automatique.



</div>

Pour plus d’informations, reportez-vous à l’article du blog DMTF « configuration automatique de Communicator et Split-Brain DNS » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .

<div>


> [!NOTE]  
> Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configuration du DNS (Domain Name System) pour la récupération d’urgence

Pour configurer le DNS de façon à rediriger le trafic Web Lync Server 2013 vers vos sites de récupération d’urgence et de basculement, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS. Vous pouvez configurer vos enregistrements DNS pour que le Web prenne en charge la récupération d’urgence, de sorte que les fonctionnalités qui utilisent les services Web se poursuivent même si un pool frontal complet tombe en panne. Cette fonctionnalité de récupération d’urgence prend en charge la découverte automatique (URL Lyncdiscover), la réunion et les URL simples de numérotation.

Vous définissez et configurez des enregistrements hôtes DNS (A et AAAA en cas d’utilisation d’IPv6) supplémentaires pour la résolution interne et externe des services Web au niveau de votre fournisseur GeoDNS. Les détails suivants supposent que les pools couplés, géographiquement dispersés et GeoDNS pris en charge par votre fournisseur avec un DNS à tour de rôle ou configurés pour utiliser Pool1 comme principaux, basculent vers Pool2 en cas de perte de communication ou de défaillance matérielle.


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
<th>Enregistrements CNAMe (exemple)</th>
<th>Paramètres DNS (sélectionnez une option)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com vers Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com vers Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com vers Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com vers Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com vers Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com vers Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com vers Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com vers Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscoverinternal.contoso.com vers Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscoverinternal.contoso.com vers Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscover.contoso.com vers Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscover.contoso.com vers Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com vers Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com vers Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com vers Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com vers Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Tourniquet entre les pools</p>
<p>Utiliser le principal, se connecter au secondaire en cas d’échec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Équilibrage de charge DNS

L’équilibrage de la charge DNS est généralement implémenté au niveau de l’application. L’application (par exemple, un client exécutant Lync) tente de se connecter à un serveur dans un pool en se connectant à l’une des adresses IP renvoyées par la requête d’enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour le nom de domaine complet (FQDN) du pool.

Si par exemple il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, voilà ce qui se produit :

  - Clients exécutant une requête DNS Lync pour pool01.contoso.com. La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre) :
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Le client tente d’établir une connexion TCP (Transmission Control Protocol) à l’une des adresses IP. En cas d’échec, le client essaie l’adresse IP suivante dans le cache.

  - Si la connexion TCP réussit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool01.contoso.com.

  - Si le client essaie toutes les entrées mises en cache sans connexion, l’utilisateur est informé qu’aucun serveur exécutant Lync Server 2013 n’est disponible pour le moment.

<div>


> [!NOTE]  
> L’équilibrage de la charge DNS est différent du tourniquet (round robin) DNS (DNS RR) qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour fournir un ordre d’adresses IP différent correspondant aux serveurs d’un pool. DNS RR active en général uniquement la distribution de la charge, mais n’active pas le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue. Par conséquent, le tourniquet DNS (round robin) seul est moins fiable que l’équilibrage de la charge DNS. Vous pouvez utiliser le tourniquet DNS (round robin) conjointement avec l’équilibrage de la charge DNS.



</div>

L’équilibrage de la charge DNS est utilisé dans les cas suivants :

  - Équilibrage de la charge du SIP de serveur à serveur vers les serveurs Edge

  - Équilibrage de la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel.

  - Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)

  - Équilibrage de la charge de l’ensemble du trafic client-serveur entre les clients et les serveurs Edge

L’équilibrage de la charge DNS ne peut pas être utilisé dans les cas suivants :

  - Trafic Web client à serveur vers le directeur ou les serveurs frontaux

Équilibrage de la charge DNS et trafic fédéré :

Si plusieurs enregistrements DNS sont renvoyés par une requête SRV DNS, le service Edge d’accès sélectionne toujours l’enregistrement DNS SRV avec la priorité numérique la plus basse et la pondération numérique la plus élevée. Le document IETF (Internet Engineering Task Force) « un RR DNS pour la spécification de l’emplacement des services (DNS SRV) » <http://www.ietf.org/rfc/rfc2782.txt> indique que s’il existe plusieurs enregistrements SRV DNS définis, Priority est utilisé pour la première fois, puis Weight. Par exemple, l’enregistrement DNS SRV a a un poids de 20 et une priorité de 40 et un enregistrement DNS SRV B dont le poids est de 10 et la priorité 50. L’enregistrement DNS SRV A avec la priorité 40 est sélectionné. Les règles suivantes s’appliquent à la sélection des enregistrements SRV DNS :

  - La priorité est prise en compte en premier. Un client doit essayer de contacter l’hôte cible défini par l’enregistrement DNS SRV avec la priorité la plus faible qu’il peut atteindre. Les cibles ayant la même priorité doivent être testées dans un ordre défini par le champ Weight.

  - Le champ poids spécifie un poids relatif pour les entrées présentant la même priorité. Les poids plus élevés doivent se voir attribuer une probabilité proportionnellement plus élevée de sélection. Les administrateurs DNS doivent utiliser le poids 0 lorsqu’il n’y a aucune sélection de serveur à effectuer. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements dont le poids est supérieur à 0 doivent avoir une chance très faible d’être sélectionnés.

Si plusieurs enregistrements SRV DNS avec une priorité et un poids égaux sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV qui a été reçu en premier à partir du serveur DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

