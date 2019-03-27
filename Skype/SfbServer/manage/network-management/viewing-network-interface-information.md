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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Affichage des informations d’interface réseau dans Skype pour Business Server

Vous pouvez afficher les informations d’interface réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkInterface** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Pour afficher les informations d’interface réseau

  - Pour afficher les informations d’interface réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkInterface
    
    Cette commande retourne des informations semblables à ce qui suit pour chaque interface réseau :
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Pour plus d’informations, voir [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


