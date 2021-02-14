---
title: Affichage des informations de l’interface réseau
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez afficher les informations de l’interface réseau à l Windows PowerShell l'Get-CsNetworkInterface cmdlet. Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815134"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="8a50e-104">Affichage des informations d’interface réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8a50e-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="8a50e-105">Vous pouvez afficher les informations de l’interface réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="8a50e-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="8a50e-106">Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50e-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="8a50e-107">Pour voir les informations d’interface réseau</span><span class="sxs-lookup"><span data-stu-id="8a50e-107">To view network interface information</span></span>

  - <span data-ttu-id="8a50e-108">Pour afficher les informations de l’interface réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="8a50e-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="8a50e-109">Cette commande renvoie des informations comme celles-ci pour chaque interface réseau :</span><span class="sxs-lookup"><span data-stu-id="8a50e-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="8a50e-110">Pour plus d’informations, voir [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface) (contenu éventuellement en anglais).</span><span class="sxs-lookup"><span data-stu-id="8a50e-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


