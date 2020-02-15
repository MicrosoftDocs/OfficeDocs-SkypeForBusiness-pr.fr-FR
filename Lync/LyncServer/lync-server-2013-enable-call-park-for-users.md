---
title: 'Lync Server 2013 : activation du parcage d’appel pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8d739c9987c0a17c29997fad8ac47b2d886fbea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="d46b8-102">Activer le parcage d’appel pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d46b8-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d46b8-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d46b8-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d46b8-104">Les utilisateurs ne peuvent pas parkiser les appels ou récupérer les appels parqués jusqu’à ce qu’ils soient activés pour le parcage d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="d46b8-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d46b8-105">Par défaut, le parcage d’appel est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d46b8-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="d46b8-106">Vous pouvez activer le parcage d’appel au niveau de l’étendue globale ou de l’étendue du site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d46b8-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="d46b8-107">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="d46b8-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="d46b8-108">Si vous avez plusieurs stratégies de voix, vérifiez toutes les stratégies pour activer le parcage d’appel, et pas seulement la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="d46b8-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="d46b8-109">Pour utiliser le panneau de configuration Lync Server pour activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d46b8-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="d46b8-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou**CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="d46b8-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d46b8-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d46b8-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d46b8-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d46b8-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="d46b8-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="d46b8-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="d46b8-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="d46b8-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="d46b8-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="d46b8-118">Pour utiliser des applets de commande afin d’activer le parcage d’appel pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d46b8-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="d46b8-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d46b8-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d46b8-120">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d46b8-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d46b8-121">Générer</span><span class="sxs-lookup"><span data-stu-id="d46b8-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="d46b8-122">Par exemple, pour activer le parcage d’appel pour la stratégie de voix globale par défaut :</span><span class="sxs-lookup"><span data-stu-id="d46b8-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d46b8-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d46b8-123">See Also</span></span>


[<span data-ttu-id="d46b8-124">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d46b8-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

