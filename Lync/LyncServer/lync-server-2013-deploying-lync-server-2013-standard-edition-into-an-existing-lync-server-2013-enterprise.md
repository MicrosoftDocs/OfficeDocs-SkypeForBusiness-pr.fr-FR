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

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="24542-102">Déploiement de Lync Server 2013 Standard Edition dans une instance existante de Lync Server 2013 Enterprise</span><span class="sxs-lookup"><span data-stu-id="24542-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24542-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="24542-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24542-104">Le déploiement d’un serveur Standard Edition dans un déploiement Enterprise Edition existant est semblable au déploiement de rôles serveur supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="24542-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="24542-105">Un serveur Standard Edition Server peut être déployé sur un autre site, ce qui permet aux utilisateurs de ce site d’être hébergés sur le serveur Standard Edition plutôt que le pool frontal sur un réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="24542-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="24542-106">Les procédures d’installation du nouveau site et des serveurs de ce site sont déjà définies dans d’autres sections de la documentation de [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="24542-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="24542-107">**Pour définir un nouveau site**</span><span class="sxs-lookup"><span data-stu-id="24542-107">**To define a new site**</span></span>

1.  <span data-ttu-id="24542-108">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="24542-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="24542-109">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **nouveau site central**.</span><span class="sxs-lookup"><span data-stu-id="24542-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="24542-110">Dans la page **identifier le site** , attribuez un nom au site et entrez éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="24542-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="24542-111">Suivez les procédures permettant de définir le reste de la topologie de site.</span><span class="sxs-lookup"><span data-stu-id="24542-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="24542-112">Pour plus d’informations, reportez-vous à [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="24542-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="24542-113">Publiez la topologie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="24542-113">Publish the updated topology.</span></span> <span data-ttu-id="24542-114">Pour plus d’informations, reportez-vous à [la rubrique publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="24542-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="24542-115">Configurer et installer un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="24542-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="24542-116">Si vous avez déployé un environnement uniquement avec un serveur Standard Edition Server, vous avez commencé le processus d’installation à partir de l’Assistant Déploiement de Lync Server à l’aide du lien <STRONG>préparer le premier serveur Standard Edition Server</STRONG> pour installer les fichiers de base de données initiale sur le nouveau serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="24542-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="24542-117"><STRONG>Ne suivez pas</STRONG> ce processus lors de l’installation d’un serveur Standard Edition Server dans un déploiement 2013 Lync Server existant.</span><span class="sxs-lookup"><span data-stu-id="24542-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

