---
title: Affichage des informations de l’interface réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez afficher les informations de l’interface réseau à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkInterface. Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279388"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="6774b-104">Affichage des informations de l’interface réseau dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6774b-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="6774b-105">Vous pouvez afficher les informations de l’interface réseau à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="6774b-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="6774b-106">Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6774b-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="6774b-107">Pour afficher les informations sur l’interface réseau</span><span class="sxs-lookup"><span data-stu-id="6774b-107">To view network interface information</span></span>

  - <span data-ttu-id="6774b-108">Pour afficher les informations sur l’interface réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="6774b-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="6774b-109">Cette commande renvoie des informations similaires à ce qui suit pour chaque interface réseau:</span><span class="sxs-lookup"><span data-stu-id="6774b-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="6774b-110">Pour plus d’informations, consultez la rubrique [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="6774b-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


