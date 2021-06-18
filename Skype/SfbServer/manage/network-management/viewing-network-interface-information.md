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
description: Vous pouvez afficher les informations de l’interface réseau à l’Windows PowerShell l'Get-CsNetworkInterface cmdlet. Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122418"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Affichage des informations d’interface réseau dans Skype Entreprise Server

Vous pouvez afficher les informations de l’interface réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkInterface.** Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Pour voir les informations d’interface réseau

  - Pour afficher les informations de l’interface réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkInterface
    
    Cette commande renvoie des informations comme celles-ci pour chaque interface réseau :
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Pour plus d’informations, voir [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface) (contenu éventuellement en anglais).