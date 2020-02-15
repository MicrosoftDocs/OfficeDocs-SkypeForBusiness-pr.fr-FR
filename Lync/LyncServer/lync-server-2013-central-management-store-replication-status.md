---
title: 'Lync Server 2013 : état de réplication du magasin central de gestion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d411733712cf274760a45cd4e315b4f02a66e0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="20623-102">État de réplication du magasin central de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20623-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20623-103">_**Dernière modification de la rubrique :** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="20623-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="20623-104">Lorsqu’un administrateur apporte une modification d’un type à Lync Server (par exemple, lorsqu’un administrateur crée une nouvelle stratégie de voix ou modifie les paramètres de configuration du serveur de carnet d’adresses), cette modification est enregistrée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="20623-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="20623-105">À son tour, la modification doit être répliquée sur tous les ordinateurs qui exécutent des services ou des rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20623-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="20623-106">Pour répliquer des données, le réplicateur principal (exécuté sur le serveur de gestion centralisée) crée une capture instantanée des données de configuration modifiées.</span><span class="sxs-lookup"><span data-stu-id="20623-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="20623-107">Une copie de cette capture instantanée est ensuite envoyée à chaque ordinateur exécutant des services ou des rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20623-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="20623-108">Sur ces ordinateurs, un agent de réplication reçoit la capture instantanée et télécharge les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="20623-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="20623-109">L’agent envoie ensuite au réplicateur principal un message signalant l’état de la réplication la plus récente.</span><span class="sxs-lookup"><span data-stu-id="20623-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="20623-110">La cmdlet Get-CsManagementStoreReplicationStatus vous permet de vérifier l’état de réplication de tout ou partie des ordinateurs Lync Server de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="20623-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="20623-111">Qui peut exécuter cette applet de commande ?</span><span class="sxs-lookup"><span data-stu-id="20623-111">Who can run this cmdlet?</span></span> <span data-ttu-id="20623-112">Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Get-CsManagementStoreReplicationStatus : RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="20623-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="20623-113">Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="20623-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="20623-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20623-114">See Also</span></span>


[<span data-ttu-id="20623-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="20623-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

