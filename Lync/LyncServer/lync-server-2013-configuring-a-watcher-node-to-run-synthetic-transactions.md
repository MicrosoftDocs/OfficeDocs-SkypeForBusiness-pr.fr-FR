---
title: 'Lync Server 2013: configuration d’un nœud d’observateur pour exécuter des transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="8d7e4-102">Configuration d’un nœud d’observateur pour exécuter des transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d7e4-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d7e4-103">_**Dernière modification de la rubrique:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="8d7e4-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="8d7e4-104">Une fois les fichiers de l’agent de centre système installés, vous devez configurer le nœud de l’observateur.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="8d7e4-105">Les étapes à suivre pour configurer un nœud d’observateur varient selon que votre ordinateur de nœud de l’observateur se trouve à l’intérieur du réseau de périmètre ou en dehors de votre réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="8d7e4-106">Lorsque vous configurez un nœud observateur, vous devez également sélectionner le type de méthode d’authentification utilisé par ce nœud.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="8d7e4-107">Lync Server 2013 vous permet de choisir parmi deux méthodes d’authentification: serveur de confiance ou authentification des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="8d7e4-108">Les différences entre ces deux méthodes sont décrites dans le tableau suivant:</span><span class="sxs-lookup"><span data-stu-id="8d7e4-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d7e4-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="8d7e4-109">Configuration</span></span></th>
<th><span data-ttu-id="8d7e4-110">Description</span><span class="sxs-lookup"><span data-stu-id="8d7e4-110">Description</span></span></th>
<th><span data-ttu-id="8d7e4-111">Emplacements pris en charge</span><span class="sxs-lookup"><span data-stu-id="8d7e4-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d7e4-112">Serveur de confiance</span><span class="sxs-lookup"><span data-stu-id="8d7e4-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="8d7e4-113">Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="8d7e4-114">Cette fonctionnalité est utile pour les administrateurs préférant gérer un certificat unique au lieu de nombreux mots de passe d’utilisateur sur chaque nœud d’observateur.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="8d7e4-115">Dans l’entreprise</span><span class="sxs-lookup"><span data-stu-id="8d7e4-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="8d7e4-116">Notez que, dans cette méthode, le nœud Watcher doit se trouver dans le même domaine que les pools surveillés.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="8d7e4-117">Si le nœud d’observation et les pools surveillés figurent dans des domaines différents, utilisez plutôt l’authentification des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d7e4-118">Authentification des informations d’identification</span><span class="sxs-lookup"><span data-stu-id="8d7e4-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="8d7e4-119">Stocke les noms d’utilisateur et les mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="8d7e4-120">Ce mode nécessite une plus grande gestion du mot de passe, mais est la seule option disponible pour les nœuds d’observation situés en dehors de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="8d7e4-121">Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="8d7e4-122">En dehors de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="8d7e4-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="8d7e4-123">Dans l’entreprise</span><span class="sxs-lookup"><span data-stu-id="8d7e4-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8d7e4-124">Vous devez également vérifier que votre pare-feu dispose de règles de trafic entrant pour MonitoringHost. exe et PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="8d7e4-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="8d7e4-125">Si ces processus sont bloqués par le pare-feu, vos transactions synthétiques échoueront avec l’erreur 504 (délai d’expiration du serveur).</span><span class="sxs-lookup"><span data-stu-id="8d7e4-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

