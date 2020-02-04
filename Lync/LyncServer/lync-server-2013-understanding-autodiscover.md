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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Comprendre la découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-03_

Le service de découverte automatique de Lync Server 2013 est une fonctionnalité introduite dans Microsoft Lync Server 2010 dans le cadre de la mise à jour cumulative pour Lync Server 2010:2011. Outre les correctifs, cette mise à jour cumulative a fourni une prise en charge pour les clients Lync mobile et Lync 2013.

Dans Lync Server 2013, le service de découverte automatique fait partie intégrante de l’utilisation des clients mobiles internes et externes, et la découverte automatique est également étendue aux nouveaux clients, tels que la dernière présentation de l’application Lync du Windows Store pour Windows 8. La découverte automatique est également utilisée par le client de bureau 2013 Lync. La découverte automatique est reconnue dans Lync Server par le système de noms de domaine (DNS) requis **lyncdiscover.\< Domain\> ** et **lyncdiscoverinternal.\< Domain\>(domaine**). De plus, les versions plus récentes de Lync 2010 et du client de bureau 2013 de Lync préfèrent la découverte automatique par le biais des enregistrements SRV DNS (Domain Name System), à l’aide des enregistrements SRV DNS uniquement si lyncdiscover. \<Domain\> ou lyncdiscoverinternal. \<le\> domaine ne répond pas ou n’est pas résolu. L’application Lync du Windows Store pour Windows 8 et Lync mobile utilise uniquement la découverte automatique et ne fait pas référence aux enregistrements DNS SRV traditionnels.

Dans Lync Server 2013, la découverte automatique est développée pour communiquer au client les éléments, fonctionnalités et méthodes de communication disponibles pour le client. Les informations sont communiquées par le biais d’une requête envoyée par le client, et les services Web de Lync Server répondent par une réponse clairement définie indiquant le nom du client et le mode de contact de ces fonctionnalités dans le format de la découverte automatique. Document de réponse.

La meilleure façon de comprendre le document de réponse de découverte automatique, y compris la façon dont les services Web communiquent les fonctionnalités aux clients par le biais de ce document, consiste à dissect et à définir chaque ligne dans une réponse standard du document de réponse de découverte automatique du service Web Lync.

<div class="">


> [!NOTE]  
> Dans les détails qui suivent, l’utilisateur est déjà authentifié sur le serveur principal en réponse à une demande d’authentification.



</div>

<div class="">


> [!NOTE]  
> Le service Web de découverte automatique Lync est défini dans les <STRONG>protocoles Microsoft Office</STRONG> dans la section <STRONG>spécifications ouvertes</STRONG> de la bibliothèque <STRONG>Microsoft Developer Network</STRONG> (MSDN). Pour plus d’informations, reportez-vous au document de spécification complet « protocole de service Web <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>de découverte automatique » dans :. Pour plus d’informations sur l’authentification, voir « protocole de service Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>d’authentification OC » à l’adresse.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>La réponse de découverte automatique du service Web de Lync Server

La réponse renvoyée lors de l’envoi de la demande de découverte automatique est identique pour un client interne ou externe. Certains paramètres qui sont compatibles avec la localisation peuvent changer. Si une requête client est reçue alors que le pool réel est différent de celui qui a été contacté, le groupe de ressources de famille de l’utilisateur est défini pour cet utilisateur. Un collègue dont le compte utilisateur se trouve sur un autre groupe, mais qui se connecte à partir du même bureau, obtiendrait une réponse légèrement différente. La réponse indique le serveur frontal ou le pool frontal approprié pour cet utilisateur.

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

## <a name="autodiscover-response-document-details"></a>Détails du document de réponse automatique

Le document de réponse de découverte automatique peut être dans l’un des deux formats proposés. Le format par défaut est JSON (JavaScript Object Notation). Le format autre est le document XML (Extensible Markup Language). Le code XML est utilisé pour cet exemple. La requête et la réponse sont prévisibles, car le document est doté d’un schéma défini qui détermine le format. La ligne du document qui décrit le schéma utilisé est la première ligne de la requête ou de la réponse :

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La définition de **AccessLocation = "External"** indique que la requête a été effectuée à partir d’un utilisateur externe.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Les SipServerInternalAccess et SipServerExternalAccess ne sont pas utilisés actuellement. Ces entrées sont réservées pour une utilisation ultérieure.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess et SipClientExternalAccess décrivent le nom de domaine et le port complets qu’un client interne ou externe utilisera pour accéder au serveur SIP défini. Le client de bureau Lync et l’application Lync du Windows Store utilisent ces entrées en fonction de leur emplacement (interne ou externe) pour trouver le directeur ou le serveur principal.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Les `Autodiscover` références contiennent les points d’entrée de service pour le service de découverte automatique. L’attribut Token contient le nom du service, et la clé href est une URL qui définit pour le client où le service est disponible. Les clients sur un réseau externe utilisent `External/Autodiscover`le. Le service de découverte automatique est installé dans le cadre du processus de déploiement. `Internal/Autodiscover`n’est pas utilisé et est réservé pour une utilisation ultérieure.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Les `AuthBroker` références contiennent les points d’entrée de service pour le service de Broker d’identification interne et externe (par exemple, SIP. svc). L’attribut Token contient le nom du service, et la clé href est une URL qui définit pour le client où le service est disponible. Clients du réseau interne à utiliser `Internal/AuthBroker`. Les clients sur un réseau externe utilisent `External/AuthBroker`le. Le service AuthBroker est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Le `WebScheduler` jeton fait référence aux URL relatives à l’accès client aux conférences sur le Web pour les conférences Lync Server. Pour l’instant, `External/WebScheduler` seul le est utilisé. Le WebScheduler est installé dans le cadre de la procédure de déploiement de vos services Web de déploiement de Lync Server 2013 internes.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`et `External/Mcx` sont les emplacements des services de mobilité, introduits dans une mise à jour cumulative pour Lync Server 2010 : novembre 2011. Ces références seront toujours utilisées par Lync 2010 mobile sur tous les appareils pris en charge. Le service MCX est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **External/Ucwa** et **Ucwa** permettent aux clients d’accéder à l’interface de programmation d’application Web Unified Communications (API Ucwa, ou simplement Ucwa). `Internal/Ucwa`les `External/Ucwa` répertoires virtuels sont des points d’accès réservés pour une future amélioration des fonctionnalités, et ne sont pas utilisés. Le `Ucwa` répertoire virtuel est utilisé pour Microsoft Lync mobile (introduit avec Lync Server 2013) sur tous les appareils pris en charge. Le service UCWA est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **Externe/Xframe** et **Xframe** offrent un accès aux applications serveur UCWA. XFrame est installé dans le cadre du processus de déploiement de vos services Web de déploiement de Lync Server 2013 internes.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Le `Self` jeton fait référence à des informations spécifiques au client (type de réponse de l’utilisateur) qui effectue la requête. Le client qui a effectué cette demande était externe, et cette référence de découverte automatique correspond à la partie utilisateur du service de découverte automatique.

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

