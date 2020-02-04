---
title: 'Lync Server 2013 : Déploiement de Lync Server 2013 Standard Edition dans une instance existante de Lync Server 2013 Enterprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Déploiement de Lync Server 2013 Standard Edition dans une instance existante de Lync Server 2013 Enterprise

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Le déploiement d’un serveur Standard Edition dans un déploiement Enterprise Edition existant est semblable au déploiement de rôles serveur supplémentaires. Un serveur Standard Edition Server peut être déployé sur un autre site, ce qui permet aux utilisateurs de ce site d’être hébergés sur le serveur Standard Edition plutôt que le pool frontal sur un réseau étendu (WAN). Les procédures d’installation du nouveau site et des serveurs de ce site sont déjà définies dans d’autres sections de la documentation de [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Pour définir un nouveau site**

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **nouveau site central**.

3.  Dans la page **identifier le site** , attribuez un nom au site et entrez éventuellement une description.

4.  Suivez les procédures permettant de définir le reste de la topologie de site. Pour plus d’informations, reportez-vous à [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publiez la topologie mise à jour. Pour plus d’informations, reportez-vous à [la rubrique publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configurer et installer un serveur Standard Edition Server.
    
    <div>
    

    > [!Caution]  
    > Si vous avez déployé un environnement uniquement avec un serveur Standard Edition Server, vous avez commencé le processus d’installation à partir de l’Assistant Déploiement de Lync Server à l’aide du lien <STRONG>préparer le premier serveur Standard Edition Server</STRONG> pour installer les fichiers de base de données initiale sur le nouveau serveur Standard Edition. <STRONG>Ne suivez pas</STRONG> ce processus lors de l’installation d’un serveur Standard Edition Server dans un déploiement 2013 Lync Server existant.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

