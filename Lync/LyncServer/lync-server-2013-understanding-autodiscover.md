---
title: Présentation de la découverte automatique
TOCTitle: Présentation de la découverte automatique
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945654(v=OCS.15)
ms:contentKeyID: 53095538
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de la découverte automatique

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le service de découverte automatique de Lync Server 2013 est une fonctionnalité initialement introduite dans Microsoft Lync Server 2010 dans le cadre de la Mise à jour cumulative pour Lync Server 2010 de novembre 2011. Outre des correctifs, cette mise à jour cumulative offre la prise en charge des clients Lync Mobile et Lync 2013.

Dans Lync Server 2013, le service de découverte automatique fait partie intégrante du fonctionnement des clients mobiles internes et externes et il est également étendu aux nouveaux clients, tels que la nouvelle application Lync du Windows Store pour Windows 8. La découverte automatique est également utilisée par les clients de bureau Lync 2013. Elle est reconnue dans Lync Server par les enregistrements DNS (Domain Name System) requis **lyncdiscover.\<domaine\>** et **lyncdiscoverinternal.\<domaine\>**. Par ailleurs, les nouvelles versions du client de bureau Lync 2010 et Lync 2013 privilégient la découverte automatique plutôt que les enregistrements SRV DNS et ne font appels à ces derniers que si lyncdiscover.\<domaine\> ou lyncdiscoverinternal.\<domaine\> ne répond pas ou ne peut pas résoudre les adresses. L’application Lync du Windows Store pour Windows 8 et Lync Mobile utilise exclusivement la découverte automatique et ne fait pas référence aux enregistrements SRV DNS traditionnels.

Dans Lync Server 2013, la découverte automatique est étendue afin de communiquer au client les éléments, fonctionnalités et méthodes de communication qui lui sont accessibles. Ces informations sont communiquées par le biais d’une demande envoyée à partir du client et les services web de Lync Server répondent de manière clairement définie quels sont les éléments accessibles au client et comment contacter ces fonctionnalités dans le format du document de réponse de découverte automatique.

Le meilleur moyen de comprendre le document de réponse de découverte automatique, y compris la façon dont les services web indiquent les fonctionnalités accessibles aux clients par le biais de ce document, consiste à disséquer et définir chaque ligne d’une réponse par défaut dans le document de réponse de découverte automatique envoyé par le service web Lync.

> [!NOTE]  
> Dans les détails qui suivent, l’utilisateur a déjà été authentifié auprès du serveur central en répondant à une demande d’authentification.

> [!NOTE]  
> Le service web de découverte automatique de Lync est défini dans les <strong>Protocoles Microsoft Office</strong> dans la section <strong>Spécifications ouvertes</strong> de la bibliothèque <strong>Microsoft Developer Network</strong> (MSDN). Pour plus d’informations, voir le document de spécification complet intitulé « Lync Autodiscover Web Service Protocol » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=273839" class="uri">http://go.microsoft.com/fwlink/?linkid=273839</a>. Pour plus d’informations sur l’authentification, voir « Protocole du service web d’authentification OC » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=279015" class="uri">http://go.microsoft.com/fwlink/?linkid=279015</a>.

## La réponse de découverte automatique du service web du serveur Lync

La réponse renvoyée lorsque la demande de découverte automatique est envoyée est identique pour un client interne ou externe. Certains paramètres dépendant de l’emplacement peuvent changer. Si une demande du client est reçue mais que le pool réel est un pool autre que celui ayant été contacté, le pool d’accueil de l’utilisateur est défini pour cet utilisateur. Un collègue dont le compte d’utilisateur se trouve sur un autre pool mais qui se connecte depuis le même bureau obtiendrait une réponse légèrement différente. La réponse indique le serveur frontal ou pool de serveurs frontaux correct pour l’utilisateur en question.

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

## Détails du document de réponse de découverte automatique

Le document de réponse de découverte automatique peut être soit au format JSON (JavaScript Object Notation) (format par défaut), soit au format XML (Extensible Markup Language). Le format XML est utilisé pour cet exemple. La demande et la réponse sont prévisibles car le document a un schéma défini qui détermine le format. La ligne dans le document qui décrit le schéma employé est la première ligne de la demande ou de la réponse :

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La définition de **AccessLocation=”External”** indique que la demande provient d’un utilisateur externe.

```
<SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
```
```
<SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
```

SipServerInternalAccess et SipServerExternalAccess ne sont pas utilisées actuellement. Ces entrées sont réservées à un usage ultérieur.

```
<SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
```
```
<SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
```

SipClientInternalAccess et SipClientExternalAccess décrivent le nom de domaine complet et le port qu’utilisera un client interne ou externe pour accéder au serveur SIP défini. Le client de bureau Lync et l’application Lync du Windows Store utilisent ces entrées en fonction de leur emplacement (interne ou externe) pour trouver le directeur ou le serveur frontal.

```
<Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
```
```
<Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
```

Les références `Autodiscover` contiennent les points d’entrée du service de découverte automatique. L’attribut de jeton contient le nom du service et href est une URL qui définit pour le client où se trouve le service. Les clients d’un réseau externe utilisent `External/Autodiscover`. Le service de découverte automatique est installé dans le cadre du processus de déploiement. `Internal/Autodiscover` n’est pas utilisé actuellement et est réservé pour un usage ultérieur.

```
<Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
```
```
<Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
```

Les références `AuthBroker` contiennent les points d’entrée du service Broker d’authentification interne et externe, dans notre exemple sip.svc. L’attribut de jeton contient le nom du service et href est une URL qui définit pour le client où se trouve le service. Les clients du réseau interne utilisent `Internal/AuthBroker`. Les clients d’un réseau externe utilisent `External/AuthBroker`. Le service AuthBroker est installé dans le cadre du processus de déploiement de vos services web Lync Server 2013 internes.

```
<Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
```
```
<Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
```

Le jeton `WebScheduler` fait référence aux URL pour l’accès des clients à la planification basée sur le web pour les conférences Lync Server. Actuellement, seul `External/WebScheduler` est utilisé. Le service WebScheduler est installé dans le cadre du processus de déploiement de vos services web Lync Server 2013 internes.

```
<Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
```
```
<Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
```

`Internal/Mcx` et `External/Mcx` sont les emplacements des services de mobilité, introduits dans la Mise à jour cumulative pour Lync Server 2010 de novembre 2011. Ces références continueront à être utilisées par Lync 2010 Mobile sur tous les périphériques pris en charge. Le service Mcx est installé dans le cadre du processus de déploiement de vos services web Lync Server 2013 internes.

```
<Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
```
```
<Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
```
```
<Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
```

**Internal/Ucwa**, **External/Ucwa** et **Ucwa** permettent aux clients d’accéder à l’interface de programmation d’applications web de communications unifiées (API UCWA, ou simplement UCWA). Les répertoires virtuels `Internal/Ucwa` et `External/Ucwa` sont des points d’accès inutilisés actuellement car réservés pour une amélioration ultérieure de la fonctionnalité. Le répertoire virtuel `Ucwa` est utilisé pour Microsoft Lync Mobile (introduit dans Lync Server 2013) sur tous les périphériques pris en charge. Le service UCWA est installé dans le cadre du processus de déploiement de vos services web Lync Server 2013 internes.

```
<Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
```
```
<Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
```
```
<Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
```

`Internal/XFrame`, **External/XFrame** et **XFrame** fournissent l’accès pour les applications de serveur basées sur UCWA. XFrame est installé dans le cadre du processus de déploiement de vos services web Lync Server 2013 internes.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Le jeton `Self` fait référence à des informations spécifiques au client (type de réponse utilisateur) qui effectue la demande. Le client ayant effectué cette demande était externe et cette référence de découverte automatique renvoie à la partie utilisateur du service de découverte automatique.

## Voir aussi

#### Autres ressources

[Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planification de la découverte automatique](lync-server-2013-planning-for-autodiscover.md)

