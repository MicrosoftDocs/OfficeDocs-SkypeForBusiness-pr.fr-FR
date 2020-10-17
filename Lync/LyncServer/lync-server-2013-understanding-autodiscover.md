---
title: 'Lync Server 2013 : présentation de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527761"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a>Présentation de la découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-03_

Le service de découverte automatique Lync Server 2013 est une fonctionnalité qui a été initialement introduite dans Microsoft Lync Server 2010 dans le cadre de la mise à jour cumulative de Lync Server 2010:2011. Outre les correctifs, cette mise à jour cumulative a fourni une prise en charge pour les clients Lync mobile et Lync 2013.

Dans Lync Server 2013, le service de découverte automatique fait partie intégrante des clients mobiles externes et internes, et la découverte automatique est également étendue aux nouveaux clients, tels que l’application Lync Windows Store récemment introduite pour Windows 8. La découverte automatique est également utilisée par les clients de bureau Lync 2013. La découverte automatique est reconnue dans Lync Server par les enregistrements DNS (Domain Name System) requis **lyncdiscover \<domain\> .** et **lyncdiscoverinternal. \<domain\> **. En outre, les versions plus récentes du client de bureau Lync 2010 et Lync 2013 préfèrent la découverte automatique sur les enregistrements SRV DNS (Domain Name System), à l’aide des enregistrements SRV DNS uniquement si lyncdiscover.\<domain\> ou lyncdiscoverinternal.\<domain\> ne répond pas ou ne se résout pas. L’application Lync Windows Store pour Windows 8 et Lync mobile utilise exclusivement la découverte automatique et ne fait pas référence aux enregistrements DNS SRV traditionnels.

Dans Lync Server 2013, la découverte automatique est étendue pour communiquer au client les éléments, les fonctionnalités et les méthodes de communication disponibles pour le client. Les informations sont communiquées par le biais d’une demande envoyée à partir du client et les services Web Lync Server répondent par une réponse clairement définie indiquant les éléments disponibles pour le client, ainsi que la façon de contacter ces fonctionnalités dans le format du document de réponse de découverte automatique.

La meilleure façon de comprendre le document de réponse de découverte automatique, y compris la façon dont les services Web communiquent les fonctionnalités aux clients par le biais de ce document, consiste à dissect et à définir chaque ligne dans une réponse classique du document de réponse de découverte automatique de Lync Web service.

<div class="">


> [!NOTE]  
> Dans les détails suivants, l’utilisateur s’est déjà authentifié auprès du serveur associé en répondant à une demande d’authentification.



</div>

<div class="">


> [!NOTE]  
> Le service Web de découverte automatique Lync est défini dans les <STRONG>protocoles Microsoft Office</STRONG> dans la section <STRONG>spécifications ouvertes</STRONG> de la bibliothèque MSDN ( <STRONG>Microsoft Developer Network</STRONG> ). Pour plus d’informations, reportez-vous au document de spécification complet, « Lync Autodiscover Web service Protocol », à l’adresse suivante : <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> . Pour plus d’informations sur l’authentification, voir « OC Authentication Web service Protocol » à l’adresse <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Réponse de découverte automatique de service Web Lync Server

La réponse renvoyée lors de l’envoi de la demande de découverte automatique est la même pour un client interne ou externe. Certains paramètres qui sont compatibles avec l’emplacement peuvent changer. Si une demande client est reçue, mais que le pool réel est différent de celui qui a été contacté, le pool d’accueil de l’utilisateur est défini pour cet utilisateur. Un collègue dont le compte d’utilisateur se trouve sur un pool différent, mais qui se connecte à partir du même bureau, obtient une réponse légèrement différente. La réponse indique le serveur frontal ou le pool frontal correct pour cet utilisateur.

Exemple de document de réponse de découverte automatique :

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>Informations sur le document de réponse de découverte automatique

Le document de réponse de découverte automatique peut être dans l’un des deux formats. Le format par défaut est JavaScript Object Notation (JSON). L’autre format est le document XML (Extensible Markup Language). Le code XML est utilisé pour cet exemple. La demande et la réponse sont prévisibles, car le document possède un schéma défini qui détermine le format. La ligne dans le document qui décrit le schéma utilisé est la première ligne de la demande ou de la réponse :

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La définition de **AccessLocation = « External »** indique que la demande a été effectuée à partir d’un utilisateur externe.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess et SipServerExternalAccess ne sont actuellement pas utilisés. Ces entrées sont réservées pour une utilisation ultérieure.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess et SipClientExternalAccess décrivent le nom de domaine complet et le port qu’un client interne ou externe utilisera pour accéder au serveur SIP défini. Le client de bureau Lync et l’application Lync du Windows Store utilisent ces entrées en fonction de leur emplacement (interne ou externe) pour rechercher le directeur ou le serveur frontal.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Les `Autodiscover` références contiennent les points d’entrée de service pour le service de découverte automatique. L’attribut Token contient le nom du service et le href est une URL qui définit le client où se trouve le service. Les clients sur un réseau externe utilisent le `External/Autodiscover` . Le service de découverte automatique est installé dans le cadre du processus de déploiement. `Internal/Autodiscover` n’est pas utilisé actuellement et est réservé à une utilisation ultérieure.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Les `AuthBroker` références contiennent les points d’entrée de service pour le service de Broker d’authentification interne et externe, dans ce cas, SIP. svc. L’attribut Token contient le nom du service et le href est une URL qui définit le client où se trouve le service. Clients sur le réseau interne avec utilisation `Internal/AuthBroker` . Les clients sur un réseau externe utilisent le `External/AuthBroker` . Le service AuthBroker est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Le `WebScheduler` jeton fait référence aux URL pour l’accès client à la planification Web pour les conférences Lync Server. Actuellement, seul le `External/WebScheduler` est utilisé. Le WebScheduler est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` et `External/Mcx` sont les emplacements des services de mobilité, introduits dans la mise à jour cumulative de Lync Server 2010 : novembre 2011. Ces références continueront à être utilisées par Lync 2010 mobile sur tous les appareils pris en charge. Le service MCX est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **External/Ucwa** et **Ucwa** permettent aux clients d’accéder à l’interface de programmation d’applications Web Unified Communications (Ucwa API, ou simplement Ucwa). `Internal/Ucwa` et les `External/Ucwa` répertoires virtuels sont des points d’accès réservés pour l’amélioration des fonctionnalités futures et ne sont pas utilisés. Le `Ucwa` répertoire virtuel est utilisé pour Microsoft Lync mobile (introduit avec Lync Server 2013) sur tous les appareils pris en charge. Le service UCWA est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** et **Xframe** fournissent l’accès aux applications serveur basées sur UCWA. XFrame est installé dans le cadre du processus de déploiement de vos services Web de déploiement interne de Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Le `Self` jeton fait référence à des informations spécifiques au client (type de réponse de l’utilisateur) qui effectue la demande. Le client qui a effectué cette demande était externe et cette référence de découverte automatique concerne la partie utilisateur du service de découverte automatique.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planification de la découverte automatique dans Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

