---
title: 'Lync Server 2013 : Rechercher des utilisateurs de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Rechercher des utilisateurs de Lync Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-14_

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer des utilisateurs pour Lync Server 2013. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à l’aide du panneau de configuration de Lync Server ou du composant logiciel enfichable utilisateurs et ordinateurs Active Directory. La procédure suivante vous explique comment utiliser le panneau de configuration de Lync Server pour rechercher des utilisateurs.

<div>


> [!NOTE]  
> Dans un environnement doté d’une topologie de forêt centrale, il est possible que les résultats de la recherche soient inexacts lorsque vous recherchez un utilisateur à l’aide de son adresse de messagerie. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP (par exemple, SIP : nom), ajouter un filtre de recherche et sélectionner une adresse SIP contenant une adresse de messagerie partielle ou utiliser l’applet de requête <STRONG>Get-Csuser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Pour rechercher un ou plusieurs utilisateurs

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de **recherche utilisateurs** , entrez tout ou la première partie du nom d’affichage, prénom, nom, nom de compte Sam, adresse SIP ou URI de ligne du compte d’utilisateur que vous souhaitez rechercher, puis cliquez sur **Rechercher**.

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur la flèche de développement située dans le coin supérieur droit de l’écran au-dessus des résultats de la **recherche**, puis cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété User en le tapant ou en cliquant sur la flèche dans la liste déroulante pour sélectionner une propriété d’utilisateur.
    
    3.  Dans la liste **égal à** , cliquez sur **égal à** ou **n’est pas égal à**.
    
    4.  Dans la zone de texte, tapez les critères de recherche que vous voulez utiliser pour filtrer les résultats de recherche, puis cliquez sur **Rechercher**.

6.  Les résultats de la recherche apparaissent sous résultats de la **recherche**. Vous pouvez sélectionner tout ou partie des utilisateurs de la liste et effectuer des tâches de configuration pour les utilisateurs sélectionnés.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Affichage d’informations sur les comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

