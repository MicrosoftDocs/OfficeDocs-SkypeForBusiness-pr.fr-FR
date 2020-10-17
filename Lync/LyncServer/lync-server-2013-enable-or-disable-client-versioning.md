---
title: 'Lync Server 2013 : activation ou désactivation du contrôle de version du client'
description: 'Lync Server 2013 : activation ou désactivation du contrôle de version du client.'
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
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546620"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="aeb98-103">Activer ou désactiver le contrôle de version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb98-103">Enable or disable client versioning in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb98-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aeb98-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aeb98-105">Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, soit globalement, soit pour des sites particuliers.</span><span class="sxs-lookup"><span data-stu-id="aeb98-105">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="aeb98-106">La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb98-106">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="aeb98-107">Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter.</span><span class="sxs-lookup"><span data-stu-id="aeb98-107">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="aeb98-108">Vous pouvez désactiver la configuration de version du client globale si vous ne souhaitez pas que le contrôle de version du client se produise.</span><span class="sxs-lookup"><span data-stu-id="aeb98-108">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="aeb98-109">Vous pouvez activer ou désactiver le contrôle de version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aeb98-109">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aeb98-110">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="aeb98-110">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="aeb98-111">Pour activer ou désactiver le contrôle de version du client à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="aeb98-111">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aeb98-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aeb98-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aeb98-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aeb98-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aeb98-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aeb98-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aeb98-115">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="aeb98-115">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="aeb98-116">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="aeb98-116">Do the following:</span></span>
    
      - <span data-ttu-id="aeb98-117">Pour activer ou désactiver globalement le contrôle de version du client, double-cliquez sur la configuration **globale** , puis modifiez les paramètres.</span><span class="sxs-lookup"><span data-stu-id="aeb98-117">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="aeb98-118">Pour activer ou désactiver le contrôle de version du client pour un site particulier, cliquez sur **nouveau**, sélectionnez le site, cliquez sur **OK**, puis modifiez les paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="aeb98-118">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aeb98-119">Activation ou désactivation du contrôle de version du client à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb98-119">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aeb98-120">Vous pouvez activer ou désactiver le contrôle de version du client à l’aide de la cmdlet **Set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="aeb98-120">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="aeb98-121">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeb98-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aeb98-122">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="aeb98-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="aeb98-123">Pour activer le contrôle de version du client</span><span class="sxs-lookup"><span data-stu-id="aeb98-123">To enable client versioning</span></span>

  - <span data-ttu-id="aeb98-124">Vous pouvez activer le contrôle de version du client en affectant à la propriété **Enabled** la valeur True ($true).</span><span class="sxs-lookup"><span data-stu-id="aeb98-124">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="aeb98-125">Pour désactiver le contrôle de version du client</span><span class="sxs-lookup"><span data-stu-id="aeb98-125">To disable client versioning</span></span>

  - <span data-ttu-id="aeb98-126">Vous pouvez désactiver le contrôle de version du client en affectant à la propriété **Enabled** la valeur false ($false).</span><span class="sxs-lookup"><span data-stu-id="aeb98-126">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="aeb98-127">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="aeb98-127">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

