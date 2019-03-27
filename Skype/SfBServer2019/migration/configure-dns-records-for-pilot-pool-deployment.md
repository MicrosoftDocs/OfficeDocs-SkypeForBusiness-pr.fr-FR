---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872738"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="da296-104">Configuration des enregistrements DNS pour le déploiement d’un pool pilote</span><span class="sxs-lookup"><span data-stu-id="da296-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="da296-105">Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote.</span><span class="sxs-lookup"><span data-stu-id="da296-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="da296-106">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="da296-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="da296-107">Pour configurer les enregistrements d’hôte DNS A</span><span class="sxs-lookup"><span data-stu-id="da296-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="da296-108">Sur le serveur de nom de domaine DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="da296-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="da296-109">Dans l’arborescence de la console pour votre domaine, développez **Zones de recherche directes**, puis cliquez sur le domaine dans lequel Skype pour Business Server 2019 sera installé.</span><span class="sxs-lookup"><span data-stu-id="da296-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="da296-110">Cliquez sur **nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="da296-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="da296-111">Cliquez sur **nom**, tapez le nom d’hôte pour le Skype pour le pool d’entreprise Server 2019 (le nom de domaine est déterminée automatiquement à partir de la zone que l’enregistrement est défini dans et ne doit pas figurer dans le cadre de l’enregistrement A).</span><span class="sxs-lookup"><span data-stu-id="da296-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="da296-112">Cliquez sur **Adresse IP**, puis tapez l’adresse IP pour le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="da296-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="da296-113">Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="da296-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="da296-114">Lorsque vous avez terminé, cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="da296-114">When you are finished, click **Done**.</span></span>
    

