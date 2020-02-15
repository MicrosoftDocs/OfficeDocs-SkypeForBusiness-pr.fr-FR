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
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="0e1a4-103">Afficher des informations sur des jonctions SIP individuelles dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0e1a4-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="0e1a4-104">Dans Skype entreprise Server, plusieurs jonctions peuvent être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont pas une seule et même, et que les administrateurs doivent utiliser la cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.</span><span class="sxs-lookup"><span data-stu-id="0e1a4-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="0e1a4-105">La cmdlet Get-CsTrunk peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e1a4-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="0e1a4-106">**Pour afficher les informations de toutes vos jonctions SIP**</span><span class="sxs-lookup"><span data-stu-id="0e1a4-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="0e1a4-107">La commande suivante retourne des informations sur toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="0e1a4-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="0e1a4-108">**Pour afficher les informations d’une jonction SIP spécifique**</span><span class="sxs-lookup"><span data-stu-id="0e1a4-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="0e1a4-109">Cette commande renvoie des informations uniquement pour la jonction SIP avec l’identité PstnGateway : 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="0e1a4-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="0e1a4-110">**Affichage des informations pour toutes les jonctions SIP affectées à un pool**</span><span class="sxs-lookup"><span data-stu-id="0e1a4-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="0e1a4-111">Dans cet exemple, les informations sont renvoyées pour toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="0e1a4-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
