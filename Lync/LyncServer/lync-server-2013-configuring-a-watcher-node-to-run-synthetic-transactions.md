---
title: 'Lync Server 2013 : configuration d’un nœud observateur pour exécuter des transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9514099b3981dafdbb34911d0cedd249221c5621
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499101"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="87103-102">Configuration d’un nœud observateur pour exécuter des transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87103-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87103-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="87103-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="87103-p101">Une fois les fichiers de l’agent System Center installés, vous devez configurer le nœud observateur. La procédure varie selon que l’ordinateur du nœud observateur se trouve à l’intérieur ou à l’extérieur de votre réseau de périphérie.</span><span class="sxs-lookup"><span data-stu-id="87103-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="87103-106">Lorsque vous configurez un nœud observateur, vous devez également choisir le type de méthode d’authentification utilisé par ce nœud.</span><span class="sxs-lookup"><span data-stu-id="87103-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="87103-107">Lync Server 2013 vous permet de choisir l’une des deux méthodes d’authentification suivantes : serveur approuvé ou authentification des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="87103-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="87103-108">Les différences entre ces deux méthodes sont indiquées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="87103-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87103-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="87103-109">Configuration</span></span></th>
<th><span data-ttu-id="87103-110">Description</span><span class="sxs-lookup"><span data-stu-id="87103-110">Description</span></span></th>
<th><span data-ttu-id="87103-111">Emplacements pris en charge</span><span class="sxs-lookup"><span data-stu-id="87103-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87103-112">Serveur approuvé</span><span class="sxs-lookup"><span data-stu-id="87103-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="87103-113">Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="87103-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="87103-114">Utile pour les administrateurs qui préfèrent gérer un seul certificat au lieu de plusieurs mots de passe d’utilisateur sur chaque nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="87103-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="87103-115">Au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="87103-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="87103-p103">Notez qu’avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud observateur et les pools surveillés se trouvent dans des domaines différents, utilisez l’authentification des informations d’identification à la place.</span><span class="sxs-lookup"><span data-stu-id="87103-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87103-118">Authentification des informations d’identification</span><span class="sxs-lookup"><span data-stu-id="87103-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="87103-119">Stocke les noms d’utilisateur et mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="87103-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="87103-p104">Ce mode implique davantage d’opérations de gestion des mots de passe, mais est la seule option pour les nœuds observateurs situés en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="87103-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="87103-122">En dehors de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="87103-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="87103-123">Au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="87103-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87103-124">Vous devez également vérifier que votre pare-feu comporte des règles de trafic entrant pour MonitoringHost.exe et PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="87103-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="87103-125">Si ces processus sont bloqués par le pare-feu, vos transactions synthétiques échouent avec une erreur 504 (délai d’attente du serveur).</span><span class="sxs-lookup"><span data-stu-id="87103-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

