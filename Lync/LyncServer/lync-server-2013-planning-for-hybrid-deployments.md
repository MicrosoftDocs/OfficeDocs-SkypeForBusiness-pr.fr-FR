---
title: 'Lync Server 2013 : planification des déploiements hybrides'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planification des déploiements hybrides de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-05-25_

Prenez en compte les exigences suivantes pour les utilisateurs et votre infrastructure réseau lors de la planification d’un déploiement hybride.

<div>

## <a name="infrastructure-requirements"></a>Exigences d’infrastructure

Pour pouvoir implémenter et déployer un déploiement hybride, vous devez disposer des éléments suivants configurés dans votre environnement.

  - Un client Microsoft Office 365 doté de Skype entreprise online. Notez que vous pouvez uniquement utiliser un seul client pour une configuration hybride avec votre déploiement local.

  - Un déploiement local unique (infrastructure) de Skype entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Voir la configuration requise pour la topologie.
    
    Pour plus d’informations sur la configuration de votre déploiement Lync Server 2013 ou Lync Server 2010 pour une application hybride, voir [configuration de déploiements hybrides Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).

  - Outils d’administration de Skype entreprise Server 2015. Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration de Lync Server 2013.

  - Pour prendre en charge l’authentification unique avec Office 365 de façon à ce que les utilisateurs puissent utiliser les mêmes informations d’identification pour se connecter à Office en local, vous pouvez utiliser les fonctionnalités de synchronisation de mot de passe d’Azure Active Directory (AAD) Connect. Vous pouvez également utiliser AD FS (Active Directory Federation Services) avec l’authentification unique pour Office 365.
    
    Pour plus d’informations, consultez [intégration de vos identités locales avec Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Une solution unique de synchronisation d’annuaires pour assurer la synchronisation de vos objets Active Directory locaux et en ligne. Pour plus d’informations sur la synchronisation d’annuaires, voir [Outils d’intégration d’annuaire](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Prise en charge du client Lync

Il existe certaines différences entre les fonctionnalités prises en charge dans les clients Lync, ainsi que les fonctionnalités disponibles dans les environnements locaux et en ligne. Avant de décider de l’endroit où vous souhaitez accéder aux utilisateurs de votre organisation, vous pouvez afficher la prise en charge du client pour les différentes configurations de Lync Server. Les clients suivants sont pris en charge dans Skype entreprise Online dans un déploiement hybride Lync :

  - Lync 2010

  - Lync 2013

  - application Lync du Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync pour Mac 2011

  - Lync Room System

  - Lync Basic 2013

Pour plus d’informations sur la prise en charge des clients, voir les rubriques suivantes :

  - [Clients pour Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tableau de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tableau de comparaison des clients mobiles pour Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Pour configurer votre déploiement pour une connexion hybride avec Skype entreprise Online, vous devez disposer de l’une des topologies prises en charge suivantes :

  - Un déploiement 2015 de Skype entreprise Server avec tous les serveurs exécutant Skype entreprise Server 2015.

  - Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.

  - Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les mises à jour les plus récentes.
    
      - Le serveur de périphérie de Fédération et le serveur de tronçon suivant du serveur Edge de Fédération doivent exécuter Lync Server 2010 avec les mises à jour cumulatives les plus récentes.
    
      - Les outils d’administration de Skype entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de travail de gestion.

  - Un déploiement Lync Server 2013 et Skype entreprise Server 2015 mixte avec les rôles serveur suivants dans au moins un site exécutant Skype entreprise Server 2015 :
    
      - Au moins un pool d'entreprise ou serveur Standard Edition 
    
      - Pool directeur associé à la fédération SIP, le cas échéant
    
      - Pool Edge associé à la fédération SIP

  - Un déploiement Lync Server 2010 et Skype entreprise Server 2015 mixte avec les rôles de serveurs suivants dans au moins un site exécutant Skype entreprise Server 2015 :
    
      - Au moins un pool d'entreprise ou serveur Standard Edition 
    
      - Pool directeur associé à la fédération SIP, le cas échéant
    
      - Pool Edge associé à la fédération SIP pour le site

  - Un déploiement Lync Server 2010 et Lync Server 2013 mixte avec les rôles serveur suivants dans au moins un site exécutant Lync Server 2013 :
    
      - Au moins un pool d'entreprise ou serveur Standard Edition dans le site
    
      - Pool directeur associé à la fédération SIP, si elle existe dans le site
    
      - Pool Edge associé à la fédération SIP pour le site

<div>


> [!IMPORTANT]  
> Tout le fonctionnement de la gestion des utilisateurs, y compris les utilisateurs locaux et UNRESOLVED_TOKEN_VAL (skypeforbusiness) en ligne, doit être réalisé à l’aide de la version installée la plus récente des outils d’administration. Les outils d’administration doivent être installés sur un serveur distinct qui dispose d’un accès de connexion au déploiement local existant et à Internet. L’applet de connexion <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-Csuser</A> pour déplacer des utilisateurs de votre déploiement local vers UNRESOLVED_TOKEN_VAL (skype16_online) doit être exécutée à partir des outils d’administration connectés à votre déploiement local.



</div>

Pour plus d’informations sur les topologies prises en charge, voir [topologies prises en charge dans Lync server 2013](lync-server-2013-supported-topologies.md)et [topologies de référence de Lync Server 2013 pour les déploiements hybrides d’entreprise](http://go.microsoft.com/fwlink/p/?linkid=398709).

Pour plus d’informations sur les déploiements hybrides et la connexion de PowerShell à Lync Online, voir [Lync Online : Lync PowerShell et résolution des problèmes hybrides](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Configuration requise pour les listes de Fédération autorisées/bloquées

La liste des domaines autorisés comprend les domaines pour lesquels un nom de domaine complet Edge partenaire est configuré (parfois appelé *serveur partenaire autorisé* ou *partenaire de fédération direct*). Vous devez connaitre la différence entre la fédération ouverte et la fédération fermée, appelée *découverte de partenaire* et *liste de domaines partenaires autorisés*, dans les déploiements locaux.

La configuration ci-dessous est requise pour configurer un déploiement hybride :

  - La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.

  - La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

  - La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

  - La Fédération doit être activée pour les communications externes pour le client en ligne, qui est configuré à l’aide du panneau de configuration Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Paramètres DNS

Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes Lync doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, voir [Configuration requise pour le système de noms de domaine (DNS) pour Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau ci-dessous fonctionne dans votre déploiement local :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Enregistrement DNS</p></td>
<td><p>Résolvable par</p></td>
<td><p>Enregistrement DNS requis</p></td>
</tr>
<tr class="even">
<td><p>Enregistrement SRV DNS pour _sipfederationtls. _tcp. &lt;sipdomain.com&gt; pour tous les domaines SIP pris en charge résolus vers les adresses IP externes d’Access Edge</p></td>
<td><p>Serveur(s) Edge</p></td>
<td><p>Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.</p></td>
</tr>
<tr class="odd">
<td><p>Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web</p></td>
<td><p>Ordinateurs des utilisateurs connectés au réseau d'entreprise interne</p></td>
<td><p>Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées. </p></td>
</tr>
</tbody>
</table>


En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne.

</div>

<div>

## <a name="firewall-considerations"></a>Considérations en matière de pare-feu

Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.

En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer les périphériques de pare-feu de votre réseau pour accepter les connexions basées sur les noms de \*domaine génériques (par exemple, tout le trafic de. Outlook.com). Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d'adresses IP que vous voulez autoriser et les ports.

Reportez-vous à la rubrique d’aide [URL et plages d’adresses IP Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Configuration requise pour les ports et les protocoles

En plus de la configuration requise pour les ports pour les communications internes de Lync Server 2013, vous devez également configurer les ports suivants.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/port</th>
<th>Applications</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Ouvrir entrant</p>
<ul>
<li><p>Services ADFS (Active Directory Federation Services)</p>
<p>Pour plus d’informations, voir <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Présentation des services de rôle AD FS</a>.</p></li>
<li><p>Services ADFS (Active Directory Federation Services) (rôle serveur proxy)</p></li>
<li><p>Portail Microsoft Online Services</p></li>
<li><p>Mon portail d’entreprise</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Client Lync (communications vers Lync Online à partir d’un serveur Lync local)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 et 443</p></td>
<td><p>Ouvrir entrant</p>
<ul>
<li><p>Outil de synchronisation d’annuaires de Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Ouvrir entrant/sortant sur le serveur de périphérie</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions de partage de données</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions audio, vidéo et de partage d’application</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions audio et vidéo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Ouvrir sortant pour les sessions audio et vidéo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Comptes et données utilisateur

Dans le cas d’un déploiement hybride Lync Server 2013, tous les utilisateurs que vous souhaitez utiliser dans Lync Online doivent d’abord être créés dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS). Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise Online, qui va déplacer la liste de contacts de l’utilisateur.

Lorsque vous synchronisez des comptes d’utilisateurs entre vos déploiements Lync local et Lync Online avec AD FS et DirSync, vous devez synchroniser les comptes d’annonces de tous les utilisateurs Lync de votre organisation entre votre déploiement local et Lync en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.

<div>


> [!IMPORTANT]  
> Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte d’utilisateur n’est pas synchronisé avec Active Directory local et l’utilisateur n’existe pas dans l’annuaire Active Directory local. Si vous avez déjà créé des utilisateurs dans Lync Online et que vous souhaitez configurer une connexion hybride avec un serveur Lync local, voir <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">déplacement des utilisateurs de Lync Online vers Lync local dans Lync server 2013</A>.



</div>

Lors de la planification d'un déploiement hybride, prenez en compte les aspects suivants liés aux utilisateurs.

  - **Le nombre**maximal de contacts pour les utilisateurs de Lync Online 250 est fixé aux utilisateurs    Au-delà de ce chiffre, les contacts seront supprimés de la liste des contacts de l'utilisateur.

  - **Messagerie instantanée et présence**   les listes de contacts, groupes et listes de contrôle d’accès des utilisateurs sont migrés avec le compte d’utilisateur.

  - **Les données de conférence, le contenu de la réunion et les réunions**   planifiées, ce contenu n’est pas migré avec le compte d’utilisateur. Les utilisateurs doivent replanifier les réunions une fois leur compte migré sur Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Fonctionnalités et stratégies utilisateur

  - Dans un environnement hybride Lync Server 2013, les utilisateurs peuvent être activés pour la messagerie instantanée, la voix et les réunions localement ou en ligne, mais pas les deux simultanément.

  - **Client Lync certains**     utilisateurs peuvent nécessiter une nouvelle version du client après leur déplacement vers Lync Online. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un pool Lync Server 2013 avant la migration vers Lync Online.
    
    Pour plus d’informations sur la prise en charge des clients, voir [clients pour Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) et [clients et configurations de port réseau prises en charge](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Les stratégies locales et la configuration (non-utilisateur)**   en ligne et en local nécessitent une configuration distincte. Vous ne pouvez pas définir des stratégies globales qui s'appliquent au deux.

</div>

</div>

<span> </span>

</div>

</div>

</div>

