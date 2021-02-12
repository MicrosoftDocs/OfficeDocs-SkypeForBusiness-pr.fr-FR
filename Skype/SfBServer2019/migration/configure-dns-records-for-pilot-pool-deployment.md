---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754054"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="686aa-104">Configuration des enregistrements DNS pour le déploiement d’un pool pilote</span><span class="sxs-lookup"><span data-stu-id="686aa-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="686aa-105">Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote.</span><span class="sxs-lookup"><span data-stu-id="686aa-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="686aa-106">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="686aa-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="686aa-107">Pour configurer des enregistrement d’hôte DNS (A)</span><span class="sxs-lookup"><span data-stu-id="686aa-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="686aa-108">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="686aa-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="686aa-109">Dans l’arborescence de la console de votre domaine, développez **Zones** de recherche avant, puis cliquez avec le bouton droit sur le domaine dans lequel Skype Entreprise Server 2019 sera installé.</span><span class="sxs-lookup"><span data-stu-id="686aa-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="686aa-110">Cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="686aa-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="686aa-111">Cliquez sur Nom , tapez le nom d’hôte pour le pool Skype Entreprise Server 2019 (le nom de domaine est supposé dans la zone où l’enregistrement est défini et n’a pas besoin d’être entré dans l’enregistrement A).</span><span class="sxs-lookup"><span data-stu-id="686aa-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="686aa-112">Cliquez **sur Adresse IP,** puis tapez l’adresse IP du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="686aa-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="686aa-113">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="686aa-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="686aa-114">Lorsque vous avez terminé, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="686aa-114">When you are finished, click **Done**.</span></span>
    

