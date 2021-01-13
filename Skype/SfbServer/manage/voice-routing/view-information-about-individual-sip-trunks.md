---
title: Afficher des informations sur des trunks SIP individuelles dans Skype Entreprise Server
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
description: Dans Skype Entreprise Server, plusieurs branches peuvent être affectées à une seule passerelle PSTN . Cela signifie que les passerelles et les trunks ne sont pas identiques et que les administrateurs doivent utiliser l'Get-CsTrunk cmdlet pour afficher des informations sur une seule trunk SIP.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826174"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="7626d-103">Afficher des informations sur des trunks SIP individuelles dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7626d-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="7626d-104">Dans Skype Entreprise Server, plusieurs branches peuvent être affectées à une seule passerelle PSTN . Cela signifie que les passerelles et les trunks ne sont pas identiques et que les administrateurs doivent utiliser l';cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une seule trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="7626d-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="7626d-105">La cmdlet Get-CsTrunk peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7626d-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="7626d-106">**Pour afficher des informations pour toutes vos trunks SIP**</span><span class="sxs-lookup"><span data-stu-id="7626d-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="7626d-107">La commande suivante retourne des informations sur toutes les trunks SIP en cours d’utilisation dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="7626d-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="7626d-108">**Pour afficher les informations d’une trunk SIP spécifique**</span><span class="sxs-lookup"><span data-stu-id="7626d-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="7626d-109">Cette commande retourne des informations uniquement pour la trunk SIP dont l’identité est PstnGateway:192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="7626d-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="7626d-110">**Affichage des informations pour toutes les trunks SIP affectées à un pool**</span><span class="sxs-lookup"><span data-stu-id="7626d-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="7626d-111">Dans cet exemple, les informations sont retournées pour toutes les trunks SIP affectées au pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="7626d-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
