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
ms.openlocfilehash: c00ffe97b77f20107fc3351a678c71e28bbc6675
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-19_

Pour les serveurs Standard Edition et frontal, et les directeurs, le programme d’installation de Lync Server 2013 crée des répertoires virtuels dans Internet Information Services (IIS) aux fins suivantes :

  - Pour permettre aux utilisateurs de télécharger des fichiers à partir du service de carnet d’adresses

  - Pour permettre aux clients d’obtenir des mises à jour

  - Pour activer les conférences

  - Pour permettre aux utilisateurs de télécharger le contenu d’une réunion

  - Pour permettre aux utilisateurs d’étendre les groupes de distribution

  - Pour activer la fonction de conférence téléphonique

  - Pour activer les fonctionnalités de Response Group

Par ailleurs, la mise à jour cumulative pour Lync Server 2010 : novembre 2011 du programme d’installation crée des répertoires virtuels dans les services Internet (IIS) pour les raisons suivantes :

  - Serveur frontal ou serveurs Standard Edition pour prendre en charge les fonctionnalités de mobilité, telles que la messagerie instantanée et la présence, sur les appareils mobiles

  - Sur des serveurs frontaux ou Standard Edition et sur des directeurs pour permettre aux appareils mobiles de détecter automatiquement les ressources de mobilité



> [!NOTE]
> Si vous déployez une mobilité, nous vous recommandons d’utiliser IIS 7,5. Le programme d’installation de service de mobilité Lync Server définit des indicateurs ASP.NET pour améliorer les performances. IIS 7,5 est installé par défaut sur Windows Server 2008 R2 et le programme d’installation de service de mobilité modifie automatiquement les paramètres de ASP.NET. Si vous utilisez IIS 7,0 sur Windows Server 2008, vous devez modifier manuellement ces paramètres.



Le serveur Lync nécessite l’installation des modules IIS suivants :


> [!IMPORTANT]
> Si votre organisation nécessite que vous localisiez les services Internet (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers du serveur Lync dans la boîte de dialogue d’installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers du serveur Lync sera également déployé sur ce lecteur. Pour plus d’informations sur la façon de déplacer le INETPUB déployé par Windows Server Manager lors de l' <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>installation d’IIS, voir.


  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Suivi

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Compression du contenu dynamique

  - Console de gestion des services Internet (IIS)

  - Scripts et outils de gestion des services Internet (IIS)

  - Authentification anonyme (installée par défaut lors de l’installation d’IIS)

  - Authentification par mappage de certificat client

Le tableau suivant répertorie les URI des répertoires virtuels pour l’accès interne et les ressources système de fichiers auxquelles ils font référence.

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
<th>URI de répertoire virtuel</th>
<th>Fait référence à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur de carnet d’adresses</p></td>
<td><p>nom&lt;de domaine&gt;complet https:///ABS/int/Handler</p></td>
<td><p>Emplacement des fichiers de téléchargement de carnet d’adresses pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Service de découverte automatique</p></td>
<td><p>nom&lt;de domaine&gt;complet https:///autodiscover</p></td>
<td><p>Emplacement du service de découverte automatique de Lync Server qui recherche les ressources de mobilité pour les utilisateurs d’appareils mobiles internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour du client</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///AutoUpdate/int</p></td>
<td><p>Emplacement des fichiers de mise à jour pour les clients basés sur des ordinateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Donne</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///conf/int</p></td>
<td><p>Emplacement des ressources de conférence pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour de périphériques</p></td>
<td><p>DeviceUpdateFiles_Int&lt;FQDN&gt;interne http://</p></td>
<td><p>Emplacement des fichiers de mise à jour de l’appareil de communications unifiées (UC) pour les appareils UC internes.</p></td>
</tr>
<tr class="even">
<td><p>Répond</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///etc/place/null</p></td>
<td><p>Emplacement du contenu de la réunion pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Service de mobilité</p></td>
<td><p>nom&lt;de domaine&gt;complet https:///MCX</p></td>
<td><p>Emplacement des ressources de service de mobilité pour les utilisateurs de périphériques mobiles internes.</p></td>
</tr>
<tr class="even">
<td><p>Extension du groupe et service de requête Web du carnet d’adresses</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///GroupExpansion/int/service.asmx</p></td>
<td><p>Emplacement du service Web qui autorise l’extension du groupe pour les utilisateurs internes. Il s’agit également de l’emplacement du service de requête sur le carnet d’adresses qui fournit les informations de liste d’adresses globale aux clients mobiles Lync mobile de Lync mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Conférences téléphoniques</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///PhoneConferencing/int</p></td>
<td><p>Emplacement des données de la conférence téléphonique pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Mises à jour de périphériques</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///RequestHandler</p></td>
<td><p>Emplacement du gestionnaire de demandes de service Web de mise à jour de l’appareil qui permet aux périphériques d’UC internes de télécharger les journaux et de rechercher les mises à jour.</p></td>
</tr>
<tr class="odd">
<td><p>application Response Group</p></td>
<td><p>nom&lt;de domaine&gt;complet http:///RgsConfig</p>
<p>nom&lt;de domaine&gt;complet http:///RgsClients</p></td>
<td><p>Emplacement de l’outil de configuration de Response Group.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Pour les pools frontaux dans une configuration consolidée, vous devez déployer IIS avant de pouvoir ajouter des serveurs au pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez utiliser le composant logiciel enfichable d’administration d’IIS pour affecter le certificat utilisé par le serveur de composants Web IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

