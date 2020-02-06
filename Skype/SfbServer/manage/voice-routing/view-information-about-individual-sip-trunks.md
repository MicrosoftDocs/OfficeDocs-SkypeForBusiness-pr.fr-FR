---
title: Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server
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
description: Dans Skype entreprise Server, plusieurs Trunks peuvent être affectées à une seule passerelle RTC ; Cela signifie que les passerelles et les Trunks ne sont pas les mêmes et qu’ils doivent utiliser l’applet de cmdlet Get-CsTrunk pour afficher des informations sur un Trunk SIP individuel.
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816923"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server

Dans Skype entreprise Server, plusieurs Trunks peuvent être affectées à une seule passerelle RTC ; Cela signifie que les passerelles et les Trunks ne sont pas les mêmes que les passerelles et les administrateurs doivent utiliser l’applet de passe [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur un Trunk SIP individuel.

Vous pouvez exécuter l’applet de commande Get-CsTrunk à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.

**Pour afficher des informations sur toutes vos jonctions SIP**

La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :

`Get-CsTrunk`

**Pour afficher les informations relatives à une jonction SIP spécifique**

La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Affichage des informations pour toutes les lignes SIP attribuées à un pool**

Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
