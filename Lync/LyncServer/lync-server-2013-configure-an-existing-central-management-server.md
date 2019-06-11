---
title: 'Lync Server 2013 : Configuration d’un serveur de gestion centralisée existant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="2a782-102">Configuration d’un serveur de gestion centralisée existant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a782-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a782-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2a782-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2a782-104">Si vous réutilisez un serveur de gestion central à partir d’un déploiement 2013 de Lync Server, vous devez exécuter la procédure décrite ci-dessous pour vous assurer que le panneau de configuration de Lync Server et Windows PowerShell fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="2a782-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="2a782-105">Pour configurer un serveur de gestion central existant</span><span class="sxs-lookup"><span data-stu-id="2a782-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="2a782-106">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a782-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a782-107">Utilisez l’applet de commande **Update-CsAdminRole** pour mettre à jour les rôles de contrôle d’accès basé sur les rôles stockés dans le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="2a782-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a782-108">Aucune sortie n’est attendue, sauf s’il y a une erreur.</span><span class="sxs-lookup"><span data-stu-id="2a782-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

