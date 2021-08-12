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
ms.openlocfilehash: 482655d36a16158866207e9157d25288e418f7e9ee00dc88ea7a59d653e5c566
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281797"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Affichage des informations de l’interface réseau dans Skype Entreprise Server

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