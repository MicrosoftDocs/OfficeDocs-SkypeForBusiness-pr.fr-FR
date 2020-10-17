---
title: Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33c3db01f772f43ea8507cee5c309b6705c8a69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528141"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-19_

Pour les serveurs Standard Edition et les serveurs frontaux et les directeurs, le programme d’installation de Lync Server 2013 crée des répertoires virtuels dans les services Internet (IIS) aux fins suivantes :

  - permettre aux utilisateurs de télécharger des fichiers du service de carnet d’adresses ;

  - Pour permettre aux clients d’obtenir des mises à jour

  - activer les conférences ;

  - permettre aux utilisateurs de télécharger le contenu de réunions ;

  - permettre aux utilisateurs de développer des groupes de distribution ;

  - activer la téléconférence ;

  - activer les fonctionnalités du service Response Group.

En outre, la mise à jour cumulative de Lync Server 2010 : novembre 2011 installer crée des répertoires virtuels dans les services Internet (IIS) dans les buts suivants :

  - Sur les serveurs frontaux ou les serveurs Standard Edition pour prendre en charge la fonctionnalité de mobilité, telle que la messagerie instantanée et la présence, sur les appareils mobiles

  - Sur les serveurs frontaux ou Standard Edition et sur les directeurs pour permettre aux appareils mobiles de découvrir automatiquement les ressources de mobilité



> [!NOTE]
> Si vous déployez la mobilité, nous vous recommandons d’utiliser les services Internet (IIS) 7.5. Le programme d’installation de Lync Server Mobility service définit certains indicateurs ASP.NET pour améliorer les performances. Les services Internet (IIS) 7.5 sont installés par défaut sur Windows Server 2008 R2 et le programme d’installation du service de mobilité modifie automatiquement les paramètres ASP.NET. Si vous utilisez les services Internet (IIS) 7.0 sur Windows Server 2008, vous devez modifier manuellement ces paramètres.



Lync Server nécessite l’installation des modules IIS suivants :


> [!IMPORTANT]
> Si votre organisation exige que vous localisiez les services Internet (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue de configuration. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Lync Server seront également déployés sur ce lecteur. Pour plus d’informations sur la façon de déplacer le INETPUB déployé par le gestionnaire Windows Server lors de l’installation d’IIS, reportez-vous à la rubrique <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .


  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Analyzer

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Compression du contenu dynamique

  - Console de gestion IIS

  - Scripts et outils de gestion IIS

  - Authentification anonyme (installée par défaut avec IIS)

  - Authentification par mappage de certificat client

Le tableau suivant répertorie les URI des répertoires virtuels pour l’accès interne et les ressources du système de fichiers auxquelles ils se rapportent.

### <a name="virtual-directories-for-internal-access"></a>Répertoires virtuels pour l’accès interne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>URI du répertoire virtuel</th>
<th>Se rapporte à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur de carnet d’adresses</p></td>
<td><p>&lt;nom de domaine complet interne https:// &gt; /ABS/int/Handler</p></td>
<td><p>Emplacement des fichiers téléchargés du serveur de carnet d’adresses pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Service de découverte automatique</p></td>
<td><p>&lt;nom de domaine complet interne https:// &gt; /autodiscover</p></td>
<td><p>Emplacement du service de découverte automatique Lync Server qui localise les ressources de mobilité pour les utilisateurs d’appareils mobiles internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour du client</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /AutoUpdate/int</p></td>
<td><p>Emplacement des fichiers de mise à jour pour les clients internes basés sur ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>CONF</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /conf/int</p></td>
<td><p>Emplacement des ressources de conférence pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour des périphériques</p></td>
<td><p>&lt;nom de domaine complet (FQDN) interne http:// &gt; /DeviceUpdateFiles_Int</p></td>
<td><p>Emplacement des fichiers de mise à jour des appareils de communications unifiées pour les appareils de communications unifiées internes.</p></td>
</tr>
<tr class="even">
<td><p>Satisfaire</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /etc/place/null</p></td>
<td><p>Emplacement du contenu de réunion pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Service de mobilité</p></td>
<td><p>&lt;nom de domaine complet interne https:// &gt; /MCX</p></td>
<td><p>Emplacement des ressources du service de mobilité pour les utilisateurs d’appareils mobiles internes.</p></td>
</tr>
<tr class="even">
<td><p>Développement de groupes et service de requête web du carnet d’adresses</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /GroupExpansion/int/service.asmx</p></td>
<td><p>Emplacement du service web qui active le développement des groupes pour les utilisateurs internes. Il s’agit également de l’emplacement du service de requête sur le Web du carnet d’adresses qui fournit des informations de liste d’adresses globales aux clients mobiles Lync mobile Microsoft Lync 2010 internes.</p></td>
</tr>
<tr class="odd">
<td><p>Téléconférence</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /PhoneConferencing/int</p></td>
<td><p>Emplacement des données de téléconférence pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Mises à jour des périphériques</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /RequestHandler</p></td>
<td><p>Emplacement du Gestionnaire des demandes du service web de mise à jour des périphériques qui permet aux appareils de communications unifiées internes de télécharger des journaux et de vérifier l’existence de mises à jour.</p></td>
</tr>
<tr class="odd">
<td><p>Application Response Group</p></td>
<td><p>&lt;nom de domaine complet interne http:// &gt; /RgsConfig</p>
<p>&lt;nom de domaine complet interne http:// &gt; /RgsClients</p></td>
<td><p>Emplacement de l’outil de configuration du service Response Group.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Pour les pools frontaux dans une configuration consolidée, vous devez déployer les services Internet (IIS) avant de pouvoir ajouter des serveurs au pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" />Note de sécurité :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez utiliser le composant logiciel enfichable d’administration IIS pour assigner le certificat utilisé par le serveur de composants web IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

