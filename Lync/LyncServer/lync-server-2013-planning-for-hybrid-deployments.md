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
ms.openlocfilehash: 54888a96d33dc3d9195256483f41719031847744
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planification des déploiements hybrides Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-05-25_

Vous devez tenir compte des exigences suivantes pour les utilisateurs et l’infrastructure réseau lors de la planification d’un déploiement hybride.

<div>

## <a name="infrastructure-requirements"></a>Conditions requises pour l’infrastructure

Les éléments suivants doivent être configurés dans votre environnement afin d’implémenter et de déployer un déploiement hybride.

  - Une organisation Microsoft Office 365 avec Skype entreprise Online activé. Notez que vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.

  - Un seul déploiement local (infrastructure) de Skype entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Consultez la rubrique Configuration requise pour la topologie.
    
    Pour plus d’informations sur la configuration de votre déploiement Lync Server 2013 ou Lync Server 2010 en environnement hybride, consultez la rubrique [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).

  - Outils d’administration de Skype entreprise Server 2015. Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration Lync Server 2013.

  - Pour prendre en charge l’authentification unique avec Office 365 afin que les utilisateurs puissent utiliser les mêmes informations d’identification de connexion pour se connecter à Office comme ils le font sur site, vous pouvez utiliser les fonctionnalités de synchronisation de mot de passe d’Azure Active Directory (AAD) Connect. Vous pouvez également utiliser les services ADFS (Active Directory Federation Services) pour l’authentification unique avec Office 365.
    
    Pour plus d'informations, voir [Intégration de vos identités locales avec Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).

  - Une solution de synchronisation d’annuaire unique permettant de synchroniser vos objets Active Directory en local et en ligne. Pour plus d’informations sur la synchronisation d’annuaires, consultez la rubrique [Outils d’intégration d’annuaire](https://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Prise en charge des clients Lync

Il existe certaines différences entre les fonctionnalités prises en charge par les clients Lync, ainsi que les fonctionnalités disponibles dans les environnements locaux et en ligne. Avant de décider où vous voulez héberger les utilisateurs de votre organisation, vous pouvez afficher la prise en charge du client pour les différentes configurations de Lync Server. Les clients suivants sont pris en charge avec Skype entreprise Online dans un déploiement Lync hybride :

  - Lync 2010

  - Lync 2013

  - Application Lync du Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync pour Mac 2011

  - Lync Room System

  - Lync Basic 2013

Pour plus d’informations sur la prise en charge du client, consultez les rubriques suivantes :

  - [Clients pour Lync Online](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Tableaux de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tableaux de comparaison des clients mobiles pour Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Conditions requises pour la topologie

Pour configurer votre déploiement hybride avec Skype entreprise Online, vous devez disposer de l’une des topologies prises en charge suivantes :

  - Un déploiement de Skype entreprise Server 2015 avec tous les serveurs exécutant Skype entreprise Server 2015.

  - Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.

  - Un déploiement de Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les mises à jour cumulatives les plus récentes.
    
      - Le serveur Edge de Fédération et le serveur du tronçon suivant du serveur Edge de Fédération doivent exécuter Lync Server 2010 avec les mises à jour cumulatives les plus récentes.
    
      - Les outils d’administration de Skype entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de gestion.

  - Un déploiement mixte de Lync Server 2013 et de Skype entreprise Server 2015 avec les rôles serveur suivants dans au moins un site exécutant Skype entreprise Server 2015 :
    
      - Au moins un pool d’entreprise ou un serveur Standard Edition
    
      - Pool Directeur associé à la Fédération SIP, le cas échéant
    
      - Pool de serveurs Edge associé à la Fédération SIP

  - Un déploiement mixte de Lync Server 2010 et de Skype entreprise Server 2015 avec les rôles de serveurs suivants dans au moins un site exécutant Skype entreprise Server 2015 :
    
      - Au moins un pool d’entreprise ou un serveur Standard Edition
    
      - Pool Directeur associé à la Fédération SIP, le cas échéant
    
      - Pool de serveurs Edge associé à la Fédération SIP pour le site

  - Un déploiement mixte de Lync Server 2010 et de Lync Server 2013 avec les rôles serveur suivants dans au moins un site exécutant Lync Server 2013 :
    
      - Au moins un pool d’entreprise ou un serveur Standard Edition dans le site
    
      - Pool Directeur associé à la Fédération SIP, s’il existe dans le site
    
      - Pool de serveurs Edge associé à la Fédération SIP pour le site

<div>


> [!IMPORTANT]  
> Toutes les opérations de gestion des utilisateurs, y compris les déplacements entre les utilisateurs locaux et les UNRESOLVED_TOKEN_VAL (skypeforbusiness) en ligne, doivent être réalisées à l’aide de la dernière version installée des outils d’administration. Les outils d’administration doivent être installés sur un serveur distinct qui dispose d’un accès au déploiement local existant et à Internet. La cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-Csuser</A> pour déplacer des utilisateurs de votre déploiement local vers UNRESOLVED_TOKEN_VAL (skype16_online) doit être exécutée à partir des outils d’administration connectés à votre déploiement local.



</div>

Pour plus d’informations sur les topologies prises en charge, voir [topologies prises en charge dans Lync server 2013](lync-server-2013-supported-topologies.md)et [topologies de référence Lync Server 2013 pour les déploiements hybrides d’entreprise](https://go.microsoft.com/fwlink/p/?linkid=398709).

Pour plus d’informations sur la résolution des problèmes liés aux déploiements hybrides et à la connexion de PowerShell à Lync Online, voir [Lync Online : Lync PowerShell et Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Configuration requise pour les listes autorisées/bloquées de la Fédération

La liste des domaines autorisés inclut des domaines dont le nom de domaine complet (FQDN) du partenaire est configuré. Ces derniers sont parfois appelés *serveurs partenaires autorisés* ou *partenaires de Fédération directe*. Vous devez être familiarisé avec la différence entre la Fédération ouverte et la Fédération fermée, respectivement appelée liste de domaines de *découverte* et de *domaine partenaire autorisés*dans les déploiements locaux.

Les conditions requises suivantes doivent être remplies pour pouvoir configurer un déploiement hybride :

  - La correspondance de domaine doit être configurée de la même façon pour votre déploiement local et votre organisation Office 365. Si la découverte des partenaires est activée sur le déploiement local, la Fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n’est pas activée, alors la Fédération fermée doit être configurée pour votre client en ligne.

  - La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

  - La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

  - La Fédération doit être activée pour les communications externes pour le client en ligne, qui est configuré à l’aide du panneau de configuration Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Paramètres DNS

Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes de Lync doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la rubrique [Domain Name System (DNS) Requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Enregistrement DNS</p></td>
<td><p>Résolu par</p></td>
<td><p>Enregistrement DNS requis</p></td>
</tr>
<tr class="even">
<td><p>Enregistrement DNS SRV pour _sipfederationtls. _tcp. &lt;sipdomain.com&gt; pour tous les domaines SIP pris en charge résolus pour accéder à l’adresse IP externe du serveur Edge (s)</p></td>
<td><p>Serveur (s) Edge</p></td>
<td><p>Activer la communication fédérée dans une configuration hybride. Le serveur Edge doit indiquer où acheminer le trafic fédéré pour le domaine SIP qui est réparti entre local et en ligne.</p></td>
</tr>
<tr class="odd">
<td><p>Enregistrements DNS A (s) pour le nom de domaine complet du service de conférence Web Edge, par exemple webcon.contoso.com résolution des adresses IP externes Edge de conférence Web</p></td>
<td><p>Ordinateurs des utilisateurs connectés au réseau d’entreprise interne</p></td>
<td><p>Permettre aux utilisateurs en ligne de présenter ou d’afficher le contenu des réunions hébergées sur site. Le contenu inclut des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.</p></td>
</tr>
</tbody>
</table>


En fonction de la configuration de DNS dans votre organisation, il se peut que vous deviez ajouter ces enregistrements à la zone DNS hébergée interne pour les domaines SIP correspondants afin de fournir la résolution DNS interne à ces enregistrements.

</div>

<div>

## <a name="firewall-considerations"></a>Considérations relatives au pare-feu

Les ordinateurs de votre réseau doivent être en mesure d’effectuer des recherches DNS Internet standard. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour qu’ils acceptent les connexions basées sur des noms de \*domaine génériques (par exemple, tout le trafic provenant de. Outlook.com). Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d’adresses IP que vous voulez autoriser et les ports spécifiés.

Reportez-vous à la rubrique d’aide [URL et plages d’adresses IP Office 365](https://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Configuration requise pour les ports et les protocoles

En plus des ports requis pour la communication interne de Lync Server 2013, vous devez également configurer les ports suivants.


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
<td><p>TCP 443</p></td>
<td><p>Ouvrir entrant</p>
<ul>
<li><p>Services ADFS (rôle de serveur de fédération)</p>
<p>Pour plus d’informations, consultez la rubrique <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role services</a>.</p></li>
<li><p>Services ADFS (rôle de serveur proxy)</p></li>
<li><p>Portail Microsoft Online Services</p></li>
<li><p>Portail de mon entreprise</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Client Lync (communication vers Lync Online à partir de Lync Server sur site)</p></li>
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
<td><p>Ouvrir les ports entrants/sortants sur le serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Ouvrir les sessions de partage de données entrantes/sortantes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Ouverture des sessions audio, vidéo et de partage d’application</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Ouvrir le trafic entrant/sortant pour les sessions audio et vidéo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Ouvrir des sessions audio et vidéo sortantes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Comptes d’utilisateurs et données

Dans un déploiement hybride Lync Server 2013, tout utilisateur que vous souhaitez héberger dans Lync Online doit d’abord être créé dans le déploiement local, afin que le compte d’utilisateur soit créé dans les services de domaine Active Directory. Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise Online, ce qui déplace la liste des contacts de l’utilisateur.

Lorsque vous synchronisez des comptes d’utilisateurs entre vos déploiements Lync Online et Lync Online avec AD FS et DirSync, vous devez synchroniser les comptes AD de tous les utilisateurs Lync de votre organisation entre vos déploiements Lync sur site et en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et les utilisateurs en ligne de votre organisation peut ne pas fonctionner comme prévu.

<div>


> [!IMPORTANT]  
> Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte d’utilisateur n’est pas synchronisé avec Active Directory local et l’utilisateur n’existe pas dans l’environnement Active Directory local. Si vous avez déjà créé des utilisateurs dans Lync Online et que vous souhaitez configurer un environnement hybride avec un serveur Lync Server local, consultez la rubrique <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.



</div>

Vous devez également tenir compte des problèmes liés aux utilisateurs suivants lors de la planification d’un déploiement hybride.

  - **Contacts**   de l’utilisateur la limite de contacts pour les utilisateurs de Lync Online est de 250. Tous les contacts au-delà de ce numéro seront supprimés de la liste des contacts de l’utilisateur lors du déplacement du compte vers Lync Online.

  - **Messagerie instantanée et présence**   les listes de contacts, les groupes et les listes de contrôle d’accès des utilisateurs sont migrés avec le compte d’utilisateur.

  - **Données de conférence, contenu de réunion et réunions**   planifiées ce contenu n’est pas migré avec le compte d’utilisateur. Les utilisateurs doivent replanifier les réunions après la migration de leurs comptes vers Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Stratégies et fonctionnalités utilisateur

  - Dans un environnement hybride Lync Server 2013, les utilisateurs peuvent être activés pour la messagerie instantanée, la voix et les réunions en local ou en ligne, mais pas les deux en même temps.

  - **Client Lync certains**     utilisateurs peuvent exiger une nouvelle version du client lorsqu’ils sont déplacés vers Lync Online. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un pool Lync Server 2013 avant la migration vers Lync Online.
    
    Pour plus d’informations sur la prise en charge des clients, voir [clients pour Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) et [clients Lync pris en charge et les configurations des ports réseau](https://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Les stratégies locales et de configuration (non utilisateur)**   en ligne et locales nécessitent une configuration distincte. Vous ne pouvez pas définir des stratégies globales qui s’appliquent aux deux.

</div>

</div>

<span> </span>

</div>

</div>

</div>

