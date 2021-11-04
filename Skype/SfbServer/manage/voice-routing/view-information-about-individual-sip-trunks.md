---
title: 'Skype Entreprise Server : afficher des informations sur les différentes trunks SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Dans Skype Entreprise Server, plusieurs branches peuvent être affectées à une seule passerelle PSTN. Les passerelles et les trunks ne sont pas identiques, et les administrateurs doivent utiliser la cmdlet Get-CsTrunk pour afficher des informations sur une trunk SIP individuelle.
ms.openlocfilehash: dc5ccfdb5e248d843fb3a8a4e926a7e462097789
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774714"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype Entreprise Server : afficher des informations sur les différentes trunks SIP

Dans Skype Entreprise Server, plusieurs trunks peuvent être affectés à une seule passerelle PSTN ; Cela signifie que les passerelles et les trunks ne sont pas identiques et que les administrateurs doivent utiliser l';cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une trunk SIP individuelle.

La cmdlet Get-CsTrunk peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.

**Pour afficher des informations pour toutes vos trunks SIP**

La commande suivante retourne des informations sur toutes les trunks SIP en cours d’utilisation dans votre organisation :

`Get-CsTrunk`

**Pour afficher les informations d’une trunk SIP spécifique**

Cette commande retourne des informations uniquement pour la trunk SIP dont l’identité est PstnGateway:192.168.0.240 :

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Affichage des informations pour toutes les trunks SIP affectées à un pool**

Dans cet exemple, les informations sont retournées pour toutes les trunks SIP affectées au pool atl-cs-001.litwareinc.com :

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
