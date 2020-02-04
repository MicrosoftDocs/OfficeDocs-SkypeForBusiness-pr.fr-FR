---
title: 'Lync Server 2013 : Configuration des noms de domaine complets d’une batterie de serveurs web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="54c09-102">Configuration des noms de domaine complets d’une batterie de serveurs web pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c09-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c09-103">_**Dernière modification de la rubrique :** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="54c09-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="54c09-104">Lors de la définition de la configuration du serveur Standard Edition Server, du pool frontal ou du pool de directeurs dans le générateur de topologie, vous configurez un nom de domaine complet (FQDN) pour les services Web externes.</span><span class="sxs-lookup"><span data-stu-id="54c09-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="54c09-105">Pendant le processus de connexion d’un client hébergé sur le serveur Standard Edition ou du pool frontal, les noms de domaine complets configurés pour les services Web sont envoyés par le biais de la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="54c09-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="54c09-106">Si vous avez besoin d’ajouter ou de modifier l’URL des services Web externes, vous utilisez le générateur de topologie pour configurer ou reconfigurer la configuration des services Web à l’aide de la procédure décrite dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="54c09-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="54c09-107">Pour configurer un nom de domaine complet du pool externe pour les services Web</span><span class="sxs-lookup"><span data-stu-id="54c09-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="54c09-108">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="54c09-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="54c09-109">Dans le générateur de **topologie, dans**l’arborescence de la console sous les **éditions frontale standard**, cliquez avec le bouton droit sur le nom du **pool, puis**cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="54c09-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="54c09-110">Dans la section **services Web** , ajoutez ou modifiez le **nom de domaine complet des services Web externes**.</span><span class="sxs-lookup"><span data-stu-id="54c09-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="54c09-111">Passez en revue et ajustez les **ports Listening** pour HTTP et HTTPS.</span><span class="sxs-lookup"><span data-stu-id="54c09-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="54c09-112">Les valeurs par défaut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="54c09-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="54c09-113">**Ports Listening :** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="54c09-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="54c09-114">**Ports publiés :** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="54c09-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="54c09-115">Lorsque le port **Listening** correspond au port sur lequel les services Web externes seront configurés pour recevoir des demandes de la part du proxy inverse, et que les **ports publiés** correspondent aux ports publiés en externe par le proxy inverse et sont communiqués aux clients lors de la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="54c09-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="54c09-116">Lorsque vous avez terminé vos ajouts et mises à jour, cliquez sur **OK** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="54c09-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="54c09-117">Cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="54c09-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c09-118">Après la publication réussie, un lien vous informant que vous devez effectuer des étapes supplémentaires est peut-être affiché.</span><span class="sxs-lookup"><span data-stu-id="54c09-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="54c09-119">Le lien, si vous cliquez dessus, ouvre une liste de serveurs affectés par les modifications apportées au générateur de topologie, qui vous oblige à réexécuter l’Assistant Déploiement de Lync Server sur chaque serveur pour mettre à jour la configuration pour les composants ajoutés, supprimés ou modifiés.</span><span class="sxs-lookup"><span data-stu-id="54c09-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="54c09-120">Répétez ces étapes pour chaque serveur Standard Edition, pool frontal, directeur ou pool de directeurs au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="54c09-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

