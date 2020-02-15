---
title: Afficher des informations sur des jonctions SIP individuelles dans Skype entreprise Server
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
description: Dans Skype entreprise Server, plusieurs jonctions peuvent être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont pas un et que les administrateurs doivent utiliser la cmdlet Get-CsTrunk pour afficher des informations sur une jonction SIP individuelle.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048177"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Afficher des informations sur des jonctions SIP individuelles dans Skype entreprise Server

Dans Skype entreprise Server, plusieurs jonctions peuvent être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont pas une seule et même, et que les administrateurs doivent utiliser la cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.

La cmdlet Get-CsTrunk peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.

**Pour afficher les informations de toutes vos jonctions SIP**

La commande suivante retourne des informations sur toutes les jonctions SIP utilisées dans votre organisation :

`Get-CsTrunk`

**Pour afficher les informations d’une jonction SIP spécifique**

Cette commande renvoie des informations uniquement pour la jonction SIP avec l’identité PstnGateway : 192.168.0.240 :

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Affichage des informations pour toutes les jonctions SIP affectées à un pool**

Dans cet exemple, les informations sont renvoyées pour toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com :

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
