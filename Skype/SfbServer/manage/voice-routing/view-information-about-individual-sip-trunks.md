---
title: Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype pour Business Server, vous pouvant assigner plusieurs jonctions à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont pas les mêmes, et les administrateurs doivent utiliser l’applet de commande Get-CsTrunk pour afficher des informations sur une jonction SIP individuelle.
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214616"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server

Dans Skype pour Business Server, vous pouvant assigner plusieurs jonctions à une seule passerelle PSTN ; Cela signifie que les passerelles et jonctions ne sont pas les mêmes, et que les administrateurs doivent utiliser l’applet de commande [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.

L’applet de commande Get-CsTrunk peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.

**Pour afficher des informations sur toutes vos jonctions SIP**

La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :

`Get-CsTrunk`

**Pour afficher les informations relatives à une jonction SIP spécifique**

La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Affichage des informations pour toutes les jonctions SIP affectées à un Pool**

Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
