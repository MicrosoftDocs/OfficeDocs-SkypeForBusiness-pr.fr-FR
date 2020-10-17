---
title: 'Lync Server 2013 : définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
description: 'Lync Server 2013 : définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946aec82f33dffe268fefb3548b8db2f5c19e1a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567760"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="1f1b3-103">Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f1b3-103">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f1b3-104">_**Dernière modification de la rubrique :** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="1f1b3-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="1f1b3-105">Effectuez cette procédure sur le site central si vous n’avez pas défini le Survivable Branch Appliance ou le serveur Survivable Branch Server lorsque vous l’avez ajouté à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-105">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="1f1b3-106">Pour définir un Survivable Branch Appliance ou un serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="1f1b3-106">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="1f1b3-107">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologies Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1f1b3-108">Dans l’arborescence de la console, développez le site central, développez **sites de succursale**, puis développez le nom du site de succursale où vous souhaitez déployer le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-108">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="1f1b3-109">Cliquez avec le bouton droit sur **Survivable Branch Appliances**, puis cliquez sur **nouveau Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-109">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f1b3-110"><STRONG>Survivable Branch Appliances</STRONG> est l’endroit où vous définissez les serveurs Survivable Branch Servers et les Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-110"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="1f1b3-111">Dans la boîte de dialogue **définir le Survivable Branch Appliance** , cliquez sur nom de domaine **complet**, tapez le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server que vous allez déployer sur ce site de succursale, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-111">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f1b3-112">Si vous définissez un Survivable Branch appliance, le nom que vous entrez dans le nom de <STRONG>domaine complet</STRONG> doit être le même que celui du Survivable Branch Appliance que vous avez affecté à l’attribut <STRONG>servicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f1b3-112">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="1f1b3-113">Pour plus d’informations, consultez <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">la rubrique ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-113">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="1f1b3-114">Cliquez sur **pool frontal**, cliquez sur le serveur frontal (pool de services d’utilisateurs) sur le site central auquel ce Survivable Branch Appliance ou le serveur Survivable Branch Server se connectera, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-114">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="1f1b3-115">Cliquez sur **serveur Edge**, cliquez sur le pool de serveurs Edge auquel ce Survivable Branch Appliance ou le serveur Survivable Branch Server se connectera pour fournir la connectivité PSTN aux utilisateurs distants du site de succursale, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-115">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="1f1b3-116">Cliquez sur **adresse IP ou nom de domaine complet**de la passerelle, puis tapez le nom de domaine complet ou l’adresse IP de l’homologue de passerelle auquel est associé le Survivable Branch Appliance ou le serveur Survivable Branch Server pour le routage des appels RTC entrants ou sortants.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-116">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f1b3-117">Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation qui se trouve à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-117">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="1f1b3-118">Cliquez sur **Port d’écoute pour la passerelle IP/PSTN**, puis acceptez le port par défaut.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-118">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="1f1b3-119">Dans **protocole de transport SIP**, cliquez sur le protocole de transport que le Survivable Branch Appliance ou le serveur Survivable Branch utilisera, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-119">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f1b3-120">Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="1f1b3-120">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="1f1b3-121">Si vous définissez un Survivable Branch Appliance, consultez la documentation du fournisseur de votre Survivable Branch Appliance pour vérifier que ce dernier prend en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-121">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="1f1b3-122">Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch Appliance ou serveur Survivable Branch Server, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="1f1b3-122">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="1f1b3-123">**Étape suivante**: [déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="1f1b3-123">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

