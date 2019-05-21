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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Affichage des informations de l’interface réseau dans Skype entreprise Server

Vous pouvez afficher les informations de l’interface réseau à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsNetworkInterface** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Pour afficher les informations sur l’interface réseau

  - Pour afficher les informations sur l’interface réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
    
        Get-CsNetworkInterface
    
    Cette commande renvoie des informations similaires à ce qui suit pour chaque interface réseau:
    
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


