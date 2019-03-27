---
title: Affichage des informations d’interface réseau
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez afficher les informations d’interface réseau à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkInterface. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888028"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="07a50-104">Affichage des informations d’interface réseau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="07a50-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="07a50-105">Vous pouvez afficher les informations d’interface réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="07a50-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="07a50-106">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07a50-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="07a50-107">Pour afficher les informations d’interface réseau</span><span class="sxs-lookup"><span data-stu-id="07a50-107">To view network interface information</span></span>

  - <span data-ttu-id="07a50-108">Pour afficher les informations d’interface réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="07a50-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="07a50-109">Cette commande retourne des informations semblables à ce qui suit pour chaque interface réseau :</span><span class="sxs-lookup"><span data-stu-id="07a50-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="07a50-110">Pour plus d’informations, voir [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="07a50-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


