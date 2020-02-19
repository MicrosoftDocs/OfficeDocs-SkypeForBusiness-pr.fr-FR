---
title: Vérifier la connectivité entre les serveurs internes et les serveurs Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8165781f9604b84f5b846ebda8679f9110262b88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="015f1-102">Vérifier la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="015f1-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015f1-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="015f1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="015f1-104">Dans Lync Server 2013, un Assistant validation distinct était disponible pour vous aider à valider la connectivité entre les serveurs Edge et les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="015f1-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="015f1-105">Dans Lync Server 2013, la validation de la connectivité est exécutée automatiquement lorsque vous installez vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="015f1-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="015f1-106">Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Windows PowerShell **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion (ou tout ordinateur appartenant à un domaine sur lequel les composants principaux de Lync Server 2013 (OcsCore. msi) sont installés.</span><span class="sxs-lookup"><span data-stu-id="015f1-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="015f1-107">Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ».</span><span class="sxs-lookup"><span data-stu-id="015f1-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="015f1-108">Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="015f1-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="015f1-109">Vous pouvez vérifier la connectivité des utilisateurs externes séparément, notamment à l’aide de l’Analyseur de connectivité à distance d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="015f1-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="015f1-110">Pour plus d’informations, reportez-vous à [Vérifier la connectivité pour les utilisateurs externes dans Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="015f1-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

