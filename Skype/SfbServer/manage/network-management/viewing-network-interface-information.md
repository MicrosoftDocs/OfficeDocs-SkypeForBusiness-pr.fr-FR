---
title: Affichage des informations de l’interface réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez afficher les informations de l’interface réseau à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkInterface. Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817350"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Affichage des informations de l’interface réseau dans Skype entreprise Server

Vous pouvez afficher les informations de l’interface réseau à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsNetworkInterface** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Pour afficher les informations sur l’interface réseau

  - Pour afficher les informations sur l’interface réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkInterface
    
    Cette commande renvoie des informations similaires à ce qui suit pour chaque interface réseau :
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Pour plus d’informations, consultez la rubrique [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


