---
title: 'Lync Server 2013 : activer ou désactiver le contrôle de version du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="95dc7-102">Activer ou désactiver le contrôle de version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95dc7-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95dc7-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="95dc7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="95dc7-104">Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, globalement ou pour des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="95dc7-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="95dc7-105">La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur.</span><span class="sxs-lookup"><span data-stu-id="95dc7-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="95dc7-106">Lorsque la configuration globale est activée, toutes les stratégies de version de client en vigueur sont prises en compte lorsque les utilisateurs essaient de se connecter.</span><span class="sxs-lookup"><span data-stu-id="95dc7-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="95dc7-107">Vous pouvez désactiver la configuration de la version du client global si vous ne souhaitez pas que le contrôle de version du client se produise.</span><span class="sxs-lookup"><span data-stu-id="95dc7-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="95dc7-108">Vous pouvez activer ou désactiver le contrôle de version du client via le panneau de configuration de Lync Server 2013 ou Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="95dc7-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95dc7-109">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes ne sont affectés que par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="95dc7-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="95dc7-110">Pour activer ou désactiver le contrôle de version du client à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="95dc7-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="95dc7-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="95dc7-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95dc7-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95dc7-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95dc7-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95dc7-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95dc7-114">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="95dc7-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="95dc7-115">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="95dc7-115">Do the following:</span></span>
    
      - <span data-ttu-id="95dc7-116">Pour activer ou désactiver globalement le contrôle de version, double-cliquez sur la configuration **globale** , puis modifiez les paramètres.</span><span class="sxs-lookup"><span data-stu-id="95dc7-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="95dc7-117">Pour activer ou désactiver le contrôle de version du client pour un site particulier, cliquez sur **nouveau**, sélectionnez le site, cliquez sur **OK**, puis modifiez les paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="95dc7-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="95dc7-118">Activation ou désactivation du contrôle de version du client à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95dc7-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="95dc7-119">Vous pouvez activer ou désactiver le contrôle de version du client à l’aide de l’applet **de contrôle Set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="95dc7-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="95dc7-120">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95dc7-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="95dc7-121">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="95dc7-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="95dc7-122">Pour activer le contrôle de version du client</span><span class="sxs-lookup"><span data-stu-id="95dc7-122">To enable client versioning</span></span>

  - <span data-ttu-id="95dc7-123">Vous pouvez activer le contrôle de version du client en définissant la propriété **Enabled** sur True ($true).</span><span class="sxs-lookup"><span data-stu-id="95dc7-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="95dc7-124">Pour désactiver le contrôle de version du client</span><span class="sxs-lookup"><span data-stu-id="95dc7-124">To disable client versioning</span></span>

  - <span data-ttu-id="95dc7-125">Vous pouvez désactiver le contrôle de version du client en définissant la propriété **Enabled** sur false ($false).</span><span class="sxs-lookup"><span data-stu-id="95dc7-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="95dc7-126">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="95dc7-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

