---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer le pool de pilotes, vous devez mettre à jour les entrées de l’hôte DNS pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813852"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="00954-104">Configuration des enregistrements DNS pour le déploiement d’un pool pilote</span><span class="sxs-lookup"><span data-stu-id="00954-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="00954-105">Avant de déployer le pool de pilotes, vous devez mettre à jour les entrées de l’hôte DNS pour le pool pilote.</span><span class="sxs-lookup"><span data-stu-id="00954-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="00954-106">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="00954-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="00954-107">Pour configurer les enregistrements d’un hôte DNS</span><span class="sxs-lookup"><span data-stu-id="00954-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="00954-108">Sur le serveur DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="00954-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="00954-109">Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Skype entreprise Server 2019 sera installé.</span><span class="sxs-lookup"><span data-stu-id="00954-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="00954-110">Cliquez sur **nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="00954-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="00954-111">Cliquez sur **nom**, entrez le nom d’hôte du pool 2019 de Skype entreprise Server (le nom de domaine est utilisé dans la zone dans laquelle l’enregistrement est défini et n’a pas besoin d’être entré dans le cadre de l’enregistrement a).</span><span class="sxs-lookup"><span data-stu-id="00954-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="00954-112">Cliquez sur **adresse IP**, puis tapez l’adresse IP de la liste frontale.</span><span class="sxs-lookup"><span data-stu-id="00954-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="00954-113">Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="00954-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="00954-114">Lorsque vous avez terminé, cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="00954-114">When you are finished, click **Done**.</span></span>
    

