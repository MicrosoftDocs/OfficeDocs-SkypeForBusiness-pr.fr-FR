---
title: 'Lync Server 2013 : supprimer une règle de stratégie de version de client existante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad64a77e8244bf1eb2073a5d62edcb30e41eb20
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="b541d-102">Supprimer une règle de stratégie de version de client existante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b541d-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b541d-103">_**Dernière modification de la rubrique :** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="b541d-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="b541d-104">Une stratégie de version de client est composée d’un ensemble de règles de stratégie de version de client.</span><span class="sxs-lookup"><span data-stu-id="b541d-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="b541d-105">Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b541d-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="b541d-106">Vous pouvez supprimer des règles individuelles d’une stratégie de version de client à partir de Lync Server 2013 Control Panel.</span><span class="sxs-lookup"><span data-stu-id="b541d-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="b541d-107">Pour supprimer des règles de stratégie de version de client avec le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b541d-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b541d-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b541d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b541d-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b541d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b541d-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b541d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b541d-111">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation de la stratégie de la **version de client** .</span><span class="sxs-lookup"><span data-stu-id="b541d-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="b541d-112">Dans la page **stratégie de version du client** , double-cliquez sur la stratégie de version du client pour la règle que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b541d-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="b541d-113">Les règles apparaissent dans la page **modifier la stratégie de version du client** .</span><span class="sxs-lookup"><span data-stu-id="b541d-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="b541d-114">Pour supprimer une règle, sélectionnez-la, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b541d-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

